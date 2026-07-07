# 112 Proofs Matrix — Constitutional Verification Grid

## 8 × 7 × 2 = 112 Proof Obligations

This directory formalizes the OMI constitution as a verification grid. Every invariant claim of the system must answer eight questions, be enforceable through seven algorithms, and be provable in two forms.

---

## The Formula

```text
8 invariant questions define what must remain true.
7 algorithms define how the system enforces those truths.
2 proof forms ensure each claim is both constructible and falsifiable.

8 × 7 × 2 = 112 proof obligations
```

---

## Structure

| Directory | Contents |
|-----------|----------|
| `Q1-source-of-truth.md` through `Q8-open-meaning-closed-law.md` | One document per invariant question; each contains the 7 × 2 = 14 proof cells for that question |
| `algorithms/A1-transition.md` through `A7-branch-reconciliation.md` | One document per algorithm; each contains the 8 × 2 = 16 proof cells for that algorithm |
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

Each algorithm defines a concrete enforcement mechanism. Every algorithm must provide a constructive proof and a falsification proof for each of the 8 invariant questions.

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

## The 2 Proof Forms

Every cell in the 8×7 grid must provide:

| Proof Form | Question It Answers |
|------------|---------------------|
| **Constructive** | How is this property established? What mechanism builds the guarantee? |
| **Falsification** | How is violation detected or rejected? What test breaks a false claim? |

A claim that cannot be constructed is not implementable. A claim that cannot be falsified is not testable. Both forms are required.

---

## Cross-Reference: Canonical State Files

| State | Connection to Constitutional Grid |
|-------|----------------------------------|
| `00-ORIGIN.md` | Genesis context; the void from which these questions emerged |
| `01-ONTOLOGY.md` | Names the entities that the constitution governs |
| `02-DOCTRINE.md` | The invariant laws that the 112 matrix formalizes |
| `03-MANIFESTO.md` | Philosophical justification for open meaning / closed law (Q8) |
| `04-FOUNDATIONS.md` | Primitives that underpin the algorithms (postulates, axioms, palindrome) |
| `05-PROJECTIONS.md` | Projection algorithm (A3) specification |
| `06-PROTOCOL.md` | Control-plane (A2) and escape (A4) spec; frame format |
| `07-GEOMETRY.md` | Transition algorithm (A1) — Delta Law; partition/chirality (A5) — Fano |
| `08-ISA.md` | Machine implementation of all 7 algorithms |
| `09-ECOSYSTEM.md` | Proposal/receipt (A6) and branch/reconciliation (A7) in open world |
| `10-GLOSSARY.md` | Definitions of every term used in the grid |

---

## Usage

The 112 matrix serves three purposes:

1. **Design verification** — Every new feature must satisfy all relevant proof cells
2. **Implementation testing** — Each cell is a test case in the canonical test suite
3. **Formal verification** — Coq proofs in `proofs/` implement the cells as theorems

See `CONSTITUTION.md` at the repository root for the master document.
