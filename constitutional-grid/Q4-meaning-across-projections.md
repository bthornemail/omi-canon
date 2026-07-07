# Q4 — How Does It Preserve Meaning Across Projections?

**Answer:** Artifacts are projections of invariant state, not authorities.

## Core Principle

A text view of an OMI frame is not the frame. A graph visualization is not the frame. A 3D rendering is not the frame. They are projections — surfaces through which a reader may recognize structure. The meaning of the system is not in any single projection. It is in the invariant state from which all projections are derived.

This is the OMI Collapse rendered as a constitutional constraint: representation and interpretation share one surface, but that surface is the canonical binary frame, not any particular projection of it. The meaning is preserved because the projections are functions of the state. Change the state, and all projections change consistently. Attempt to change a projection independently, and the invariant detects the divergence.

---

## A1 — Transition

### Constructive Proof
The same seed and tick reproduce the same canonical basis for interpretation. The Delta Law is deterministic. Given genesis state S₀ and tick count T, the state at T is always Δ_C^T(S₀). This state is the basis for all projections. Any two parties with the same S₀ and same T compute the same canonical state, and therefore all projections render the same meaning.

### Falsification Proof
Same-input, different-state outcome falsifies the deterministic meaning anchor. If two runs with identical S₀ and identical T produce different canonical states, then projections will differ. There is no single meaning — there are two different meanings depending on implementation. A divergence in canonical state is the only thing that can falsify meaning preservation across projections.

---

## A2 — Control-Plane

### Constructive Proof
Structural boundaries preserve semantic grouping across projections. The FS/GS/RS/US/ESC/NULL markers partition the frame into a hierarchy. This hierarchy is the same regardless of which projection renders it. The text projection shows the group boundaries as indentation. The graph projection shows them as node clusters. The SVG projection shows them as regions. The same structural grouping is preserved across all projections because they all read the same control markers.

### Falsification Proof
Boundary loss merges scopes and breaks semantic invariants. If a projection fails to render a control boundary (e.g., treating a GS marker as continuous text instead of a group separator), it merges two scopes that the canonical state keeps separate. The viewer sees a different structure than the canonical state defines. A projection that loses boundaries is a misrepresentation — it does not preserve meaning.

---

## A3 — Projection

### Constructive Proof
Text, graph, SVG, 3D, and XR views are generated from the same source state. The projection algorithm is a pure function: `projection(canonical_state, surface_selector) → artifact`. Given the same state and the same selector, the artifact is deterministic. The text artifact, graph artifact, SVG artifact, 3D artifact, and XR artifact are all different functions of the same input. They agree because they are functions of the same value.

### Falsification Proof
A projection-specific ontology that cannot map back to source is invalid. If a projection introduces concepts that have no representation in the canonical state (e.g., a 3D projection with lighting parameters that are not derived from any segment), those concepts are not canonical. They exist only in the projection. A viewer interacting with them may infer meaning that does not exist in the state. The projection leaks invented meaning.

---

## A4 — Escape

### Constructive Proof
An interrupt affects the interpretation window, not already-committed prior frame. When ESC opens a scope, the interpreter reads sub-instructions within that window. The canonical state before the ESC is not modified by the sub-instructions. After ESC closes, the interpreter returns to the data stream at the same position it would have been had the ESC not occurred. The meaning of the pre-escape state is preserved across the interrupt.

### Falsification Proof
Escape mutating prior committed meaning violates the replay boundary. If the ESC scope modifies state that was committed before the ESC opened, then the pre-escape meaning is retroactively changed. The projection of the pre-escape frame no longer matches what was rendered at that time. Replay cannot reconstruct the original viewer experience. ESC may only affect interpretation within its scope.

---

## A5 — Partition & Chirality (Fano Selection)

### Constructive Proof
Chirality selects orientation deterministically while preserving the canonical truth boundary. The partition structure defines which elements are in which subset. The chirality label defines which subset is inbound (ο) and which is outbound (Ο). Both are derived from canonical state. The meaning of "this subset is first" is the same across all projections because the chirality function is deterministic and state-derived.

### Falsification Proof
Projection or UI order changing the A5 winner is invalid. If a projection reorders partition subsets based on layout convenience (e.g., placing the smaller subset first for visual balance), the chirality label no longer reflects the canonical meaning. The viewer sees a different orientation than the law defines. A projection must render the partition in its canonical order, not in a visually convenient order.

---

## A6 — Proposal/Receipt

### Constructive Proof
Semantic changes are explicit proposals with receipts before commit. A proposal documents the intended change. A receipt records that the proposal was accepted. The commit applies the change. At each step, the canonical state is well-defined. Projections always render committed state, not proposed state. The meaning a viewer sees is the meaning that has been accepted, not the meaning that has been suggested.

### Falsification Proof
Unreceipted semantic drift cannot be verified and is invalid. If state changes without a matching proposal-receipt pair, the projections will change without any audit trail. A viewer cannot determine whether the change was intentional or accidental. Meaning has drifted without accountability. Every semantic change must be traceable to a proposal and receipt.

---

## A7 — Branch/Reconciliation

### Constructive Proof
Branch meaning is diffable against canonical reference. The branch algorithm stores the base index and the delta set. The reconciliation algorithm can compute: `canonical_state_at_tick(commit_point) + branch_deltas = merged_state`. The meaning of the branch at any point is the canonical state at the base, modified by the accumulated deltas. A diff tool can show exactly where the branch diverges from canonical.

### Falsification Proof
Unanchored branch semantics without base comparison is invalid. If a branch does not record its base index, there is no way to compute what the canonical state was at the fork point. The branch's meaning is independent of the canonical trace — it could have been written from scratch. Without a base for comparison, the projection cannot show divergence. An unanchored branch is indistinguishable from a new canonical trace.
