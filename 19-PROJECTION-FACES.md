# State 19 — Projection Faces: The Vocabulary

## What This State Is

This state is the transition from "what cannot be reduced" to "how it becomes visible." After establishing the irreducible primitives, I needed to define how accepted truth is exposed, folded, projected, and inspected.

This is the state where the invisible becomes visible.

---

## 1. What Is a Face?

A face is the answer to: *how does a Relation appear?*

Every face follows the same four-step derivation:

```text
Relation        — the irreducible object (Null, Bit, Pair, Relation)
    ↓
Face            — the named surface orientation (which way the Relation is read)
    ↓
Projection      — the algorithm mapping Relation → surface representation
    ↓
Carrier         — the concrete medium (buffer, stream, pixel, memory)
```

A **face** is not the projection. The face names a **reading orientation**. The projection implements that orientation. The carrier transports the result.

The same Relation can be read through many faces. Each face is a different answer to: *what does this mean when viewed this way?*

Examples of faces:
- **Omi-Ring** — the 5040-slot replay ring read as a circular store
- **Omi-World** — the blackboard surface read as a navigable space
- **Omi-Sense** — analog signals read as candidate Relations
- **Omi-Portal** — the external nondeterminism boundary read as a gate
- **Omi-Gnomon** — gauge orientation read as selection index

These are not implementation names. They are **vocabulary items** — the terms used to describe which face a projection is realizing.

---

## 2. Projection Is Not Authority

This is the first and most important principle of this state:

```text
projection != validation
projection != authority
render != believe
```

A projection displays accepted state. It does not create it.

The entire system is protected by one invariant: **only validation and receipt may accept**. Projection is always downstream of acceptance. It can display, suggest, or render — but it cannot validate or accept.

---

## 3. Carrier Implementations

Once the face vocabulary is established, any concrete rendering technology is merely another carrier. The current set includes:

### Text and Symbolic Carriers
- **Markdown / HTML / PDF** — human-readable document projections
- **CLI / TUI** — terminal-oriented projections
- **SVG / Canvas / QR / barcode** — visual graphic carriers

### Structured Data Carriers
- **DOM / CSSOM / JSDOM** — browser document model projections
- **JSON Canvas** — graph-oriented addressable surface

### Network and Hardware Carriers
- **SSE / WAN telemetry** — streaming event projections
- **IPv6 frame / eBPF gate** — kernel-level network projections

### Memory Carriers
- **5040 ring / receipt** — internal storage projection

Each carrier implements the four-step face derivation. None creates authority. None validates. Each is downstream of acceptance.

---

## 4. The Projection Hierarchy

```text
Guiding gates:
  ONTOLOGY.md, DOCTRINE.md, FOUNDATIONS.md, ATOMIC-KERNEL.md

Executable truth gates:
  RULES.omi  (MUST)
  FACTS.omi  (FACT)
  CLOSURES.omi  (CLOSE)
  COMBINATORS.omi  (COMBINE)
  CONS.omi  (CONS)

Compiled mirrors:
  RULES.imo, FACTS.imo, CLOSURES.imo, COMBINATORS.imo, CONS.imo

Carrier surfaces:
  DOM / CSSOM / JSDOM
  JSON Canvas
  SSE / WAN telemetry
  IPv6 frame / eBPF gate
  Markdown / PDF / HTML
  CLI / TUI
  Visual (SVG / Canvas / QR / barcode)
  Memory (5040 ring / receipt)
```
  Markdown / PDF / HTML
  CLI / TUI
  Visual (SVG / Canvas / QR / barcode)
  Memory (5040 ring / receipt)
```

---

## 3. The Pipeline

```text
validate → resolve → record → materialize → project → inspect
```

Projection is the sixth stage. It is never the first.

Canonical order:

```text
Q_frame(S) validates the carrier.
nibble-walk selects the local region.
Base36 indexes the socket.
Q_xy projects the coordinate.
ψ(frame, path, socket, receipt) instantiates one slice.
DOM exposes the accepted projection.
```

---

## 4. The Six DOM Projection Handles

OMI uses six DOM projection handles:

```text
id             → local pointer / selector hook
data-omi       → readable declaration surface
data-imo       → interpreted mirror surface
<o>            → object carrier boundary
<omi>          → declaration container
<imo>          → interpretation / receipt container
```

These handles provide the bridge between the abstract OMI frame geometry and the concrete browser DOM. An OMI address like `omi-0500-03bf-0000-2b05-2f05-0000-039f-05ff` can select a DOM node via CSS attribute selectors.

---

## 5. The Four Gauges

```text
o---o  = Gauge 0 / FS  / object / file / carrier boundary
/---/  = Gauge 1 / GS  / path   / group / context
?---?  = Gauge 2 / RS  / query  / record / relation
@---@  = Gauge 3 / US  / socket / unit / point
```

These four gauges define the carrier surface for every OMI object:

```text
o---o/---/?v=<base64url>;l=<length>;h=<hash>@<base36-ref>@
```

Each gauge is a different mode of access:

| Gauge | Name | Access Mode | Question |
|-------|------|-------------|----------|
| `o---o` | FS | Boundary | What is the object? |
| `/---/` | GS | Navigation | Where is it? |
| `?---?` | RS | Query | What does it reference? |
| `@---@` | US | Socket | Where does it terminate? |

---

## 6. The Bridge Equation

The spatial projection from OMI coordinates to visual geometry is governed by one binary quadratic form:

```text
Q_xy(x,y) = 60x² + 16xy + 4y²
          = 4(15x² + 4xy + y²)
