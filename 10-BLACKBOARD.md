# State 10 — Blackboard: The Construction Surface

## What This State Is

This state is the transition from "what can be declared" to "how declarations become resolved." After OMI-Lisp establishes the notation surface, the blackboard is the construction surface where declared Relations are canonically cited, classified, reduced, composed, closed, and attributed.

The blackboard is not a data structure. It is a model of deterministic symbolic construction: declarations occupy addressed positions, and resolution is the refinement of those positions through canonical citation, truth gates, minimized relations, combinators, Delta transitions, and closure.

OMI-Lisp is not evaluated like a conventional programming language.

It is resolved.

---

## The Three Components

### Bitboard — The Vertex Field

A bitboard marks occupied address positions. It answers: what exists on the surface?

```
Bitboard = the set of declared Relations at their addresses
```

Each address on the bitboard either contains a Relation or is empty. The bitboard is the occupancy map — it says what is present at each position.

Bitboard resolution is binary: a position is either occupied (a Relation exists there) or vacant (no Relation has been declared). This binary occupancy is the foundation of lazy evaluation: evaluation only proceeds when a position is occupied.

### Bit-blip — The Edge Event

A bit-blip marks a transition between address positions. It answers: what happens on the surface?

```
Bit-blip = a transition event between two bitboard positions
```

Bit-blips are the edges of the blackboard graph. They connect occupied vertices through directed transitions. A bit-blip does not create a new vertex — it records that a transition has occurred between two existing vertices.

Bit-blips are the mechanism by which lazy evaluation progresses. Evaluation of a vertex produces a bit-blip to the next vertex. The chain of bit-blips traces the evaluation path.

### Blackboard — The Resolved Face

The blackboard is the resolved face produced by the relation between bitboards and bit-blips:

```
Blackboard = bitmap projection of vertices + edges
```

A blackboard is not a collection of separate objects. It is a single surface on which vertices and edges have been resolved into a readable bitmap. The blackboard is what projection faces (State 11) read from.

---

## Addressed Identity

The key collapse in the blackboard model is:

```
address = identity
data = addressed identity
```

A Relation does not have an address as a property. A Relation is at an address. The address is its identity. Two Relations at different addresses are different Relations — even if their fields are identical.

This collapse means there is no distinction between "the address of something" and "the thing itself." The blackboard is the set of all addresses and their occupancies. There is no lookup table — the address is the presence.

---

## Lazy Resolution

Resolution on the blackboard proceeds lazily:

1. An OMI-Lisp declaration occupies a vertex on the bitboard
2. When that vertex is read, evaluation checks whether its dependencies are occupied
3. If dependencies are occupied, the vertex produces a value and emits a bit-blip to the next vertex
4. If dependencies are not occupied, evaluation suspends — the vertex remains unevaluated until its dependencies arrive

This is the OMI resolution model: no strict evaluation, no eager computation. Everything proceeds by need, driven by the occupancy of addressed vertices and by the canonical rule surfaces that determine how a declaration may be accepted.

---

## Resolution Pipeline

A declaration does not execute immediately. It enters a deterministic relation pipeline where every stage refines its meaning while preserving canonical addressing and provenance:

```text
Declaration
    ↓
Canonical OMI---IMO Citation
    ↓
Truth Gate
    ↓
Decision Table
    ↓
Wittgenstein Operator Selection
    ↓
Karnaugh Reduction
    ↓
Combinator Construction
    ↓
Delta Transition
    ↓
Blackboard Configuration
    ↓
Blackboard Construction
    ↓
Blackboard Composition
    ↓
Blackboard Closure
    ↓
Difference Resolution
    ↓
Canonical OMI---IMO Notation
    ↓
Canvas Node Attribution
    ↓
Receipt / Attestation
```

This is no longer simply an evaluation pipeline. It is a deterministic symbolic construction pipeline. Every declaration becomes a locally resolvable relation whose provenance remains visible from the original citation through the final accepted attestation.

---

## Canonical Citation

Every declaration first becomes an `OMI---IMO` citation. The citation identifies:

```text
where the declaration exists
which scope contains it
which gauge framed it
which relation it belongs to
```

The citation does not accept the declaration. It gives the declaration immutable identity so that later stages can classify, reduce, compose, and attest the same relation without losing provenance.

---

## Truth Gates and Decision Tables

Truth gates do not compute. They classify.

Each declaration is compared against canonical rule sets stored in the `.omi` truth-gate files:

```text
RULES.omi
FACTS.omi
COMBINATORS.omi
CLOSURES.omi
CONS.omi
```

These files are deterministic decision surfaces rather than executable programs. They organize constitutional cells by:

```text
Question
Algorithm
Citation Slot
Proof Form
```

giving:

```text
8 × 7 × 4 × 2 = 448
```

