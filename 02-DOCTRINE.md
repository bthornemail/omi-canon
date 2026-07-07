# State 02 — Doctrine: The Law

## What This State Is

This state is the transition from "what exists" to "what must be preserved." After discovering and naming the elements of the cosmology, I needed to articulate the invariant laws — the rules that cannot be broken without breaking the system.

The doctrine is the collapse point. Gauge tables, factorial towers, the 240 bridge, the 5040 ring, Miquel configurations, hyper-configurations, Fano selectors, quadratic laws, and error-correcting lattices are **consequences** of the doctrine, not the doctrine itself.

---

## Part I — Root Doctrine

### 1. The Central Doctrine

> **The reader may recognize. The resolver may promote. Only validation and receipt may accept.**

This is the spine of OMI. It enforces a strict separation of concerns:

| Forbidden Shortcut | Meaning |
|---|---|
| `prefix → identity` | A naming string does not constitute identity |
| `gossip → authority` | Network availability is not acceptance |
| `render → believe` | Display is not truth |
| `controller → outside receipt` | No controller operates without a receipt |

**Carrier is not authority.** A DOM node, a CSS rule, a JSON object, a QR code, a gossip network, or a portal display — none of these carry authority by themselves.

### 2. The OMI Collapse

Every major computing paradigm begins by collapsing a boundary that once seemed natural.

**Lisp collapsed program and object:**

```text
code ↔ data
```

An S-expression can be read as structure, stored as data, or evaluated as program.

**POSIX collapsed storage and communication:**

```text
storage ↔ communication
```

A file descriptor can point to a disk file, a terminal, a pipe, or a network socket.

**OMI collapses representation and interpretation:**

```text
representation ↔ interpretation
notation ↔ cipher
```

The artifact of this collapse is the **rewrite surface**. The same binary source may be interpreted through multiple lawful readings without changing the source itself.

### 3. The OMI Principle

```text
The binary source remains.
The reading changes.
Computation is the lawful rewrite of interpretation rather than the mutation of data.
```

Traditional systems treat computation as mutation:

```text
input → transformation → output
```

OMI treats computation as reinterpretation:

```text
source → notation → reading → receipt
```

The source remains unchanged. The reading rotates. The rewrite is the computation.

### 4. Notation as Cipher

A notation declares how a surface shall be read.
A cipher declares how a surface shall be transformed.

OMI removes the distinction:

```text
notation as cipher
cipher as notation
```

A cipher does not hide meaning. A cipher declares meaning. A notation is a cipher because it tells the reader how to interpret the same surface. A cipher is notation because it defines the rules by which a surface becomes readable.

This is not secrecy. This is interpretation.

### 5. Rewrite Topology

The database view says: `address → data`
The OMI view says: `address → interpretation surface`

Canonical flow:

```text
source → notation → interpretation → validation → receipt
```

Traditional computing stores values and computes transformations.
OMI registers transformations and computes values.

The binary source of truth remains fixed. Meaning emerges from the declared rewrite path through the register.

### 6. Strict Architecture Pipeline

```text
Level 5: Implementations  — gauge tables, 240 bridge, hyper-configuration
Level 4: Addressing       — omi---imo, slash-path routing, frame buffers
Level 3: Topology         — projective closure, Fano coordinates
Level 2: Dynamics         — canonical Delta_C orbit steps
Level 1: Surface          — representation ↔ interpretation
Level 0: Doctrine         — notation ↔ cipher
```

Level 0 is the ontological core: meaning and mechanism are not separate. A representation does not contain inherent semantic truth; it contains structural truth that must be unlocked by an active reading context.

Level 5 includes specific mathematical structures — lattices, gnomons, bridges, rings, selectors, and hyper-configurations. These are implementation choices. They can evolve without changing the doctrine.

---

## Part II — Doctrinal Consequences

### 7. Binary Sources of Truth

An OMI source of truth is a binary bitboard. That bitboard is versioned. It is not treated as mutable database state. It is treated as a declared rewrite surface.

The bitboard can be loaded into memory as:

```text
omi---imo
```

where:

```text
omi---imo = binary rewrite identity
/---/     = routed interpretation path
?---?     = external payload or stream attachment
```

### 8. No Database Layer

OMI is not a database. It is closer to:

```text
versioned source
rewrite table
ring register
nomogram scale
receipt machine
rewrite topology
```

A database asks: "What value is stored here?"
OMI asks: "What lawful rewrite is declared here?"

### 9. Rotation Instead of Mutation

