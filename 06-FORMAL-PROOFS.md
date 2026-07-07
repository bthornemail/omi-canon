# State 06 — Formal Proofs: What Has Been Verified

## What This State Is

This state is the transition from "how the kernel moves" to "what has actually been proven." After defining the pure algorithms, the next question is which of those algorithms have been formally verified — and through which proof system.

The canon does not claim that every algorithm is proven. It records which algorithms have been verified, against which specification, and which remain as conjectures.

---

## The Proof Stack

Proofs in OMI are organized in layers, each corresponding to a canon state:

```
Atomic Kernel proofs      (State 04)
    ↓
Algorithm proofs          (State 05)
    ↓
ISA proofs                (State 07)
    ↓
Protocol proofs           (State 08)
    ↓
Projection proofs         (State 11)
```

The proof systems used are:

- **Coq** (via omi-axioms) — for kernel, algorithmic, and type-theoretic proofs
- **brute-force enumeration** — for bounded state-space proofs (e.g., Delta Law period-8)
- **algebraic derivation** — for structural identities (e.g., 240 bridge, factorial identities)
- **constitutional matrix** — for cross-cutting verification across the entire canon

---

## What Has Been Proved

### 1. Delta Law Period-8

```
∀ x ∈ [0, 65535]: Δ⁸(x) = x
```

Proof method: brute-force enumeration over all 65536 states. Verified by the ISA test suite and independently by the Coq proof stack.

### 2. Bounded Fano Window

```
∀ convergent pair (NN, MM): resolution requires ≤ 15 iterations
```

Proof method: algebraic derivation from the Delta Law period-8 property combined with Fano plane incidence structure. The 15-step bound follows from 2×period − 1.

### 3. Q_xy Positive Definiteness

```
∀ (x, y) ≠ (0, 0): Q_xy(x, y) > 0
```

Proof method: the matrix [[60, 8], [8, 4]] has determinant 176 > 0, establishing positive definiteness via Sylvester's criterion.

### 4. Frame Validation Completeness

```
Q_frame(S) = 0 iff all segments satisfy their segment-specific invariants
```

Proof method: algebraic decomposition. Each segment contributes an independently verifiable term to Q_frame. Completeness follows from the quadratic form's separation into variable and constant components.

### 5. 240 Bridge Identity

```
2 × 5! = 15 × 16 = 240
```

Proof method: direct arithmetic. The significance is not in the computation but in the structural mapping it enables between the five-fold packet root and the four-fold selector surface.

---

## What Is Being Proved

The following proofs are in progress in the `omi-axioms` repository:

- Atomic Kernel: Null, Bit, Pair, Relation consistency
- Delta orbit theory: full characterization of all orbits under Δ_C
- Functorial semantics: projection as functor from Relation to interpretation category
- Coalgebraic bisimulation: receipt identity under observed equivalence
- OMI bialgebra: composition of algebraic and coalgebraic structures
- Verified execution: ISA opcodes satisfy their specification

---

## What Has Not Been Proved

The canon records what it does not yet claim:

- Deterministic termination for all compositions of the seven canonical operations
- Correctness of the distributed open-world protocol under arbitrary network partitions
- Bijectivity of the gauge selection function for all possible Address × Frame inputs

These are open questions. The canon tracks their status.

---

## The Constitutional Matrix

The constitutional matrix (State 19) provides a cross-cutting verification structure. It defines 112 proof cells — 8 invariants × 7 algorithms × 2 proof forms (constructive and falsification). Every claim in the canon must satisfy at least one cell.

The formal proofs in this state supply the constructive entries for the constitutional matrix. Where a formal proof does not yet exist, the cell is marked as conjectural.

---

## Doctrine Sentence

> A claim is not part of the canon until it has been verified by at least one proof system. A claim that cannot be verified is a speculation. The canon records speculations as open problems, not as truths.
