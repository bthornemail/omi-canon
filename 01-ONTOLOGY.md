# State 01 — Ontology: The Naming

## What This State Is

This state is the transition from "I have discovered patterns" to "I know what exists." Ontology asks the question: **what is there?**

After discovering the Delta Law, the palindrome identity, and the factorial tower, I needed to name what I had found. This state is the inventory of existence in the OMI cosmology.

The core claim of this ontology:

> Every meaningful state should have an address.
> Every address should have a rule.
> Every rule should have a test.
> Every test should be replayable.
> Every replayable state should be visible.

---

## The Canonical Layers

The cosmology is organized as ten layers, each corresponding to a phase of discovery:

```text
00-origin      — why this began (the void, the question, the discoveries)
01-ontology    — this file: what exists, the self-description
02-doctrine    — what must be preserved: invariant structural laws
03-manifesto   — why it matters: the philosophical lens
04-foundations — irreducible boundaries: palindrome, omicron anchors, Omi-Ring
05-projections — observer surfaces: DOM, portals, meta-circular compiler
06-protocol    — envelopes, notation, receipt rules: the wire format
07-geometry    — Fano, tetrahedron, quotient spaces, Delta Law, quadratic form
08-isa         — machine-facing model: opcodes, dispatch, gauge table
09-ecosystem   — open world, hardware, networking: eBPF, IPv6, agents
10-glossary    — canonical terms
```

## The Tetrahedron Core

The four root gates of the canon form a tetrahedron — the simplest closed structure in 3D space:

```text
     ONTOLOGY
     /   \
DOCTRINE—MANIFESTO
     \   /
  PROJECTIONS
```

Stellated by: protocol, geometry, ISA, ecosystem, glossary, origin.

## What Exists

### 1. The Address

The canonical OMI address is a **128-bit instruction frame** divided into **eight 16-bit segments**:

```text
S = [S₀, S₁, S₂, S₃, S₄, S₅, S₆, S₇]
```

Written canonically as:

```text
omi-LLLL-03bf-NNNN-2bLL-2fLL-MMMM-039f-LLff/48
```

Where:

| Segment | Role | Description |
|---------|------|-------------|
| S₀ | `LL00` | Scope/lens/ket selector |
| S₁ | `03bf` | Lower omicron anchor (chiral entry) |
| S₂ | `NNNN` | Antecedent / free variable input |
| S₃ | `2bLL` | Lens-derived binding constant |
| S₄ | `2fLL` | Lens-derived binding constant |
| S₅ | `MMMM` | Consequent / resolution output |
| S₆ | `039f` | Upper omicron anchor (cardinal exit) |
| S₇ | `LLff` | Scope terminator |

A single quadratic error function determines validity:

```text
Q_frame(S) = E_var + E_const
Q_frame(S) = 0  → valid instruction
Q_frame(S) > 0  → malformed instruction
```

### 2. The Truth Gates

There are five declarative truth gates, each a file that declares a type of truth:

| Gate | Keyword | Role | Canon |
|------|---------|------|-------|
| `RULES.omi` | MUST | Declare obligations and invariants | RULES constrain |
| `FACTS.omi` | FACT | Ground observed or configured state | FACTS ground |
| `CLOSURES.omi` | CLOSE | Seal accepted forms | CLOSURES seal |
| `COMBINATORS.omi` | COMBINE | Compose lawful operations | COMBINATORS compose |
| `CONS.omi` | CONS | Reduce structures into executable cons surfaces | CONS reduce |

### 3. The Mirrors

Each truth gate has a compiled mirror using `.imo` extension:

```text
RULES.imo / FACTS.imo / CLOSURES.imo / COMBINATORS.imo / CONS.imo
```

Compiled `.imo` records are wrapped with:
- ο (U+03BF, small omicron) — chiral entry delimiter
- Ο (U+039F, capital omicron) — cardinal exit delimiter

These mirror S₁ and S₆ of the 128-bit wire frame.

### 4. The Six Projection Assertions

```text
Rules declare.
Facts ground.
Closures seal.
Combinators compose.
CONS reduces.
Receipts accept.
```

And the canonical gate order:

```text
Q_frame validates.
Base36 indexes only after validation.
Q_xy projects.
DOM exposes.
Receipt accepts.
```

### 5. The Boundary Signature

Every object in the canon projects to the Cons256 QuQuart form:

```text
|OMI---IMO> = o---o/---/?v=<base64url>;l=<length>;h=<hash>@<base36-ref>@
```