A shift discards information. A rotation preserves information.

The canonical law:

```text
Delta_C(x) = rotl(x,1) xor rotl(x,3) xor rotr(x,2) xor C
```

Nothing falls off the edge. The edge returns through the orbit.

### 10. Projective Closure

Finite computational spaces possess closure:

```text
16 states: 15 active, 1 closure
8 states:  7 active, 1 closure
```

The closure state is not absent. It is the projective center through which the orbit returns.

### 11. The Empty List Principle

In Lisp: `nil == ()` — the empty list is simultaneously atom and list.

OMI treats closure the same way. The closure state is both a point and a space. It is origin and container.

### 12. The Slash Path

The `/---/` path is where rerouting happens:

```text
omi-<frame>-imo/<control>/<scale>/<relation>/<unit>
```

The slash path is not storage. It is interpretation routing.

### 13. Omi-Nomogram

Omi-Nomogram is the runtime scale selector — the equivalent of a slide-rule scale table:

```text
0x30 identity / unity
0x31 C/D multiply-divide
0x32 A/B square-root
0x33 K cube-root
0x34 folded pi scale
0x35 reciprocal scale
0x36 sine/cosine
0x37 tangent/cotangent
0x38 small-angle / degree-radian
0x39 Pythagorean
0x3A log10
0x3B natural log / exponential
0x3C sexagesimal gate
0x3D arbitrary powers
0x3E quadratic / gnomon
0x3F LFSR / period / replay
```

The scale does not store the result. The scale declares how the result is read.

---

## Part III — The Agreement Model

### 14. What Agreement Is

Agreement in OMI is **not** a feeling, vote, platform decision, or display rendering. It is a **structural event** with a rigorous pipeline:

```
reader → resolver → validation → receipt → materializer → projection → inspection
```

| Step | Function |
|---|---|
| **Reader** | Recognizes a form (an `omi---imo` pattern, a frame candidate, a DOM carrier, a gossip fragment). Recognition is not acceptance. |
| **Resolver** | Promotes a recognized form into a candidate (possible frame, edit, object, route, receipt, reconstruction). Promotion is not acceptance. |
| **Validation** | Checks the frame structurally via `Q_frame(S) = 0`. If the structure fails, the object rejects. |
| **Resolution** | Extracts the truth row `(LL, NN, MM)` and proves `NN → MM` through the Delta/Fano path. |
| **Receipt** | Writes a 64-bit receipt as the acceptance boundary. Only validation and receipt may accept. |
| **Materializer** | Applies the accepted rule address to affect object structure, document projection, DOM state, etc. |
| **Projection** | Displays the accepted state via DOM, SVG, Canvas, QR, portal cards, etc. Projection is downstream. |
| **Inspection** | Explains why the object should be trusted — shows source, frame, truth row, receipts, replay, conflicts, materializer rule, projection path. |

### 15. The Truth Row

Every valid frame yields exactly one truth row: `(LL, NN, MM)`.

- `LL` = the ket-like scope selector (two nibbles: high = context/family, low = execution slot)
- `NN` = antecedent (beginning)
- `MM` = consequent (resolution)
- The proven transition is `NN → MM` through Delta/Fano.

### 16. The 0xE_ Agreement Manifold

The `0xE0-0xEF` band is the single accepted execution manifold:

| Slots | Role |
|---|---|
| `0xE0-0xEB` (12) | **Inner materializers** — page-frame-root, DOM import/export, CSSOM import/export, JSDOM normalization, OMI object patch, edge/vertex traversal, snub bridge, stellated octahedron mirror, Fano triangle selection, face band, receipt projection/export |
| `0xEC-0xEF` (4) | **Outer controller vertices** — translation/viewport/focus, scale/recursion depth, rotation/spin/orientation, boundary/opacity/clipping |

### 17. The Gate and the Registry

- **The Gate** is blind: parses frame, validates, extracts truth row, resolves Delta, derives slot, writes receipt, emits envelope. It knows nothing of geometry, DOM, or application semantics.
- **The Registry** owns meaning: reads the accepted envelope, looks up the rule slot, applies the implementation, projects and explains the result.

### 18. Agreement Without Collapse

Peers may hold different orientations (edge vs. vertex vs. face traversal) while sharing the same accepted center. Chirality is not disagreement — it is oriented complementarity.

---

## Part IV — Conformance Canon

### 19. Required Acceptance Pipeline

A conforming OMI implementation **must preserve**:

