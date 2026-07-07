# Constitution of the OMI Canon

## The 112 Proofs Matrix — Constitutional Verification Grid

This document defines the constitution of the OMI canon. The constitution is not a separate document from the canon — it is the matrix that verifies every claim in the canon. Every line in every state file must satisfy at least one cell of the 112 matrix. Every algorithm must provide proof in both constructive and falsification forms. Every invariant question must be answerable by every algorithm.

---

## Repository Structure

```
omi-canon/
│
├── CONSTITUTION.md           ← This file — the verification matrix
├── README.md                 ← State transition manifest (reading paths)
│
├── 00-ORIGIN.md              ← State 00 — The Void
├── 01-ONTOLOGY.md            ← State 01 — The Naming
├── 02-DOCTRINE.md            ← State 02 — The Law
├── 03-MANIFESTO.md           ← State 03 — The Meaning
├── 04-FOUNDATIONS.md         ← State 04 — The Primitives
├── 05-PROJECTIONS.md         ← State 05 — The Surface
├── 06-PROTOCOL.md            ← State 06 — The Wire
├── 07-GEOMETRY.md            ← State 07 — The Unfolding
├── 08-ISA.md                 ← State 08 — The Machine
├── 09-ECOSYSTEM.md           ← State 09 — The World
├── 10-GLOSSARY.md            ← State 10 — The Closure
│
├── constitutional-grid/      ← The 112 Proofs Matrix
│   ├── README.md             ← Grid overview
│   ├── Q1-source-of-truth.md ← Invariant question 1 (14 proof cells)
│   ├── Q2-system-movement.md ← Invariant question 2 (14 proof cells)
│   ├── Q3-control-vs-payload.md
│   ├── Q4-meaning-across-projections.md
│   ├── Q5-intervention-and-replay.md
│   ├── Q6-collaboration-without-hidden-authority.md
│   ├── Q7-branch-and-return.md
│   ├── Q8-open-meaning-closed-law.md
│   ├── algorithms/
│   │   ├── A1-transition.md           ← Algorithm 1 (16 proof cells)
│   │   ├── A2-control-plane.md        ← Algorithm 2 (16 proof cells)
│   │   ├── A3-projection.md           ← Algorithm 3 (16 proof cells)
│   │   ├── A4-escape.md               ← Algorithm 4 (16 proof cells)
│   │   ├── A5-partition-chirality.md  ← Algorithm 5 (16 proof cells)
│   │   ├── A6-proposal-receipt.md     ← Algorithm 6 (16 proof cells)
│   │   └── A7-branch-reconciliation.md← Algorithm 7 (16 proof cells)
│   └── proofs/
│       ├── verified_execution.v       ← Verified C/Coq correspondence
│       ├── omi_pi_proof.v             ← π approximation via 1/73 weight block
│       ├── OMI_bialgebra.v            ← Bialgebraic collapse of representation/interpretation
│       ├── functorial_semantics.v     ← Functor from frames to states
│       ├── delta_orbit_theory.v       ← Algebraic Delta Law orbit properties
│       ├── coalgebraic_bisimulation.v ← Bisimulation for projection equivalence
│       └── AtomicKernel.v            ← Atomicity of transitions, proposals, branches
│
├── truth-gates/               ← OMI truth gate files (normative)
│   ├── RULES.omi
│   ├── FACTS.omi
│   ├── CLOSURES.omi
│   ├── COMBINATORS.omi
│   └── CONS.omi
│
├── mirrors/                   ← Compiled .imo mirrors
│
└── _archive/                  ← Original source documents (historical)
```

---

## The 112 Formula

```text
8 invariant questions define what must remain true.
7 algorithms define how the system enforces those truths.
2 proof forms ensure each claim is both constructible and falsifiable.
8 × 7 × 2 = 112 proof obligations
```

---

## The 8 Invariant Questions

| # | Question | Constitutional Clause |
|---|----------|----------------------|
| Q1 | **What is the source of truth?** | The algorithm is the source of truth |
| Q2 | **How does the system move?** | A bounded deterministic transition law moves the system |
| Q3 | **How does it distinguish payload from control?** | A canonical control plane separates structural roles from payload |
| Q4 | **How does it preserve meaning across projections?** | Artifacts are projections of invariant state, not authorities |
| Q5 | **How does it allow intervention without losing replay?** | ESC provides bounded interrupt with deterministic return |
| Q6 | **How does it permit collaboration without hidden authority?** | Agents collaborate through proposals, receipts, and deferred commit |
| Q7 | **How does it branch and return without fragmentation?** | Canonical trace, branch state, and shared deltas are distinct and returnable |
| Q8 | **How does it stay open in meaning while closed in law?** | Closure belongs to law; openness belongs to interpretation |