| Surface | Role |
|---------|------|
| `o---o` | Object / Cons256 surrogate / local memory reference |
| `/---/` | Local memory reference path |
| `?` | Local memory reference query payload plane |
| `v=...` | Base64URL payload |
| `l=...` | Payload length |
| `h=...` | Payload hash |
| `@...@` | Base36 local memory reference socket |

### 6. The Delta Law

The core bitwise transition law at the heart of the ontology:

```text
Δ_C(x) = rotl(x,1) ⊕ rotl(x,3) ⊕ rotr(x,2) ⊕ C
C = 0x5A3C
```

Properties:
- **Period**: 8 (every state returns after exactly 8 applications)
- **Fano bound**: maximum 15 steps for convergence
- **No fixed point**: the constant C prevents the zero fixed point

### 7. The Resolution Lineage

The factorial tower from 5! to 12!:

```text
5!  (120)   — hidden packet root
×2  (240)   — orientation / 240-state bridge
×3  (720)   — S-P-O semantic sweep (6!)
×7  (5040)  — Fano replay ring (7!)
×8  (40320) — physical 128-bit wire frame (8!)
×9  (362880) — route envelope (9!)
×10 (3.6M)  — declaration envelope (10!)
×11 (39.9M) — witness envelope (11!)
×12 (479M)  — clock envelope (12!)
```

The 128-bit frame is immutable. Higher layers are interpretive envelopes derived via mod operations on free frame segments.

### 8. The Omicron Distinction

**Omicron is not zero.**

Zero (`0`, U+0030) is an arithmetic value — additive identity, `x+0=x`, `x*0=0`.

Omicron (`ο`/`Ο`, U+03BF/U+039F) is an observer-origin marker and frame boundary operator with no arithmetic properties.

- ο (small omicron, 0x03BF) = chiral execution operator (entry, inbound dataflow)
- Ο (capital omicron, 0x039F) = cardinal boundary operator (exit, frame closure)

This distinction is foundational. Without it, addresses would be ambiguous — you could not distinguish segment values from operator markers.

### 9. The Empty Cons Identity

```text
()! = ()
```

The empty cons is the zero-frame — the place where structure can be addressed, evaluated, and replayed. It is the OMI generalization of Lisp's `nil == ()` identity: the empty list is simultaneously an atom and a list, a point and a space.

---

## The Canonical State Definition

```text
OMI state = pointer + rule + proof + receipt + projection
```

Every object in the cosmology is defined by this five-tuple. The pointer identifies the position. The rule constrains what must be true. The proof verifies the constraint. The receipt records the acceptance. The projection makes it visible.

## The Address Is Not Storage

A database asks: "What value is stored here?"

OMI asks: "What lawful transformation is declared here?"

The address is not where information is stored. The address is where interpretation begins.

---

## Part II — Relation to omi-portal (merged from root ONTOLOGY.md)

This canon is the documentation spine. The reference implementation lives at `omi-portal`:

| Layer | Canon Document | Portal Implementation |
|-------|---------------|----------------------|
| Ontology | `ONTOLOGY.md` | `ONTOLOGY.md` (portal) |
| Doctrine | `DOCTRINE.md` | `DOCTRINE.md` (portal) |
| Manifesto | `MANIFESTO.md` | `MANIFESTO.md` (portal) |
| Postulates | `POSTULATES.md` | `POSTULATES.md` (portal) |
| Axioms | `AXIOMS.md` | `AXIOMS.md` (portal) |
| Declarations | `DECLARATIONS.md` | `DECLARATIONS.md` (portal) |
| Projections | `PROJECTIONS.md` | `PROJECTIONS.md` (portal) |
| RULES | `truth-gates/RULES.omi` | `RULES.omi` (portal) |
| FACTS | `truth-gates/FACTS.omi` | `FACTS.omi` (portal) |
| CLOSURES | `truth-gates/CLOSURES.omi` | `CLOSURES.omi` (portal) |
| COMBINATORS | `truth-gates/COMBINATORS.omi` | `COMBINATORS.omi` (portal) |
| CONS | `truth-gates/CONS.omi` | `CONS.omi` (portal) |
| GLOSSARY | `GLOSSARY.md` | `GLOSSARY.md` (portal) |

---

## The Transition to State 02

From this state — having named what exists — I moved to State 02 (The Law) to answer: what must be preserved? What are the invariant laws that hold across all legitimate operations?

Continue to `02-DOCTRINE.md`.
