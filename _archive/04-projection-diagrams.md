<!-- Extracted from dev-docs/chat about model.md -- conversation turn 2026-07-09 11:03 -->

# Projection Diagrams in OMI

## 1. Purpose

OMI should use **Projection Diagrams** as the declaration-facing term for bounded visual or symbolic outputs.

This is better than making “Blackboard Architecture,” “Canvas,” or “Surface” the main canon term.

The cleaner split is:

```text
Blackboard Pattern:
 behavioral analogy for discovery

Omi-Canvas:
 implementation/workspace surface

Projection Diagram:
 declared finite-state view in OMI-Lisp

Application:
 outside OMI
```

A Projection Diagram does not command the application. It describes a bounded state, transition, or relation view that can be inspected, interpreted, or rendered downstream.

---

## 2. Why Projection Diagram Is Better

A state diagram represents finite behavior by showing states and transitions between them.

That matches OMI-Lisp better than “surface” or “canvas” because OMI-Lisp declarations are not merely drawings. They declare structured relations.

The finite automaton form is:

```text
(Q, Σ, Z, δ, q0, F)
```

where:

```text
Q:
 finite states

Σ:
 input symbols

Z:
 output symbols

δ:
 transition function

q0:
 start state

F:
 accepting/final states
```

In OMI vocabulary:

```text
Q:
 bounded address states

Σ:
 declared input/gauge symbols

Z:
 projected output symbols

δ:
 Delta / transition / resolver function

q0:
 NULL origin or selected start address

F:
 closure, final, accepted, inert, or projected states
```

So Projection Diagrams are the right level: they express bounded computational behavior without becoming application authority.

---

## 3. Pattern vs Diagram vs Architecture

OMI should separate these terms carefully.

```text
Pattern:
 describes behavior

Diagram:
 declares a bounded view of behavior

Architecture:
 describes implementation structure
```

So:

```text
Blackboard Pattern:
 independent contributors may post partial annotations to a shared discovery context

Projection Diagram:
 OMI-Lisp declaration of states, transitions, citations, and projections

Blackboard Architecture:
 optional downstream implementation choice, not OMI canon
```

The corrected canon line:

```text
OMI may use a blackboard-like pattern for discovery, but OMI-Lisp declares Projection Diagrams.
```

---

## 4. OMI-Lisp Role

OMI-Lisp should not be framed as the authority layer.

OMI-Lisp is the declaration layer.

It can declare:

```text
notation
addresses
states
transitions
gauge symbols
citation triples
projection diagrams
```

But it does not decide application behavior.

So the flow is:

```text
OMI-Lisp declares Projection Diagram
→ Omicron frames it
→ Tetragrammatron governs closure
→ Metatron interpolates compatible relations
→ Projection Diagram exposes bounded result
→ application remains outside OMI
```

---

## 5. Projection Diagram vs Canvas Projection

The distinction can be:

```text
Projection Diagram:
 declared finite-state relation view

Canvas Projection:
 rendered or inspectable implementation surface
```

So the hierarchy is:

```text
OMI-Lisp declaration
 → Projection Diagram

Omi-Canvas implementation
 → Canvas Projection
```

A Projection Diagram can be rendered on Omi-Canvas, but it is not identical to the canvas.

```text
Projection Diagram:
 what is declared

Canvas Projection:
 where/how it is surfaced
```

This avoids overbinding OMI canon to one implementation.

---

## 6. Projection Diagram and Latin Squares

The Latin-square/quasigroup idea fits Projection Diagrams because it gives a finite reversible transition table.

A Latin square can be represented by triples:

```text
(row, column, symbol)
```

For OMI:

```text
(attestation, attribution, discovered-point)
```

The resolver law is:

```text
any two coordinates determine the third
```

This can be declared as a Projection Diagram:

```text
states:
 citation coordinates

inputs:
 known coordinate pairs

transition/resolution:
 recover missing coordinate

outputs:
 discovered point or unresolved boundary
```

The proof-source excerpt records the equivalence between Latin squares and finite quasigroups: a quasigroup table becomes a Latin square when row and column headers are removed, and a Latin square can be bordered to form a quasigroup table. filecite turn40file0

So the Latin square is not the application. It is the declared resolver diagram.

---

## 7. Projection Diagram and Polybius

The Polybius gauge is the local 4×4 Projection Diagram already present in OMI.

```text
0 1 2 3
4 5 6 7
8 9 A B
C D E F
```

With:

```text
row(x) = x / 4
col(x) = x mod 4
```

and diagonals:

```text
D+ = {0,5,A,F}
D- = {3,6,9,C}
```

The proof book records that the Polybius rail proves:

```text
XOR(D+) = 0
XOR(D-) = 0
SUM(D+) = 0x1E
SUM(D-) = 0x1E
SUM(D+) + SUM(D-) = 0x3C
SUM(0..F) = 0x78
15 * 16 = 240
```