---

## The 7 Algorithms

| # | Algorithm | Constitutional Role |
|---|-----------|---------------------|
| A1 | **Transition** | Advances canonical state under deterministic law (Delta Law Δ_C) |
| A2 | **Control-Plane** | Separates FS/GS/RS/US/ESC/NULL structural markers from payload |
| A3 | **Projection** | Derives text/graph/SVG/3D/XR views without creating authority |
| A4 | **Escape** | Opens bounded interrupt scope with deterministic structural closure |
| A5 | **Partition & Chirality** | Produces balanced Fano partitions with kernel-derived orientation labels |
| A6 | **Proposal/Receipt** | Converts interventions into inspectable deferred artifacts with receipts |
| A7 | **Branch/Reconciliation** | Preserves canonical reference with anchored branches and deterministic merge |

---

## The 2 Proof Forms

| Form | Question It Answers |
|------|---------------------|
| **Constructive** | How is this property established? What mechanism builds the guarantee? |
| **Falsification** | How is violation detected or rejected? What test breaks a false claim? |

Every cell in the 8 × 7 grid requires both forms.

---

## The Full 112-Cell Matrix

### Q1 — Source of Truth (algorithm is truth)

| Algorithm | Constructive | Falsification |
|-----------|-------------|---------------|
| A1 Transition | Canonical state derived only from deterministic Δ_C over prior state + constants | Manual overwrite bypassing Δ_C yields replay mismatch |
| A2 Control-Plane | Interpretation state is explicit in canonical tuple | Hidden parser state not derivable from stream is non-canonical |
| A3 Projection | Views are generated from canonical state; projections are rebuildable | Cached artifact as authority causes divergence from recomputed output |
| A4 Escape | Interrupt semantics are law-defined (ESC + bounded scope + return) | Implicit escape or unclosed interrupt breaks deterministic decoding |
| A5 Partition & Chirality | Partition topology is deterministic; chirality is kernel-derived per tick | Hardcoded subset ordering or non-kernel orientation is invalid |
| A6 Proposal/Receipt | Proposed changes are explicit artifacts before application | Silent unreceipted mutation has no lawful proof trail |
| A7 Branch/Reconciliation | Canonical trace remains reference; branch traces are explicitly anchored | Branch overwrite of canonical without merge law is invalid |

### Q2 — System Movement (deterministic transition)

| Algorithm | Constructive | Falsification |
|-----------|-------------|---------------|
| A1 Transition | delta/replay yields same next state for same input | Nondeterministic next-state function fails parity/replay vectors |
| A2 Control-Plane | Movement is encoded within bounded symbolic control substrate | Out-of-band motion control not in stream is non-replayable |
| A3 Projection | Visual/story motion is rendered from evolving canonical index | Projection-driven state movement without event/log is invalid |
| A4 Escape | Interrupt scope returns to deterministic movement after closure | Unterminated or time-closed escape causes movement ambiguity |
| A5 Partition & Chirality | Refinement shifts are deterministic by tick with kernel-derived chirality | Arbitrary subset rotation or non-kernel first-set selection is invalid |
| A6 Proposal/Receipt | Interventions move state only at lawful deferred commit points | Mid-frame direct mutation bypassing defer/commit breaks movement law |
| A7 Branch/Reconciliation | Canonical and branch traces each move lawfully from explicit roots | Untracked fork without base/root cannot be replayed |

### Q3 — Control vs Payload (canonical control plane)

| Algorithm | Constructive | Falsification |
|-----------|-------------|---------------|
| A1 Transition | State machine update does not conflate parser mode with payload value | Mixed undecidable token semantics causes undefined transition path |
| A2 Control-Plane | FS/GS/RS/US/ESC/NULL semantics are explicit and typed | Ambiguous control token interpretation is rejected fail-closed |
| A3 Projection | Renderer consumes already-decoded state, not undecoded stream control | Renderer-side guessing of control boundaries creates non-canonical views |
| A4 Escape | ESC ESC literalization preserves payload transparency of reserved token | Unknown escape targets are rejected, preventing control/payload confusion |
| A5 Partition & Chirality | A5 controls partition and orientation only; it does not parse stream classes | Using A5 as parser authority violates control-plane law |
| A6 Proposal/Receipt | Proposal artifacts are explicit objects, not hidden inline control bytes | Inline hidden commands without artifact schema are invalid |
| A7 Branch/Reconciliation | Deltas are scoped by layer (canonical/branch/shared) | Cross-scope leakage of control intent without law is invalid |

