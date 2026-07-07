# Q6 — How Does It Permit Collaboration Without Hidden Authority?

**Answer:** Agents collaborate through proposals, receipts, and deferred commit.

## Core Principle

No collaborator has special authority. No collaborator can bypass the law. All collaborators are peers under the same constitutional constraints. Authority is not assigned to identities — it is earned through receipted proposals that conform to the law.

This is the OMI Collapse applied to multi-agent systems: the distinction between proposing agent and accepting agent is collapsed. Every agent can propose. Every agent can accept. But no agent can enforce. The algorithm determines acceptance, not the identity of the proposer.

---

## A1 — Transition

### Constructive Proof
No collaborator can bypass the law-defined transition mechanics. Every state transition, whether initiated by agent A or agent B, must go through the same Δ_C function. There is no privileged transition path for authorized agents. The transition algorithm does not consult an access control list. It transforms state according to the law, regardless of who requested the change.

### Falsification Proof
Direct collaborator state write outside the transition path is invalid. If an agent has a privileged channel to write state directly (e.g., a root-level API that skips the transition function), that agent has hidden authority. The transition algorithm is no longer the universal path for state change. Any direct write outside Δ_C is a constitutional violation.

---

## A2 — Control-Plane

### Constructive Proof
Scopes and roles are explicit in the control context. The control markers (FS, GS, RS, US, ESC, NULL) define who is speaking and in what capacity. The lane marker (a tuple of channel + lane identifiers) specifies the collaboration scope. All collaborators see the same control markers. There is no private control channel.

### Falsification Proof
A private, unshared control channel is non-canonical collaboration. If two agents communicate through a side channel (e.g., a separate TCP connection with unlogged messages), those communications are not part of the canonical frame stream. Other collaborators cannot audit them. Hidden authority emerges from hidden channels. All collaboration must occur within the shared frame stream.

---

## A3 — Projection

### Constructive Proof
Collaborators read snapshots, not hidden renderer internals. When collaborator A wants to see what collaborator B is doing, they both read from the canonical state through the projection algorithm. The projection algorithm does not have private views — it produces the same output for the same input. A collaborator cannot hide state by manipulating the renderer.

### Falsification Proof
Projection-only scraped state cannot act as canonical authority. If a collaborator scrapes a projection artifact and treats it as canonical (e.g., reading the text projection and parsing it as data), they may see stale or incomplete state. The projection is not the canonical state. Making decisions based on projection-scraped data without verifying against canonical state introduces hidden interpretation errors.

---

## A4 — Escape

### Constructive Proof
Collaboration happens inside a bounded interrupt window. ESC provides a common scope where multiple collaborators may interact. Within the ESC scope, all participants see the same sub-instructions. The scope is bounded — it does not persist across frames. After ESC closes, all collaborators return to the same canonical data stream.

### Falsification Proof
A permanent, never-closing control mode is invalid. If an ESC scope is never closed, the collaborators remain in an interrupt mode indefinitely. The canonical frame stream stops advancing. New collaborators joining the stream cannot determine what state the system is in because they do not know the history of the open ESC. An open-ended collaboration scope is a hidden authority — it controls what state is visible and when the stream advances.

---

## A5 — Partition & Chirality (Fano Selection)

### Constructive Proof
The shared selection context is inspectable, and the chirality source is derivable from canonical state. All collaborators can compute the same partition structure and the same chirality labels from the same canonical state and tick. There is no private partition scheme. Every agent knows which subset is inbound and which is outbound because they all run the same chirality function.

### Falsification Proof
Opaque ordering or a hidden chirality source is invalid. If some collaborators can compute the partition order and others cannot (because the ordering depends on a private key or a side channel), the system has hidden authority. Those who know the ordering can act on information that others lack. Chirality must be a public function of public state.

---

## A6 — Proposal/Receipt

### Constructive Proof
The accept/reject/commit trail is receipted and auditable. Every proposal is a frame in the stream. Every receipt is a frame in the stream. Every commit is a transition in the canonical state. Any collaborator can audit the history: who proposed what, when it was accepted, and what state resulted. The proposal/receipt algorithm does not privilege any agent — it treats all proposals equally.

### Falsification Proof
Silent acceptance or a hidden commit path is invalid. If a proposal is accepted without issuing a receipt, or if state changes without a corresponding commit frame, the acceptance is not auditable. Other collaborators cannot verify that the acceptance was lawful. A hidden commit path is a hidden authority — it allows state changes that cannot be traced.

---

## A7 — Branch/Reconciliation

### Constructive Proof
Shared deltas are published as explicit artifacts. When collaborators work in branches, the deltas between canonical and branch state are published as explicit frame sequences. Any collaborator can inspect the deltas, verify the base index, and understand what changes the branch introduces. The reconciliation algorithm produces a merged state that is deterministically derived from the canonical state plus the branch deltas.

### Falsification Proof
Unscoped propagation to all traces without artifact law is invalid. If a change made in one branch propagates to other branches or to the canonical trace without an explicit merge reconciliation artifact, the propagation is not auditable. Collaborators see state changes without understanding their origin. Every change must be scoped to its trace and explicitly propagated through reconciliation.
