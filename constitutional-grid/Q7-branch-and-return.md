# Q7 — How Does It Branch and Return Without Fragmentation?

**Answer:** Canonical trace, branch state, and shared deltas are distinct and returnable.

## Core Principle

Fragmentation occurs when multiple traces diverge and cannot be reconciled. OMI prevents fragmentation by maintaining a single canonical reference. Branches are not independent realities — they are derived traces anchored to the canonical base. The return path is always defined.

This is the OMI Collapse applied to versioning: the distinction between canonical and branch is collapsed at the reconciliation boundary, but maintained as separate trajectories within the trace topology. Every branch has a parent. Every merge has a receipt. Every divergence can be tracked.

---

## A1 — Transition

### Constructive Proof
Each trace (canonical and branch) follows the same lawful transition semantics. The Delta Law does not distinguish between canonical trace and branch trace. Both advance by Δ_C. The only structural difference is the base index: branch trace has a `base_index` pointing to the canonical state at the fork point, while the canonical trace starts from genesis. Because both follow the same law, replay is possible for both.

### Falsification Proof
Branch state with an undefined transition basis is invalid. If a branch trace does not use the Delta Law (e.g., it uses a different transition function), the state is not comparable. A diff between canonical and branch state would show changes that are not representable as deltas from the base. The branch is not a derivation — it is a separate system. Such a branch cannot be reconciled.

---

## A2 — Control-Plane

### Constructive Proof
Structural scopes preserve separation between layers. The control plane markers define which segments belong to which scope. In a branch context, the markers define whether a given segment is canonical scope, branch scope, or shared scope. The control plane does not collapse these scopes — it preserves them as explicit structural boundaries.

### Falsification Proof
Cross-layer scope leakage causes fragmentation and is invalid. If a canonical segment is modified by a branch delta without explicit scope marking, the modification leaks across layers. The canonical trace no longer reflects only canonical transitions. The branch trace no longer reflects only branch deltas. The two layers are fragmented — neither can be reconstructed independently.

---

## A3 — Projection

### Constructive Proof
The return to canonical reference remains available from any branch view. The projection algorithm can render the canonical trace, the branch trace, or a diff between them. Switching from branch view to canonical view is a parameter change in the projection selector, not a state mutation. The viewer may always return to the canonical reference.

### Falsification Proof
Projection-only branch identity without canonical anchor is invalid. If a projection treats a branch as a standalone view without reference to its canonical base, the viewer may not realize they are looking at a branch. They may make decisions based on branch state, thinking it is canonical. Every branch projection must make its anchored status visible.

---

## A4 — Escape

### Constructive Proof
Branch creation is an explicit bounded action within the interrupt/commit path. An ESC scope may initiate a branch by issuing a "propose branch" sub-instruction. The branch proposal includes the base index and an optional branch label. The ESC scope closes, the proposal is receipted, and the branch trace begins from the base index. The canonical trace continues unaffected.

### Falsification Proof
A never-closing branch mode without a return path is invalid. If a branch is created but the ESC scope does not close, the interpreter remains in branch-creation mode. There is no committed branch state — only an open proposal. The system is in limbo between the canonical trace and a branch that has not been finalized. An open-ended branch mode is a fragmentation risk.

---

## A5 — Partition & Chirality (Fano Selection)

### Constructive Proof
Branch selection preserves origin and chirality derivation provenance. The branch record includes the base index and the chirality state at the base tick. The partition structure at any point in the branch can be recomputed from the branch's own canonical state (base + deltas + ticks). The origin of any partition or chirality decision in the branch can be traced back to the base.

### Falsification Proof
Branch merge or selection without chirality consistency is invalid. If a branch divides the partition subsets in a different way than the canonical trace would have (e.g., merging two subsets that are separate in canonical), the chirality labels lose consistency. A merge of such a branch produces a state where the canonical chirality function no longer computes the expected partition. Branch operations must preserve partition structure.

---

## A6 — Proposal/Receipt

### Constructive Proof
Branch differences are receipted and diffable. Every delta in a branch is associated with a proposal and receipt. The set of deltas from base to HEAD is the union of all receipted proposals on the branch. The diff algorithm computes the accumulated change as: `canonical_state_at_base + Σ(accepted_proposals)`. Because every change is receipted, every change is diffable.

### Falsification Proof
Undiffable branch mutation without receipts is invalid. If a branch state differs from the base state and the difference cannot be decomposed into receipted proposals, the mutation is not auditable. The branch contains state that was not lawfully proposed and accepted. Such a branch cannot be safely reconciled because the reconciliation algorithm does not know what the change was or why it was made.

---

## A7 — Branch/Reconciliation

### Constructive Proof
`base_index + deltas + return` remains explicit and replayable. The branch reconciliation algorithm takes three inputs:
1. **base_index**: the tick in the canonical trace where the branch began
2. **deltas**: the accumulated set of receipted changes on the branch
3. **return**: the merge strategy (apply, squash, selective)

The reconciliation produces a merged canonical state by: `canonical_state_at(canonical_tip) + select(deltas, return_strategy)`. The result is deterministic and replayable.

### Falsification Proof
An untracked, irreconcilable fork without lineage metadata is invalid. If a branch has no base index, no receipted deltas, and no merge strategy, there is no way to reconcile it. The fork is irreconcilable — the system cannot determine the relationship between the branch state and the canonical state. An irreconcilable fork is fragmentation by definition.
