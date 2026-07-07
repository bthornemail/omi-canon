# 448 Proofs Matrix — Constitutional Verification Grid

## 8 × 7 × 4 × 2 = 448 Proof Cells

This directory formalizes the OMI constitution as a verification grid. Every invariant claim of the system must answer eight questions, be enforceable through seven algorithms, be positioned in four citation slots, and be provable in two forms.

---

## The Formula

```text
8  invariant questions  define what must remain true.
7  algorithms           define how the system enforces those truths.
4  citation slots       frame each claim in relational space.
2  proof forms          ensure every claim is both constructible and falsifiable.

8 × 7 × 4 × 2 = 448 proof cells
```

---

## Structure

| Directory | Contents |
|-----------|----------|
| `Q1-source-of-truth.md` through `Q8-open-meaning-closed-law.md` | One document per invariant question; each contains the 7 × 4 × 2 = 56 proof cells for that question |
| `algorithms/A1-transition.md` through `A7-branch-reconciliation.md` | One document per algorithm; each contains the 8 × 4 × 2 = 64 proof cells for that algorithm |
| `proofs/` | Coq formalization files that implement the proof obligations |

---

## The 8 Invariant Questions

Each question defines a structural invariant that the system must preserve. The answers are not negotiable — they are constitutional constraints.

| # | Question | Core Principle |
|---|----------|---------------|
| Q1 | What is the source of truth? | The algorithm is the source of truth |
| Q2 | How does the system move? | A bounded deterministic transition law moves the system |
| Q3 | How does it distinguish payload from control? | A canonical control plane separates structural roles from payload |
| Q4 | How does it preserve meaning across projections? | Artifacts are projections of invariant state, not authorities |
| Q5 | How does it allow intervention without losing replay? | ESC provides bounded interrupt with deterministic return |
| Q6 | How does it permit collaboration without hidden authority? | Agents collaborate through proposals, receipts, and deferred commit |
| Q7 | How does it branch and return without fragmentation? | Canonical trace, branch state, and shared deltas are distinct and returnable |
| Q8 | How does it stay open in meaning while closed in law? | Closure belongs to law; openness belongs to interpretation |

---

## The 7 Algorithms

Each algorithm defines a concrete enforcement mechanism. Every algorithm must provide a constructive proof and a falsification proof for each of the 8 invariant questions, in all 4 citation slots.

| # | Algorithm | Enforcement Domain |
|---|-----------|-------------------|
| A1 | Transition | Advances canonical state under deterministic law |
| A2 | Control-Plane | Separates structural channels/lanes from payload |
| A3 | Projection | Derives views from canonical state without creating authority |
| A4 | Escape | Opens bounded interrupt scope and guarantees return |
| A5 | Partition & Chirality (Fano Selection) | Produces balanced partitions and deterministic orientation |
| A6 | Proposal/Receipt | Converts interventions into inspectable deferred artifacts |
| A7 | Branch/Reconciliation | Preserves canonical reference with persistent divergence + return |

---

## The 4 Citation Slots

Each claim occupies a 4-dimensional citation space within the JSON Canvas edge encoding:

| Slot | Edge Side | Address Component | Role |
|------|-----------|-------------------|------|
| **C1** — Previous Group | `fromSide: top` | `omi---imo` | The group from which the claim descends |
| **C2** — Previous Relation | `fromSide: left` | `o---o/---/?---?@---@` | The relation frame that produced the claim |
| **C3** — Post Group | `toSide: right` | `omi---imo` | The group toward which the claim ascends |
| **C4** — Post Relation | `toSide: bottom` | `o---o/---/?---?@---@` | The relation frame consumed by the claim |

Every constitutional cell is addressable as:

```
Q{n}-A{m}-C{x}-C{y}-{constructive|falsification}
```

---

## The 2 Proof Forms

Every cell in the 8×7×4 grid must provide:

| Proof Form | Question It Answers |
|------------|---------------------|
| **Constructive** | How is this property established? What mechanism builds the guarantee? |
| **Falsification** | How is violation detected or rejected? What test breaks a false claim? |

A claim that cannot be constructed is not implementable. A claim that cannot be falsified is not testable. Both forms are required.

---

## The Wittgenstein Operator Alphabet

Every constitutional cell is labeled with one of the 16 Wittgenstein truth-functions, encoding the local truth relationship over its 4 citation slots:

