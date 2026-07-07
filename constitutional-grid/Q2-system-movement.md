# Q2 — How Does the System Move?

**Answer:** A bounded deterministic transition law moves the system.

## Core Principle

Movement in OMI is not time. It is not a clock. It is not an event loop. Movement is the application of the Delta Law to canonical state. Each application of Δ_C advances the system by one tick. The period is exactly 8 — meaning the system returns to its starting state after 8 ticks, but with new context accumulated through the orbit.

Movement is bounded because the state space is finite (16-bit segments × 8 = 128-bit frame). It is deterministic because Δ_C is a pure function: same input, same output, always. There is no random seed, no scheduler choice, no race condition.

---

## A1 — Transition

### Constructive Proof
`delta/replay` yields the same next state for the same input. The Delta Law Δ_C(x) = rotl(x,1) ⊕ rotl(x,3) ⊕ rotr(x,2) ⊕ C is a pure function. Given state S at tick T, the state at tick T+1 is always Δ_C(S). This has been verified exhaustively over all 65536 possible 16-bit states — period 8 holds for every value. Replay over any trace recomputes the same trajectory.

### Falsification Proof
Nondeterministic next-state function fails parity/replay vectors. If the transition function produces different outputs for the same input across two runs, replay will detect the mismatch. A hash-based state verification at each tick catches any deviation. If the computed hash does not match the stored receipt, the transition was not law-abiding.

---

## A2 — Control-Plane

### Constructive Proof
Movement is encoded within a bounded symbolic control substrate. The control lane markers (FS, GS, RS, US, ESC, NULL) define the structural boundaries through which state flows. The interpreter advances through the frame one segment at a time, with control markers determining whether the current segment is structural or payload. The movement of the interpreter through the frame is deterministic: byte position i always produces the same interpretation at the same position.

### Falsification Proof
Out-of-band motion control not represented in the stream is non-replayable. If movement is controlled by an external signal (timer, interrupt not in the stream, network event), the replay observer cannot reconstruct the execution. Movement must be fully determined by the frame content and the current position within it.

---

## A3 — Projection

### Constructive Proof
Visual and narrative motion is rendered from the evolving canonical index. As the canonical state advances through Delta Law ticks, the projection algorithm reads the changing state and produces updated views. The movement perceived by the viewer (text scrolling, graph rotating, SVG animating) is a reflection of underlying state movement. The projection does not move — it displays movement.

### Falsification Proof
Projection-driven state movement without event or log support is invalid. If a renderer modifies state to create the appearance of motion (e.g., interpolating frames by writing intermediate states), the movement is not canonical. The projection may only read state, not write it. Movement belongs to the transition law, not the display layer.

---

## A4 — Escape

### Constructive Proof
The interrupt scope returns to deterministic movement after closure. When the interpreter enters ESC, it suspends normal frame advancement and reads sub-instructions. When ESC terminates (via a second ESC or scope terminator), the interpreter resumes normal movement at the next frame. The escape algorithm guarantees that the number of ticks consumed during escape is bounded and deterministic.

### Falsification Proof
Unterminated or time-closed escape causes movement ambiguity and is rejected. If the ESC scope is never terminated, the interpreter cannot resume normal movement. If the scope is terminated by a timeout instead of a structural marker, the resumption point is non-deterministic. Both cases violate Q2 — the system must move deterministically or not at all.

---

## A5 — Partition & Chirality (Fano Selection)

### Constructive Proof
Refinement shifts are deterministic by tick, with kernel-derived chirality. Each tick, the partition algorithm recomputes the Fano subset boundaries. The chirality function f(kernel_state, tick) determines orientation. As the tick advances, the partition structure shifts according to the Delta Law orbit. The movement from one partition state to the next is fully determined by the tick count and the kernel state.

### Falsification Proof
Arbitrary subset rotation or label-derived first-set selection is invalid. If the partition order is based on a label that changes non-deterministically (e.g., by user input or network arrival order), the movement of the partition boundary is not canonical. Partition movement must follow the law, not external events.

---

## A6 — Proposal/Receipt

### Constructive Proof
Interventions move state only at lawful deferred commit points. A proposal does not move state — it is a request. State moves only when the receipt is issued and the commit executes. The movement from pre-proposal state to post-commit state is a law-defined transition: `S_t → propose → S_t (no change) → receipt → commit → S_{t+1}`. The system moves at commit time, not at proposal time.

### Falsification Proof
Mid-frame direct mutation bypassing defer/commit breaks movement law. If an intervention modifies state between the proposal and the receipt, that modification is not part of the lawful movement. The system moved without law authorization. Any state difference detected between proposal submission and commit execution that is not attributable to law-defined transitions invalidates the movement.

---

## A7 — Branch/Reconciliation

### Constructive Proof
Canonical and branch traces each move lawfully from explicit roots. The canonical trace moves by the Delta Law from the genesis state. The branch trace moves by the same law from the branch base index. Both trajectories are deterministic and replayable. The reconciliation algorithm computes the merge by applying branch deltas to the canonical trace. Movement in both traces and in the merge result is law-defined.

### Falsification Proof
Untracked fork without base index or root cannot be replayed. If a branch is created without recording the base index, the trajectory of the branch is not anchored. Replay cannot reconstruct the branch from genesis because the starting point is unknown. A branch that cannot be replayed violates Q2 — its movement is not traceable to the law.
