# Q5 — How Does It Allow Intervention Without Losing Replay?

**Answer:** ESC provides bounded interrupt with deterministic return.

## Core Principle

An open system must allow intervention — a user or agent must be able to interact with the state without breaking the system's ability to replay. The solution is the ESC escape mechanism: a bounded scope within which intervention occurs, followed by a deterministic return to the data stream.

The key constraint: ESC does not break replay because the intervention is either (a) recorded as a proposal before affecting state, or (b) scoped to the projection layer where it does not affect canonical state. Replay replays the canonical frame stream, not the projection-layer interactions. ESC introduces bounded non-closure that is formally closed by the termination marker.

---

## A1 — Transition

### Constructive Proof
Post-interrupt continuation resumes at the lawful next frame. When the interpreter exits an ESC scope, it returns to the data stream at the exact position it would have been if the ESC had not occurred. The canonical state before the ESC was committed. The ESC scope may read and modify local interpretation state, but the canonical transition continues from the same pre-ESC state. Replay can skip the ESC interior and jump directly to the continuation point.

### Falsification Proof
Current-frame mutation bypassing transition causes replay drift. If the ESC scope modifies the canonical state (not just local interpretation state), the post-ESC state is no longer Δ_C(pre_ESC_state). Replay that skips the ESC interior will compute a different post-ESC state. The trace diverges. Intervention that mutates canonical state outside the proposal/receipt path violates replay.

---

## A2 — Control-Plane

### Constructive Proof
ESC is an explicit structural access introducer. The ESC byte (0x03BF = ο) is a typed control marker with defined semantics. When the interpreter sees ESC, it knows that a bounded scope of intervention has begun. The control plane does not guess at intervention boundaries — ESC declares them explicitly. The stream position marks the start and end of every intervention scope.

### Falsification Proof
Implicit interrupt access without ESC is rejected. If an agent or user attempts to intervene in the stream without an ESC marker, the interpreter has no way to distinguish intervention from normal data. The control plane cannot parse an intervention that has no structural signal. An intervention without ESC is invalid by constitutional law.

---

## A3 — Projection

### Constructive Proof
Local pause is projection-only and non-authoritative. A viewer may pause their projection, zoom into a region, or rotate a 3D view without affecting the canonical state. These interactions are purely local to the projection layer. They do not generate proposals. They do not trigger receipts. They do not change the canonical state. Replay replays the state, not the viewer's interaction history.

### Falsification Proof
UI dwell time defining canonical scope is invalid by law. If a projection layer interprets "user paused on this frame for 5 seconds" as meaning "this frame should be highlighted in the canonical record," the projection layer has overstepped. Dwell time is a projection artifact. It is not canonical state. A projection that treats viewer behavior as semantic input is invalid.

---

## A4 — Escape

### Constructive Proof
Finite scope, deterministic closure, and return-to-data are enforced. The ESC algorithm defines:
- **Finite scope**: the number of bytes between ESC and scope terminator is bounded
- **Deterministic closure**: the terminator is a structural marker (ESC or scope terminator byte)
- **Return-to-data**: after the terminator, the interpreter returns to the data stream

These three properties guarantee that the intervention is contained and replayable.

### Falsification Proof
Time-based closure or open-ended escape is rejected. If an ESC scope is closed by a timeout ("ESC scope expires after 10 seconds"), the closure point is non-deterministic. Two replays with different timing will close the ESC at different points. The intervention is not replayable. Only structural closure (marker in the stream) is constitutional.

---

## A5 — Partition & Chirality (Fano Selection)

### Constructive Proof
A user or agent may influence the advisory horizon only; canonical orientation remains kernel-derived. The partition algorithm may accept advisory input (a "suggested starting subset") from the user or agent. This suggestion may influence the ordering within the advisory horizon (the next N ticks), but the canonical chirality function f(kernel_state, tick) always determines the final orientation. The suggestion is a projection-layer input, not a canonical state mutation.

### Falsification Proof
Escape or local scope overriding chirality derivation is invalid. If an ESC handler directly sets the chirality label (e.g., ESC+SET-CHIRALITY command), it overrides the kernel-derived orientation. The partition algorithm no longer reflects canonical state. Chirality must always be derived from kernel state, never set by intervention.

---

## A6 — Proposal/Receipt

### Constructive Proof
Intervention becomes a deferred artifact, then accepted or rejected. When a user or agent wishes to intervene, they issue a proposal. The proposal is an explicit artifact in the frame stream. The system may accept it (issuing a receipt and committing the change) or reject it (issuing a rejection receipt). The intervention is not applied until the commit. Replay replays the proposal and the acceptance/rejection, not the act of intervention itself.

### Falsification Proof
No proposal or receipt means no lawful intervention state transition. If state changes in response to an intervention and there is no proposal-receipt pair in the frame stream, the change is not replayable. There is no record of what was proposed, who proposed it, or whether it was accepted. The system mutated in response to an intervention that has no constitutional record — this is invalid.

---

## A7 — Branch/Reconciliation

### Constructive Proof
An interrupt can materialize a fork without mutating the canonical trace. If a user intervenes within an ESC scope and the intervention proposes a change that is accepted, the result may be a branch. The branch is a separate trace, anchored to the base index. The canonical trace is unchanged. Replay of the canonical trace continues without the branch. Replay of the branch follows its own trajectory from the base index.

### Falsification Proof
Direct canonical overwrite via branch intent is invalid. If a branch is merged back into the canonical trace without going through the reconciliation algorithm, the canonical trace is overwritten. The pre-overwrite canonical state is lost. Replay cannot reproduce the pre-branch state because the overwrite is not part of the Delta Law sequence. Branches must be reconciled, not imposed.