### Q4 — Meaning Across Projections (artifacts are not authorities)

| Algorithm | Constructive | Falsification |
|-----------|-------------|---------------|
| A1 Transition | Same seed/tick reproduces same canonical basis for interpretation | Same-input different-state outcome falsifies deterministic meaning anchor |
| A2 Control-Plane | Structural boundaries preserve semantic grouping across projections | Boundary loss merges scopes and breaks semantic invariants |
| A3 Projection | Text/graph/svg/3D/XR are generated from same source state | Projection-specific ontology that cannot map back to source is invalid |
| A4 Escape | Interrupt affects interpretation window, not already-committed prior frame | Escape mutating prior committed meaning violates replay boundary |
| A5 Partition & Chirality | Chirality selects orientation deterministically while preserving canonical truth boundary | Projection/UI order changing A5 winner is invalid |
| A6 Proposal/Receipt | Semantic changes are explicit proposals with receipts before commit | Unreceipted semantic drift cannot be verified and is invalid |
| A7 Branch/Reconciliation | Branch meaning is diffable against canonical reference | Unanchored branch semantics without base comparison is invalid |

### Q5 — Intervention and Replay (ESC bounded interrupt)

| Algorithm | Constructive | Falsification |
|-----------|-------------|---------------|
| A1 Transition | Post-interrupt continuation resumes at lawful next frame | Current-frame mutation bypassing transition causes replay drift |
| A2 Control-Plane | ESC is explicit structural access introducer | Implicit interrupt access without ESC is rejected |
| A3 Projection | Local pause is projection-only and non-authoritative | UI dwell time defining canonical scope is invalid by law |
| A4 Escape | Finite scope + deterministic closure + return-to-data are enforced | Time-based closure or open-ended escape is rejected |
| A5 Partition & Chirality | User/agent may influence advisory horizon only; canonical orientation remains kernel-derived | Escape/local scope overriding chirality derivation is invalid |
| A6 Proposal/Receipt | Intervention becomes deferred artifact, then accepted/rejected | No proposal/receipt means no lawful intervention state transition |
| A7 Branch/Reconciliation | Interrupt can materialize a fork without mutating canonical trace | Direct canonical overwrite via branch intent is invalid |

### Q6 — Collaboration Without Hidden Authority (proposals and receipts)

| Algorithm | Constructive | Falsification |
|-----------|-------------|---------------|
| A1 Transition | No collaborator can bypass law-defined transition mechanics | Direct collaborator state write outside transition path is invalid |
| A2 Control-Plane | Scopes/roles are explicit in control context | Private unshared control channel is non-canonical collaboration |
| A3 Projection | Collaborators read snapshots, not hidden renderer internals | Projection-only scraped state cannot act as canonical authority |
| A4 Escape | Collaboration happens inside bounded interrupt window | Permanent never-closing control mode is invalid |
| A5 Partition & Chirality | Shared selection context is inspectable; chirality source is derivable from canonical state | Opaque ordering or hidden chirality source is invalid |
| A6 Proposal/Receipt | Accept/reject/commit trail is receipted and auditable | Silent acceptance or hidden commit path is invalid |
| A7 Branch/Reconciliation | Shared deltas are published as explicit artifacts | Unscoped propagation to all traces without artifact law is invalid |

### Q7 — Branch and Return Without Fragmentation (anchored traces)

| Algorithm | Constructive | Falsification |
|-----------|-------------|---------------|
| A1 Transition | Each trace follows same lawful transition semantics | Branch state with undefined transition basis is invalid |
| A2 Control-Plane | Structural scopes preserve separation between layers | Cross-layer scope leakage causes fragmentation |
| A3 Projection | Return to canonical reference remains available from any branch view | Projection-only branch identity without canonical anchor is invalid |
| A4 Escape | Branch creation is explicit bounded action within interrupt/commit path | Never-closing branch mode without return path is invalid |
| A5 Partition & Chirality | Branch selection preserves origin and chirality derivation provenance | Branch merge without chirality consistency is invalid |
| A6 Proposal/Receipt | Branch differences are receipted and diffable | Undiffable branch mutation without receipts is invalid |
| A7 Branch/Reconciliation | base_index + deltas + return remains explicit and replayable | Untracked irreconcilable fork without lineage metadata is invalid |

### Q8 — Open Meaning, Closed Law (closure is law, openness is interpretation)

