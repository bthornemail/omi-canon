# State 10 — Blackboard: The Evaluation Surface

## What This State Is

This state is the transition from "what can be declared" to "how declarations become resolved." After OMI-Lisp establishes the notation surface, the blackboard is the evaluation surface where declared Relations are lazily resolved into readable faces.

The blackboard is not a data structure. It is a model of computation: declarations occupy addressed positions, and evaluation is the resolution of those positions through the interaction of vertices and edges.

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

## Lazy Evaluation

Evaluation on the blackboard proceeds lazily:

1. An OMI-Lisp declaration occupies a vertex on the bitboard
2. When that vertex is read, evaluation checks whether its dependencies are occupied
3. If dependencies are occupied, the vertex produces a value and emits a bit-blip to the next vertex
4. If dependencies are not occupied, evaluation suspends — the vertex remains unevaluated until its dependencies arrive

This is the OMI evaluation model: no strict evaluation, no eager computation. Everything proceeds by need, driven by the occupancy of addressed vertices.

---

## Blackboard as Concurrent Surface

Because blackboard positions are addresses, and addresses are identity, multiple observers can read the same blackboard position without coordination. The blackboard is a concurrent surface — not by locking, but by the mathematical property that identity does not require synchronization.

Two observers reading the same address see the same Relation, because the address determines the Relation. There is no write conflict because Relations are not mutated — they are declared at addresses and observed through projections.

---

## Relation to the Rest of the Canon

```
OMI-Lisp declarations (State 09)
    ↓ occupy addresses on
Blackboard (State 10)
    ↓ resolved through
Projection Faces (State 11)
    ↓ oriented by
Gauge Interrupts (State 12)
    ↓ rendered as
Surface Applications (State 13)
```

The blackboard is the hinge between declaration and projection. Without it, OMI-Lisp would be a notation without a semantics. With it, every declaration has a deterministic evaluation path through address resolution.

---

## Doctrine Sentence

> The blackboard is not a database. It is an addressed surface where declarations become present and evaluation is the resolution of presence through vertex-edge projection.