```
frame S
  → anchor check
  → Q_frame(S) = 0
  → truth row (LL, NN, MM)
  → LL-modulated Delta/Fano resolution
  → 64-bit receipt
  → 5040-slot replay ring (7! = 5040)
  → projection
```

### 20. The 12 Required Rules

1. Recognize `0x03BF` and `0x039F` as canonical lower frame anchors.
2. Validate frames via `Q_frame(S) = E_var + E_const = 0`.
3. Treat `Q_frame` as the **sole** structural admission predicate.
4. Extract exactly one truth row `(LL, NN, MM)` from a valid frame.
5. Implement the Delta Law with circular rotations, XOR mixing, and explicit 16-bit masking.
6. Implement LL-modulated Fano resolution for accepted truth rows.
7. Reject truth rows that do not resolve inside the bounded Fano window (max 15 steps).
8. Write accepted rows as replayable 64-bit receipts.
9. Store receipts in the `7! = 5040` slot replay ring.
10. Accept the canonical genesis frame: `0100-03bf-7c00-2b01-2f01-1434-039f-01ff`.
11. Reject malformed, byte-swapped, or anchor-invalid frames.
12. Treat DOM, SVG, JSON Canvas, QR, portal UI, typography, color, and `unicode-bidi` as **projection or reader lenses only**.

### 21. Genesis Fixture

```text
BOOT_ADDRESS = 0x7C00
BOOT_SLOT = 0x7C00 mod 5040 = 1504
GENESIS_LL = 0x01
GENESIS_NN = 0x7C00
C = (0x01 * 0x1337) & 0xFFFF = 0x1337
GENESIS_MM = Delta_{0x1337}(0x7C00) = 0x1434
GENESIS_STEPS = 1
```

### 22. Non-Conformance

An implementation is non-conforming if it:
- Uses `unicode-bidi` as lower validation authority
- Accepts frames without `Q_frame(S) = 0`
- Projects before validation
- Writes receipts before Fano resolution
- Treats glyphs, color, DOM, or portal UI as semantic authority
- Collapses conflicting receipts without an inspectable rule
- Emits facts without corresponding rules or without passing tests
- Skips bitboard validation during derivation
- Uses different bitblip policies than declared
- Projects facts before validation

---

## Part V — Rule-to-Fact Derivation

### 23. Central Derivation Law

> A fact is a grounded rule transition.

A rule says what must be true. A fact says where that rule is grounded in the current system.

```text
RULES.omi = normative invariant space
FACTS.omi = applied runtime/physical/deployment space
```

### 24. The Derivation Chain

Every derivation starts from a `RULES.omi` row:

```text
<omi-address>/<prefix> MUST <invariant-name>
```

Each rule is grounded into a fact:

```text
<omi-address>/<prefix> FACT <applied-fact-name>
```

### 25. The A-List State Transition Form

Every derivation is expressed as an association list:

```lisp
(
  (rule . "<rule-pointer>")
  (modal . "MUST")
  (invariant . "<invariant-name>")
  (state-before . "<input-state>")
  (transition . "<transition-name>")
  (state-after . "<derived-fact-state>")
  (bitboard . "<mask>")
  (bitblip . "<correction-policy>")
  (fact . "<fact-pointer>")
  (test . "<test-file>")
  (projection . "<visible-output>")
)
```

### 26. Bitboard Masks

A bitboard is the fixed-width mask used to extract or compare rule-bearing fields:

| Prefix | Segment Mask |
|---|---|
| `/48` | `[ffff,ffff,ffff,0000,0000,0000,0000,0000]` |
| `/80` | `[ffff,ffff,ffff,ffff,ffff,0000,0000,0000]` |
| `/96` | `[ffff,ffff,ffff,ffff,ffff,ffff,0000,0000]` |
| `/112` | `[ffff,ffff,ffff,ffff,ffff,ffff,ffff,0000]` |
| `/120` | byte-specific narrowing of final segment |
| `/128` | `[ffff,ffff,ffff,ffff,ffff,ffff,ffff,ffff]` |

### 27. Bitblip Policies

A bitblip is a small bit-level deviation from an expected mask:

| Policy | Meaning |
|---|---|
| `accept-exact` | Only exact bitboard match is valid |
| `correct-single` | One-bit deviation may be corrected |
| `evict-single` | One-bit deviation is rejected |
| `correct-up-to-2` | Up to two bit deviations may be repaired |
| `evict-over-2` | More than two bit deviations are rejected |
| `warn-near-miss` | Near miss routes to warning but does not commit |
| `drop-packet` | Kernel/network failure path |
| `skip-replay` | Do not write receipt |
| `route-preset-1` | Visual warning projection |

