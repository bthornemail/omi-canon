# Q1 — What Is the Source of Truth?

**Answer:** The algorithm is the source of truth.

## Core Principle

No artifact holds authority by position. No document holds authority by title. No witness holds authority by presence. Only the deterministic execution of the law — the algorithm — produces canonical truth.

This follows from the OMI Collapse: representation and interpretation are one surface. The algorithm that transitions state and the algorithm that verifies state are the same algorithm. There is no external validator. There is no separate oracle. The law is self-certifying.

---

## A1 — Transition

### Constructive Proof
Canonical state is derived only from deterministic transition over prior state plus law constants (Delta Law rotation-XOR structure with period 8). Given the same prior state and the same tick, the transition algorithm always produces the same next state. The proof chain is: prior state → Δ_C → next state → receipt → replay verification.

### Falsification Proof
Any direct manual state overwrite that bypasses the transition function produces a replay mismatch. If the stored state S' differs from Δ_C(S) for the prior state S, replay over the trace will detect the divergence. A falsified state cannot be reconstructed by replaying the law.

---

## A2 — Control-Plane

### Constructive Proof
Interpretation state is explicit in the canonical tuple: `(channel, lane, mode, scope, numsys)`. The control plane separates FS (frame start), GS (group start), RS (record start), US (unit start), ESC (escape), and NULL into typed structural markers. The parsing state is derivable from the stream position alone — no hidden register maintains undisclosed control context.

### Falsification Proof
Hidden parser or control state not derivable from the serialized stream is non-canonical. If an implementation maintains a private mode flag that is not deterministically reconstructable from the byte stream, that implementation fails the Q1 invariant. Two parsers with different hidden states produce different interpretations of the same stream — the algorithm is no longer the sole source of truth.

---

## A3 — Projection

### Constructive Proof
Views (text, graph, SVG, 3D, XR) are generated from canonical state by the projection algorithm. Every projection is rebuildable from the source state. Given the canonical state at tick T and the projection rule (surface selector + rewrite table), the output is deterministic. Any two projections of the same type for the same state are byte-identical.

### Falsification Proof
Treating a cached projection artifact as authority causes divergence from recomputed output. If a renderer serves a stale projection while the canonical state has advanced, the artifact misrepresents truth. Projection cache may improve performance but must be invalidated when the source state changes. A projection that cannot be invalidated becomes authority — this is invalid by law.

---

## A4 — Escape

### Constructive Proof
Interrupt semantics are law-defined: ESC introduces a bounded scope, the interpreter reads sub-instructions within that scope, and ESC terminates the scope with a deterministic return to the data stream. The escape algorithm is part of the canonical interpreter; it does not bypass the transition law. Post-interrupt continuation resumes at the lawful next frame.

### Falsification Proof
Implicit escape or unclosed interrupt breaks deterministic decoding and is rejected. If the interpreter enters an escape scope but the stream ends before ESC terminates, the frame is malformed and must be rejected. An escape scope that does not close violates the source-of-truth invariant because there is no lawful next state.

---

## A5 — Partition & Chirality (Fano Selection)

### Constructive Proof
Partition topology is deterministic: given a Fano plane and the canonical state, the partition algorithm produces the same N subsets in the same arrangement. Chirality ordering is kernel-derived per tick: `chirality = f(kernel_state, tick)` determines which half of each partition is labeled `ο` (inbound/entry) and which is labeled `Ο` (outbound/closure). The selection is reproducible from the same seed and tick.

### Falsification Proof
Any hardcoded subset ordering or non-kernel orientation is invalid. If the partition labels first/second based on a static lookup table instead of computing from kernel state + tick, then two runs with different canonical states but the same lookup table produce the same order — the algorithm is no longer the source of truth. Similarly, chirality derived from wall-clock time or random source is invalid.

---

## A6 — Proposal/Receipt

### Constructive Proof
Proposed changes are represented as explicit artifacts before application. The proposal is a well-formed OMI frame with a proposal flag. The receipt is a deterministic acknowledgment: `provenance | steps | LL | NN | MM`. No state transition occurs without a proposal-receipt pair. The algorithm that processes proposals and the algorithm that verifies receipts are the same law-defined procedure.

### Falsification Proof
Silent, unreceipted mutation has no lawful proof trail and is invalid. If an agent modifies canonical state without first issuing a proposal and receiving a receipt, there is no audit entry. Replay cannot reconstruct the transition. Any mutation without a matching receipt is a violation of Q1 — the algorithm was not the source of the change.

---

## A7 — Branch/Reconciliation

### Constructive Proof
The canonical trace remains the reference. Branch traces are explicitly anchored to a base index in the canonical trace. Both canonical and branch traces follow the same transition law. The branch algorithm stores: `(base_index, delta_set, return_pointer)`. The reconciliation algorithm can reconstruct the branch trajectory from these three values. The source of truth for reconciliation is the merge of canonical law + branch delta, not a manual merge result.

### Falsification Proof
Branch overwrite of canonical reference without merge law is invalid. If a branch is merged into canonical state without going through the reconciliation algorithm, the canonical trace loses its authority. The merged state is not derivable from the canonical trace alone — an external intervention inserted state without law-defined procedure. This violates Q1.