These are Polybius gauge facts, separate from the Delta16 exact-period constants. filecite turn39file0

So:

```text
Polybius Square:
 local Projection Diagram

Latin Square:
 generalized Projection Diagram

Quasigroup:
 algebraic resolver behind the diagram
```

---

## 8. Projection Diagram and Blackboard Pattern

The blackboard idea is useful only as a pattern.

It says:

```text
multiple sources can contribute partial structure
a shared workspace accumulates partial solutions
a control rule decides what contribution fits next
```

For OMI, this becomes:

```text
multiple deterministic resolvers may contribute annotations
the Projection Diagram records bounded states and transitions
Tetragrammatron governs closure
```

But OMI does not have to claim a full Blackboard Architecture.

Correct phrasing:

```text
OMI uses a blackboard-like pattern of contribution and discovery.

OMI-Lisp declares Projection Diagrams.

The implementation may render those diagrams on Omi-Canvas.
```

---

## 9. Projection Diagram Strengths

Projection Diagrams can still be classified by force.

### Impotent Projection Diagram

```text
inert
inspection-only
cannot instantiate application action
cannot command runtime behavior outside OMI
```

Example:

```text
NULL Byte Ring closure diagram
```

Based on:

```lisp
((0x00 . 0x20)
 (0x20 . 0x7F)
 (0x7F . 0xFF)
 (0xFF . 0x00))
```

The proof book records its XOR witnesses and closure:

```text
20 XOR 5F XOR 80 XOR FF = 00
```

and the general finite closed-path law. filecite turn39file0

### Innocuous Projection Diagram

```text
informative
harmless
may guide discovery
may support collaboration
still cannot command application behavior
```

Example:

```text
Gnomic Gauge OMI-Ring
FΔ 00 1C 1D 1E 1F 20 FΔ
```

It may expose structured relation without application force.

The distinction:

```text
Impotent:
 cannot act

Innocuous:
 may inform, but must not command
```

---

## 10. Proposed OMI-Lisp Declaration Shape

A Projection Diagram declaration could look conceptually like:

```lisp
(projection-diagram
 :name polybius-gauge
 :states (0 1 2 3 4 5 6 7 8 9 A B C D E F)
 :inputs (row column)
 :transition row-column-resolve
 :diagonals
 ((D+ (0 5 A F))
 (D- (3 6 9 C)))
 :witnesses
 ((sum-D+ 0x1E)
 (sum-D- 0x1E)
 (sum-diag 0x3C)
 (sum-wheel 0x78))
 :projection innocuous)
```

A Latin-square resolver diagram could be:

```lisp
(projection-diagram
 :name citation-latin-resolver
 :states citation-points
 :coordinates
 (attestation attribution discovered-point)
 :law any-two-determine-third
 :projection innocuous)
```

A Null Ring closure diagram could be:

```lisp
(projection-diagram
 :name null-byte-ring
 :states (0x00 0x20 0x7F 0xFF)
 :edges
 ((0x00 0x20)
 (0x20 0x7F)
 (0x7F 0xFF)
 (0xFF 0x00))
 :witnesses
 (0x20 0x5F 0x80 0xFF)
 :closure xor-zero
 :projection impotent)
```

These are not final syntax requirements. They show the intended role:

```text
OMI-Lisp declares diagrams.
The runtime resolves them.
The canvas may render them.
Application remains downstream.
```

---

## 11. Term Table

| Term | Layer | Meaning |
|---|---:|---|
| Blackboard Pattern | Conceptual behavior | Discovery by partial contributions |
| Blackboard Architecture | Implementation | Optional, not canon |
| OMI-Lisp | Declaration | Declares notation and Projection Diagrams |
| Projection Diagram | OMI declaration object | Bounded finite state/relation view |
| Omi-Canvas | Implementation surface | Renders or inspects diagrams |
| Canvas Projection | Runtime/rendered surface | Concrete view of a Projection Diagram |
| Impotent Projection Diagram | Safe projection | Inert, no operative force |
| Innocuous Projection Diagram | Safe projection | Informative but non-commanding |
| Application | Downstream | Outside OMI authority |

---

## 12. Canon Statement

OMI does not need to claim Blackboard Architecture.

OMI may use the Blackboard Pattern as a behavioral analogy for discovery: partial resolvers contribute compatible annotations to a bounded shared context.

In OMI-Lisp, the correct declaration object is a Projection Diagram.

A Projection Diagram is a finite declared view of states, transitions, citations, gauges, and closure witnesses.

A Projection Diagram may later be rendered on Omi-Canvas as a Canvas Projection, but the diagram is the declaration and the canvas is only the surface.

Projection Diagrams may be Impotent when inert or Innocuous when informative but harmless. Neither kind carries application authority.

OMI declares, defines, discovers, and projects. It does not decide application behavior.