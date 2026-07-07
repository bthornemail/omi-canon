# Q3 — How Does It Distinguish Payload from Control?

**Answer:** A canonical control plane separates structural roles from payload.

## Core Principle

Every byte in an OMI frame has a declared interpretation. The control plane — FS, GS, RS, US, ESC, NULL — are typed markers with fixed structural semantics. Payload is everything that is not control. The distinction is not negotiated by the communicating parties. It is not a matter of convention. It is a structural property of the frame format.

This is the OMI Collapse applied to protocol design: the same binary surface carries both control structure and payload content, but the interpretation of each bit is determined by its position within the frame, not by an external schema.

---

## A1 — Transition

### Constructive Proof
The state machine update does not conflate parser mode with payload value. The Delta Law operates on the 16-bit state segments. It does not care whether a segment is control or payload — it transforms the numerical value. The separation is maintained by the frame validation step (Q_frame(S) = 0) which runs before the transition. If the frame passes validation, the transition proceeds. Control/payload semantics are enforced at the boundary, not inside the arithmetic.

### Falsification Proof
Mixed undecidable token semantics causes undefined transition path. If a given byte value could be either control or payload depending on context that is not captured in the frame itself, the transition cannot determine which segments to transform. The Delta Law operates on fixed positions — ambiguity in segment identity leads to ambiguity in the next state.

---

## A2 — Control-Plane

### Constructive Proof
FS, GS, RS, US, ESC, and NULL semantics are explicit and typed. The control markers occupy fixed positions in the frame:

| Marker | Position | Value | Meaning |
|--------|----------|-------|---------|
| FS | Segment 0 high | 0x05 | Frame start |
| GS | Segment 3 high | 0x2B | Group start |
| RS | Segment 4 high | 0x2F | Record start |
| US | Segment 6 | 0x039F | Unit start |
| ESC | Segment 1 | 0x03BF | Escape prefix |
| NULL | Segment 7 low | 0xFF | Scope terminator |

These markers are not values that could appear in payload — they are structural. Any byte sequence that matches a control marker is a control marker, not payload.

### Falsification Proof
Ambiguous control token interpretation is rejected fail-closed. If a parser encounters a byte that could be either a control marker or a payload byte (because the schema is not fully specified), the parser must reject the frame. The fail-closed rule ensures that ambiguity never propagates. The frame must have a single unambiguous interpretation, or it is invalid.

---

## A3 — Projection

### Constructive Proof
The renderer consumes already-decoded state, not undecoded stream control. By the time the projection algorithm reads the canonical state, the control/payload separation has already been performed by the parser. The projection algorithm does not need to distinguish control from payload — it receives decoded segments with known types. The renderer displays what the parser has already separated.

### Falsification Proof
Renderer-side guessing of control boundaries creates non-canonical views. If the projection algorithm attempts to re-parse the raw stream to infer structure (instead of consuming decoded state), it may guess boundaries differently from the canonical parser. The resulting view would not match the canonical interpretation. A projection must consume decoded state, not raw bytes.

---

## A4 — Escape

### Constructive Proof
ESC ESC literalization preserves payload transparency of the reserved token. When the payload contains the byte value 0x03BF (the ESC marker), it is escaped by doubling: ESC ESC. The interpreter reads the doubled marker as a literal payload byte, not as an escape command. This ensures that control markers can appear in payload without being mistaken for control.

### Falsification Proof
Unknown escape targets are rejected, preventing control/payload confusion. If the interpreter encounters ESC followed by a byte that is not a recognized escape target, it must reject the frame. There is no "interpret as payload" fallback for unknown escapes. A rejected frame preserves the control/payload boundary — an accepted frame with ambiguous escape semantics would collapse the boundary.

---

## A5 — Partition & Chirality (Fano Selection)

### Constructive Proof
A5 controls partition and orientation only; it does not parse stream classes. The partition algorithm operates on the canonical state after the frame has been validated and control/payload separation is complete. It never sees raw bytes. It never makes parsing decisions. Its inputs are decoded segments with known types.

### Falsification Proof
Using A5 as parser authority violates control-plane law. If the partition algorithm attempts to determine segment types (e.g., "is this segment control or payload?") it oversteps its constitutional role. The partition algorithm divides already-parsed state. It does not parse. Any implementation that conflates partition selection with parsing is invalid.

---

## A6 — Proposal/Receipt

### Constructive Proof
Proposal artifacts are explicit objects, not hidden inline control bytes. A proposal is a well-formed OMI frame with a proposal flag in the control segment. It is not a special byte sequence hidden inside the payload. The receipt is a similarly explicit acknowledgment structure. Both are subject to the same control/payload separation as any other frame.

### Falsification Proof
Inline hidden commands without artifact schema are invalid. If an agent encodes a state-changing command as a specialized byte sequence within payload (e.g., a magic number that means "accept this proposal"), the control/payload boundary is violated. Control functions (propose, accept, reject, commit) must be explicit structural operations, not payload-embedded signals.

---

## A7 — Branch/Reconciliation

### Constructive Proof
Deltas are scoped by layer (canonical, branch, shared). The branch algorithm explicitly separates which segments belong to the canonical trace, which belong to the branch, and which are shared between them. The scoping is encoded in the branch header, not inferred from payload content. Control markers determine the scope of each delta.

### Falsification Proof
Cross-scope leakage of control intent without law is invalid. If a branch delta affects canonical segments without an explicit merge reconciliation step, the control intent of the branch has leaked into the canonical scope. The system cannot distinguish "this change belongs to the branch" from "this change belongs to the canonical trace" — the boundary is collapsed. All deltas must be explicitly scoped.