```
0:  ⊥  FFFF    — contradiction (no slot holds)
1:  NOR  FFFT   — joint denial
2:  ↚    FFTF   — converse nonimplication
3:  ¬p   FFTT   — negation of C1
4:  ↛    FTFF   — material nonimplication
5:  ¬q   FTFT   — negation of C2
6:  XOR  FTTF   — exclusive disjunction
7:  NAND FTTT   — not all slots hold
8:  AND  TFFF   — conjunction (all slots hold)
9:  XNOR TFFT   — equivalence
10: q   TFTF    — projection of C2
11: p→q TFTT    — implication
12: p   TTFF    — projection of C1
13: p←q TTFT    — converse implication
14: OR  TTTF    — disjunction
15: ⊤   TTTT    — tautology (any slot holds)
```

The operator is embedded in the node relation frame as:

```
o---o/FS:wittgenstein/GS:truth-table/RS:{00-15}/US:{operator}?truth@node@frame
```

---

## Wittgenstein Decision Table Encoding

The 448 cells may be encoded as decision tables in OMI-Lisp using the Wittgenstein truth-function as the operator:

```omi
(decision-table
  (name . "Q1-A1")
  (inputs . (C1 C2 C3 C4))
  (output . proof-form)
  (truth-operator . Vpq)  ;; OR — constructive if any slot holds
  (rules .
    ((TTTT . constructive)
     (TTTF . constructive)
     ...
     (FFFF . falsification))))
```

Each truth-gate file (FACTS.omi, RULES.omi, COMBINATORS.omi, CLOSURES.omi, CONS.omi) is a partial decision table over the 4 citation slots, providing the Karnaugh map for a subset of the 448 cells.

---

## Cross-Reference: Canonical State Files

| State | Connection to Constitutional Grid |
|-------|----------------------------------|
| `00-COSMOLOGY.md` | Genesis context; the void from which these questions emerged |
| `01-ONTOLOGY.md` | Names the entities that the constitution governs |
| `02-DOCTRINE.md` | The invariant laws that the 448 matrix formalizes |
| `03-FOUNDATIONS.md` | Primitives that underpin the algorithms (postulates, axioms, palindrome) |
| `04-ATOMIC-KERNEL.md` | The four irreducible objects (Null, Bit, Pair, Relation) |
| `05-PURE-ALGORITHMS.md` | The 7 canonical operations |
| `06-FORMAL-PROOFS.md` | Proof stack tracking |
| `07-ISA.md` | Machine implementation of all 7 algorithms |
| `08-PROTOCOL-SEMANTICS.md` | Control-plane (A2) and escape (A4) spec; frame format |
| `09-OMI-LISP.md` | Declaration surface — SExpr grammar, decision tables |
| `10-BLACKBOARD.md` | Evaluation surface — bitboards, bit-blips |
| `11-NOTATION-MULTIPLEXING.md` | Earned gauge-band multiplexing; pre-language structure |
| `12-VERSION-CONTROL.md` | Seeds, citations, scopes |
| `13-MASTER-ARCHITECTURE.md` | Architecture map — construction spine, constitutional spine |
| `14-CANONICAL-CONSTITUTION.md` | The verification grid — this matrix's companion |
| `15-CLASSIFICATION-TERMINOLOGY.md` | Term roles and document categories |
| `16-SYMBOLIC-GRAMMAR.md` | The Omi-* protocol grammar boundary |
| `17-RELATIONAL-QUOTATION.md` | Cardinality, ordinality, quotation, carry-forward |
| `18-GAUGE-INTERRUPTS.md` | Gauge selection (A4/A5) — orientation, pleth |
| `19-PROJECTION-FACES.md` | Projection algorithm (A3) specification |
| `20-TRANSFORM-CARRIERS.md` | External nondeterminism port contracts (A5/A6) |
| `21-SURFACE-CLAUSES.md` | Transition algorithm (A1) — Delta Law, quadratic forms, Fano |
| `22-PROPAGATION-MODEL.md` | Wave classification and carrier propagation (A3/A6/A7) |
| `23-REFERENCE-GLOSSARY.md` | Definitions of every term used in the canon |
| `24-OBSERVER-CHANGELOG.md` | Observer-facing migration history |

---

## Usage

The 448 matrix serves three purposes:

1. **Design verification** — Every new feature must satisfy all relevant proof cells
2. **Implementation testing** — Each cell is a test case in the canonical test suite
3. **Formal verification** — Coq proofs in `proofs/` implement the cells as theorems

See `19-CONSTITUTION.md` at the repository root for the master document.