| Algorithm | Constructive | Falsification |
|-----------|-------------|---------------|
| A1 Transition | Law remains deterministic regardless of interpretive overlays | Interpretive layer altering transition law falsifies closure |
| A2 Control-Plane | Structural boundaries are bounded while interpretation remains plural | Unbounded parser ambiguity destroys legal closure |
| A3 Projection | Many projections map to one canonical source | Any view elevated to source of truth is invalid |
| A4 Escape | Bounded non-closure is permitted only inside explicit escape scope | Escape without deterministic return is invalid |
| A5 Partition & Chirality | New partition schemes remain valid only with kernel-derived chirality | Extension introducing implicit ordering is invalid |
| A6 Proposal/Receipt | Differences are negotiable, receipted, and accountable | Free-form mutation without artifacts/receipts is invalid |
| A7 Branch/Reconciliation | Multiplicity of worlds preserves canonical center and return | Loss of canonical return path is fragmentation |

---

## Compact Statement

> 8 questions ask what must remain true.
> 7 algorithms provide enforceable lanes for each answer.
> 2 proof forms per lane (constructive + falsification) make every claim both buildable and break-testable.
> Therefore the framework targets **112 proofs**.

---

## Coq Proof Index

| Proof File | Primary Cells | Secondary Cells |
|-----------|--------------|-----------------|
| `proofs/verified_execution.v` | Q1A1c, Q1A1f, Q2A1c, Q2A1f, Q3A2c, Q3A2f | Q1A7c, Q1A7f |
| `proofs/omi_pi_proof.v` | Q2A1c, Q2A1f, Q4A5c, Q4A5f | Q1A5c, Q1A5f |
| `proofs/OMI_bialgebra.v` | Q8A1c, Q8A1f, Q4A3c, Q4A3f | Q8A3c, Q8A3f |
| `proofs/functorial_semantics.v` | Q6A6c, Q6A6f, Q4A3c, Q4A3f | Q1A3c, Q1A3f |
| `proofs/delta_orbit_theory.v` | Q2A1c, Q2A1f, Q1A1c, Q1A1f | Q4A1c, Q4A1f |
| `proofs/coalgebraic_bisimulation.v` | Q4A3c, Q4A3f, Q5A4c, Q5A4f, Q1A6c, Q1A6f | Q4A7c, Q4A7f |
| `proofs/AtomicKernel.v` | Q5A4c, Q5A4f, Q6A6c, Q6A6f, Q7A7c, Q7A7f | Q6A7c, Q6A7f |

---

## Cross-References to Canonical State Files

| State File | Constitutional Relevance |
|-----------|------------------------|
| `00-ORIGIN.md` | Documents the genesis of the 8 questions — what the author was discovering and why these invariants emerged from the void |
| `01-ONTOLOGY.md` | Names the entities — pointer, rule, proof, receipt, projection — that the constitution governs |
| `02-DOCTRINE.md` | Encodes the invariant laws that the 112 matrix formalizes as proof obligations |
| `03-MANIFESTO.md` | Articulates the philosophical foundation for Q8 (open meaning, closed law) — the rotation over mutation principle |
| `04-FOUNDATIONS.md` | Provides the primitives (palindrome, omicron anchors, postulates, axioms) that underpin all 7 algorithms |
| `05-PROJECTIONS.md` | Specifies the A3 projection algorithm in detail — the 6 DOM handles, bridge equation, meta-circular compiler |
| `06-PROTOCOL.md` | Specifies the A2 control-plane and A4 escape algorithms — frame format, control markers, receipt packing |
| `07-GEOMETRY.md` | Derives the A1 transition algorithm (Delta Law) and the A5 partition/chirality algorithm (Fano, 240 bridge, quadratic forms) |
| `08-ISA.md` | Implements all 7 algorithms as 32 opcodes with C99 and NodeJS backends — the machine that executes the constitution |
| `09-ECOSYSTEM.md` | Applies the constitution to multi-agent collaboration — A6 proposal/receipt and A7 branch/reconciliation in the open world |
| `10-GLOSSARY.md` | Defines every term used in the constitutional grid — closes the vocabulary |

---

## Constitutional Amendments

The constitution may be extended through the proposal/receipt mechanism defined in A6. Any amendment must:
1. Specify which cells of the 112 matrix it affects
2. Provide both constructive and falsification proofs for each affected cell
3. Pass through the same verification grid as the original claims

The 8 invariant questions themselves are not amendable. They define what it means to be OMI. A system that changes the 8 questions is a different system.

---

*The algorithm is the source of truth.*