canonical proof obligations.

Each cell carries a Wittgenstein operator code selected from the gauge family. The gauge pre-header `F0` through `FE` selects the non-closure truth rows, and `FF` seals the tautological canonical closure row. Together they form the sixteen-row local logical surface through which the declaration will be interpreted.

---

## Karnaugh Reduction

Once the operator is known, the declaration becomes a Boolean relation. Decision-table rows become Karnaugh-map regions, and equivalent regions collapse into minimal Boolean forms.

The result is not executable code. It is a minimized logical relation.

This reduction is the bridge between constitutional classification and deterministic construction. It turns the decision-table surface into a smaller relation that can be carried by pure combinators without hidden state.

---

## Combinator and Delta Construction

The minimized relation is transformed into deterministic combinators. These combinators are pure: they carry no hidden state, mutate no blackboard position, and describe only lawful structural transitions.

The Delta Law then produces deterministic movement between accepted states. Delta does not invent new meaning. It transports already minimized relations through canonical transitions.

In blackboard terms:

```text
minimized relation
    ↓
pure combinator
    ↓
Delta transition
    ↓
accepted state movement
```

---

## Blackboard Construction Stages

The blackboard is the canonical construction surface. Each accepted combinator contributes to four successive stages:

```text
Configuration
    ↓
Construction
    ↓
Composition
    ↓
Closure
```

Configuration places the relation in its addressed frame. Construction materializes the lawful transition. Composition connects that transition to adjacent accepted relations. Closure seals the resulting surface as a canonical state.

Difference is preserved throughout this process. It is not discarded as noise or treated as a failed comparison.

---

## Difference Resolution

Difference is constructive structure.

Using the factorization laws:

```text
a^2 - b^2
```

and:

```text
a^3 ± b^3
```

relations are separated into distinguishable components before being recomposed. This produces the six factor lanes represented by the gauge colors. Difference therefore becomes part of the canonical geometry rather than merely a comparison operation.

---

## Canonical Notation and Canvas Attribution

After closure, the declaration exists as canonical notation. It possesses an `OMI---IMO` citation together with its attributed relation frame:

```text
o---o/---/?---@---@
```

The notation records both identity and structural context.

The notation projects naturally onto the canvas:

- Nodes represent cited `OMI---IMO` relations
- Node text carries the attributed relation frame
- Edges describe constitutional transitions
- Colors describe gauge factor lanes
- Node dimensions describe encoding resolution and data span

The canvas is therefore not merely a diagram. It is a visual projection of canonical symbolic structure.

---

## Receipt and Attestation

The final output is richer than a receipt alone:

```text
canonical OMI---IMO citation
annotated OMI relation frame
Wittgenstein operator
decision-table reduction
Karnaugh reduction
deterministic combinator
Delta transition
blackboard construction state
canvas attribution
receipt
attestation
```

A receipt records acceptance. An attestation records how the accepted relation was derived.

---

## Geometric Interpretation

The pipeline can be understood as a deterministic observer operating over quaternion-like quartets arranged on a circular slide rule.

Using Polybius ordering over tetrahedral diagonals, declarations are injected into the blackboard where they undergo:

```text
configuration
construction
composition
closure
difference
```

through local combinatorics in the Y and Z dimensions.

The resulting notation constructs `OMI---IMO` logic diagrams analogous in spirit to Coxeter-Dynkin diagrams, except that the graph is organized around canonical citation, deterministic combinators, and attributable relation frames rather than purely geometric incidence.

---

## Blackboard as Concurrent Surface

Because blackboard positions are addresses, and addresses are identity, multiple observers can read the same blackboard position without coordination. The blackboard is a concurrent surface — not by locking, but by the mathematical property that identity does not require synchronization.

Two observers reading the same address see the same Relation, because the address determines the Relation. There is no write conflict because Relations are not mutated — they are declared at addresses and observed through projections.

---

## Relation to the Rest of the Canon

```
OMI-Lisp declarations (State 09)
    ↓ become canonical citations on
Blackboard (State 10)
    ↓ are classified and reduced through
Truth gates, decision tables, and Karnaugh regions
    ↓ are moved through
Combinators and Delta transitions
    ↓ are projected through
Projection Faces (State 11)
    ↓ are oriented by
Gauge Interrupts (State 12)
    ↓ are rendered as
Surface Applications (State 13)
```

The blackboard is the hinge between declaration and projection. Without it, OMI-Lisp would be a notation without a semantics. With it, every declaration has a deterministic construction path through citation, classification, reduction, transition, closure, attribution, receipt, and attestation.

---

## Doctrine Sentence

> The blackboard is not a database. It is an addressed construction surface where declarations become cited, reduced, composed, closed, attributed, and attested as deterministic symbolic relations.
