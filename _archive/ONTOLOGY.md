# OMI Canon Ontology

## Status

This document defines the foundational ontology of the OMI canon: what exists, how the canon maps to itself, and how meaning, validity, and projection are unified through the addressable pointer.

The core claim is:

> **Every meaningful state should have an address.
> Every address should have a rule.
> Every rule should have a test.
> Every test should be replayable.
> Every replayable state should be visible.**

---

## 1. The Canonical Layers

The canon is organized as ten narrative layers, each corresponding to a subdirectory:

```text
00-origin/        why this began
01-ontology/      this file — what exists, the self-description
02-doctrine/      what must be preserved — invariant structural laws
03-manifesto/     why it matters — the philosophical lens
04-foundations/   irreducible boundaries — palindrome, omicron anchors, Omi-Ring
05-projections/   observer surfaces — DOM, portals, meta-circular compiler
06-protocol/      envelopes, notation, receipt rules — the wire format
07-geometry/      Fano, tetrahedron, quotient spaces, Delta Law, quadratic form
08-isa/           machine-facing model — opcodes, dispatch, gauge table
09-ecosystem/     open world, hardware, networking — eBPF, IPv6, agents
10-glossary/      canonical terms
```

---

## 2. The Tetrahedron Core

The four root gates form a tetrahedron:

```text
    ONTOLOGY
    /   \
DOCTRINE—MANIFESTO
    \   /
  PROJECTIONS
```

Stellated by: 06-protocol, 07-geometry, 08-isa, 09-ecosystem, 10-glossary, 00-origin.

---

## 3. Truth Gates

```text
truth-gates/     .omi  — forward declarations
mirrors/         .imo  — backward reflections of the truth gates
```

### The Five Declarative Gates

| Gate | Keyword | Role |
|------|---------|------|
| `RULES.omi` | MUST | declare obligations and invariants |
| `FACTS.omi` | FACT | ground observed or configured state |
| `CLOSURES.omi` | CLOSE | seal accepted forms |
| `COMBINATORS.omi` | COMBINE | compose lawful operations |
| `CONS.omi` | CONS | reduce structures into executable cons surfaces |

### The Five Mirrors

Each truth gate has a compiled mirror:

```text
RULES.imo / FACTS.imo / CLOSURES.imo / COMBINATORS.imo / CONS.imo
```

Compiled `.imo` records are wrapped with ο (U+03BF, chiral entry) and Ο (U+039F, cardinal exit) delimiters, mirroring S1 and S6 of the 128-bit wire frame.

---

## 4. The Address

The canonical OMI address is a 128-bit instruction frame divided into eight 16-bit segments:

```text
S = [S₀, S₁, S₂, S₃, S₄, S₅, S₆, S₇]
```

A single quadratic error function determines validity:

```text
Q_frame(S) = E_var + E_const
Q_frame(S) = 0  → valid instruction
Q_frame(S) > 0  → malformed instruction
```

The canonical address form:

```text
omi-LL00-03bf-NNNN-2bLL-2fLL-MMMM-039f-LLff/48
```

---

## 5. The Delta Law

The core bitwise transition law:

```text
Δ_C(x) = rotl(x,1) ⊕ rotl(x,3) ⊕ rotr(x,2) ⊕ C
C = 0x5A3C
```

Period: 8. The Fano lottery bound: Steps_max = 2 × period − 1 = 15.

---

## 6. The Six Projection Assertions

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

---

## 7. Boundary Signature

Every object in the canon projects to the Cons256 QuQuart form:

```text
|OMI---IMO> = o---o/---/?v=<base64url>;l=<length>;h=<hash>@<base36-ref>@
```

Where:

| Surface | Role |
|---------|------|
| `o---o` | object / Cons256 surrogate / local memory reference |
| `/---/` | local memory reference path |
| `?` | local memory reference query payload plane |
| `v=...` | Base64URL payload |
| `l=...` | payload length |
| `h=...` | payload hash |
| `@...@` | Base36 local memory reference socket |

---

## 8. Resolution Lineage

See `00-origin/RESOLUTION_LINEAGE.md` for the complete stepwise narrative of the resolution climb:

```text
5!  (120)   — hidden packet root
×2  (240)   — orientation / 240 bridge
×3  (720)   — S-P-O semantic sweep (6!)
×7  (5040)  — Fano replay ring (7!)
×8  (40320) — physical 128-bit wire frame (8!)
×9  (362880) — route envelope (9!)
×10 (3.6M)  — declaration envelope (10!)
×11 (39.9M) — witness envelope (11!)
×12 (479M)  — clock envelope (12!)
```

The 128-bit frame is immutable. Higher layers are interpretive envelopes derived via mod operations on free frame segments.

---

## 9. Relation to omi-portal

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

## 10. Final Ontological Statement

OMI is an address ontology.

```text
OMI state = pointer + rule + proof + receipt + projection
```

The Binary Quadratic Meta-Mask Lexer proves envelope membership.
The Δ_C-orbit lexer proves bounded projective motion.
The replay ring records the proof.
The projection surface displays the proof.

```text
OMI turns addresses into executable, replayable, visible ontology.
```