```

Properties:

- Matrix is positive-definite (determinant 176) → elliptic paraboloid surface, no saddle points
- Q(0,0) = 0
- Q(3,3) = 720
- Q(x,y) is integer for x,y in 0..3
- Q(x,y)/6 lies within 0..120 for x,y in 0..3
- Q(x,y) mod 240 ranges within 0..239

Projection assertions:

```text
local240 = Q(x,y) mod 240
slot5040 = fano7×720 + role3×240 + local240
```

The coefficients encode physical domain boundaries:

- **60x²** = the High/IMO domain (CSS `id` attribute, sexagesimal spatial orientation)
- **4y²** = the Low/OMI domain (HTML `data-*` attribute, localized atomic data)
- **16xy** = the cross-term (the CSSOM/JSDOM bridge where code meets DOM)

---

## 7. The Meta-Circular Compiler

### 7.1 The Concept

The OMI meta-circular compiler is a compiler that can compile itself — a demonstration that the cosmology is self-hosting. The compiler reads `.omi` source files, validates them through `Q_frame`, resolves truth rows, writes receipts, and emits `.imo` compiled output.

### 7.2 The Compilation Pipeline

```text
.omi source
  → lexer (hex, anchors, segments)
  → parser (frame, truth row, rule)
  → validator (Q_frame = 0)
  → resolver (Delta/Fano)
  → code generator (32-slot ISA)
  → .imo output
```

### 7.3 Self-Hosting

The meta-circular property: the compiler can compile its own source code. The compiler's rules are declared in `RULES.omi`, grounded in `FACTS.omi`, and compiled through the same pipeline as any other OMI object.

This is not a trick. It is a proof that the cosmology is complete — that the system can describe its own operation within its own terms.

---

## 8. Wormhole Portals

### 8.1 The Wormhole Model

A wormhole portal is a projection surface that connects two OMI addresses across different contexts without merging them. It is the OMI equivalent of a hyperlink, but with structural guarantees.

### 8.2 Portal Properties

- **One object, many portals**: The same accepted object can be projected through different wormhole surfaces
- **Portable context**: The portal carries the frame, receipt, and projection parameters
- **Validation before projection**: The portal does not create validity — it displays what has been validated
- **Agreement without platform lock-in**: Portals can be implemented in any environment that understands the frame format

### 8.3 The Portal Promise

```
One object.
Many portals.
Inspectable history.
Portable context.
Validation before projection.
Agreement without platform lock-in.
```

---

## 9. Control Codes and Printable Projections

### 9.1 The Split

The ASCII range splits naturally into two domains:

| Range | Type | Role |
|-------|------|------|
| 0x00–0x1F | Control | Rewrite operators |
| 0x20–0x7F | Printable | Projection surfaces |

### 9.2 Control Codes as Operators

In OMI, control codes are not characters. They are **operators** that signal transitions between states of interpretation:

| Code | Name | Operation |
|------|------|-----------|
| 0x00 | NUL | Closure / projective center |
| 0x01 | SOH | Start of heading |
| 0x02 | STX | Start of text / omi entry |
| 0x03 | ETX | End of text / imo exit |
| 0x04 | EOT | End of transmission |
| 0x05 | ENQ | Enquiry / probe |
| 0x06 | ACK | Acknowledge / receipt |
| 0x07 | BEL | Attention / alert |
| 0x08 | BS | Backspace / retract |
| 0x09 | HT | Horizontal tab / scale advance |
| 0x0A | LF | Line feed / orbit step |
| 0x0B | VT | Vertical tab / plane shift |
| 0x0C | FF | Form feed / frame advance |
| 0x0D | CR | Carriage return / reset |
| 0x0E | SO | Shift out / omi mode |
| 0x0F | SI | Shift in / imo mode |

### 9.3 The Space Projection

Space (0x20) is not nothing. It is **visible absence** — the printable projection of the closure state. It is the empty pivot around which all printable projections rotate.

### 9.4 The Delete Sentinel

Delete (0x7F) is not ordinary text. It is a **terminal sentinel** — the boundary between the printable range and the extended ranges beyond.

---

## 10. Base36 Response Rule

Base36 may respond only after frame validation:

```text
Q_frame(S) = 0
  → Base36 reference socket may resolve
  → local x,y coordinates may be derived
  → Q_xy may project
  → receipt may accept
```

Invalid:

```text
Base36 symbol authorizes state
DOM id authorizes state
emoji authorizes state
barcode authorizes state
```

---

## 11. Deterministic GUI Projection

CSS / DOM / JSDOM may manipulate OMI reference projections. They do not mutate OMI truth directly.

```text
CSS selects projection.
JSDOM manipulates structure.
DOM receives interaction.
OMI validates.
Omi-Attestation witnesses.
Accepted Omi-State may be recorded.
```

The GUI is never the source of truth. It is always a projection of accepted state.

---

## The Transition to State 12

From this state — having defined the vocabulary of named faces — I moved to State 18 (Gauge Interrupts) to answer: which interpretation is selected? How does the gauge choose the reading orientation?

Continue to `18-GAUGE-INTERRUPTS.md`.