---

## Part VI — Lower Omicron / Upper Bidi

### 28. The Authority Split

**Lower authority** (structural validity): Omicron anchors `0x03BF`/`0x039F`, `Q_frame(S)`, Delta Law, Fano resolution, replay receipts.

**Upper reader lens** (projection only): `unicode-bidi`, `direction`, CSSOM, DOM, SVG, JSON Canvas, portal UI, colors, glyphs.

**Canonical split:**

> Lower Omicron validates. Upper Bidi reads. Direction is interpretation. Interpretation is rewrite. Projection is never authority.

---

## Part VII — The Open World Portal Model

### 29. Definition

An OMI open-world portal is a normal-looking web application that displays decentralized objects without making the portal itself the authority.

### 30. Consumer Promise

```
One object.
Many portals.
Inspectable history.
Portable context.
Validation before projection.
Agreement without platform lock-in.
```

### 31. Portal Flow

```
consumer action
  → portal UI
  → object projection
  → OMI frame / object address
  → Q_frame validation
  → truth-row resolution
  → receipt write
  → linear replay stream
  → hierarchical containment tree
  → portable carrier output
```

### 32. Two Core Views

Every portal object has two inspectable forms:

| View | Consumer Question | Meaning |
|---|---|---|
| **Linear** | What happened? | Replay / source-object order (`omi → payload → imo`) |
| **Hierarchical** | Where does it belong? | Scope and containment order (`FS → GS → RS → US`) |

Both are projections. Neither validates the object.

### 33. Minimal Portal Canon

> An open-world portal does not own truth. It projects accepted objects. An object is accepted when its frame validates, its truth row resolves, and its receipt can be replayed. A user trusts the portal not because the portal says so, but because the object can be inspected.

---

## Part VIII — Control Characters as Rewrite Operators (merged from root DOCTRINE.md)

### 33. Control Characters

ASCII control characters are rewrite operators. They are not merely non-printing characters. Historically they altered the state of a receiver. OMI restores this interpretation.

In conventional language, control codes were thirty-two non-printing characters. In OMI, control codes become transformation operators rather than textual characters. Control characters are operational geometry.

### 34. Unicode as Rewrite Manifold

Unicode is not merely a character set. Unicode is a rewrite manifold. Planes, surrogates, private-use ranges, direction markers, byte-order marks, and framing operators define lawful transitions between interpretations of the same binary source.

Rows are blocks. Code points are points. Relationships are incidences. The table is no longer merely a lookup structure. It becomes a rewrite structure.

### 35. Downward Execution Flow

When an application verifies a transaction or routes an agent state, it may begin with a Level 5 implementation rule. The runtime compiles that rule downward:

```text
Level 5 implementation rule
→ Level 4 operational address route
→ Level 3 discrete coordinate wheel
→ Level 2 information-preserving rotation
→ Level 1 stream boundary and control surface
→ Level 0 notation-cipher invariant
```

The final check is doctrinal: the underlying binary platform did not need to mutate. The system generated a receipt showing that the interpretive framework transitioned lawfully.

### 36. Upward Invariant Flow

When a node receives a packet, it does not need to trust Level 5 application meaning first. It validates upward:

```text
source identity
→ rotation law
→ projective boundary
→ address route
→ implementation meaning
→ lawful receipt
```

If the structural math holds as a valid projection, the node may issue a lawful receipt. Higher-order meaning is accepted because the lower-level rewrite path is valid.

### 37. The Pipe Stack

The pipe stack follows the same doctrine:

```text
source
→ carrier
→ reconstruction
→ causal proof
→ RS proof
→ acceptance
→ receipt
```

There is no database commit in this chain. The system proves relations and accepts receipts.

---

## The Doctrine in the Shortest Form

> OMI does not store data; it preserves versioned sources of truth as binary rewrite tables, then uses Omicron identity, slash-path routing, BiDi interpretation, and Omi-Nomogram scales to produce lawful receipts.

---

## One-Line Canon

```text
Lisp collapsed program and object. POSIX collapsed storage and communication. OMI collapses representation and interpretation: the same binary surface is both notation and cipher, distinguished only by the active reading, because computation is the rewrite of interpretation, not the mutation of data.
```

---

## The Transition to State 03

From this state — having articulated the invariant laws — I moved to State 03 (The Meaning) to answer: why does this matter? What philosophical lens makes sense of this cosmology?

Continue to `03-FOUNDATIONS.md`.
