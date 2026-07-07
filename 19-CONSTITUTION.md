# Constitution of the OMI Canon

## The 112 Proofs Matrix — Constitutional Verification Grid

This document defines the constitution of the OMI canon. The constitution is not a separate document from the canon — it is the matrix that verifies every claim in the canon. Every line in every state file must satisfy at least one cell of the 112 matrix. Every algorithm must provide proof in both constructive and falsification forms. Every invariant question must be answerable by every algorithm.

---

## Repository Structure

```
omi-canon/
│
├── 00-COSMOLOGY.md              ← State 00 — Cosmology
├── 01-ONTOLOGY.md               ← State 01 — Ontology
├── 02-DOCTRINE.md               ← State 02 — Doctrine
├── 03-FOUNDATIONS.md            ← State 03 — Foundations
├── 04-ATOMIC-KERNEL.md          ← State 04 — Atomic Kernel
├── 05-PURE-ALGORITHMS.md        ← State 05 — Pure Algorithms
├── 06-FORMAL-PROOFS.md          ← State 06 — Formal Proofs
├── 07-ISA.md                    ← State 07 — ISA
├── 08-PROTOCOL.md               ← State 08 — Protocol
├── 09-OMI-LISP.md               ← State 09 — OMI-Lisp
├── 10-BLACKBOARD.md             ← State 10 — Blackboard
├── 11-PROJECTION-FACES.md       ← State 11 — Projection Faces
├── 12-GAUGE-INTERRUPTS.md       ← State 12 — Gauge Interrupts
├── 13-SURFACE-APPLICATIONS.md   ← State 13 — Surface Applications
├── 14-WAVE-SURFACE-INTERPRETER.md ← State 14 — Wave Surface Interpreter
├── 15-IMO-PORTS.md              ← State 15 — IMO Ports
├── 16-DISTRIBUTED-OPEN-WORLD.md ← State 16 — Distributed Open World
├── 17-BUFFER-FRAMING.md         ← State 17 — Buffer Framing
├── 18-VERSION-CONTROL.md        ← State 18 — Version Control
├── 19-CONSTITUTION.md           ← State 19 — Constitution
├── 20-GLOSSARY.md               ← State 20 — Glossary
│
├── AGENTS.md                 ← Coding agent configuration
├── CONTRIBUTING.md           ← Contribution guide
├── LICENSE                   ← MIT license
├── README.md                 ← State transition manifest (reading paths)
├── SKILLS.md                 ← Repeatable project workflows
│
├── constitutional-grid/      ← The 448 Proofs Matrix
│   ├── README.md             ← Grid overview
│   ├── Q1-source-of-truth.md ← Invariant question 1 (56 proof cells)
│   ├── Q2-system-movement.md ← Invariant question 2 (56 proof cells)
│   ├── Q3-control-vs-payload.md
│   ├── Q4-meaning-across-projections.md
│   ├── Q5-intervention-and-replay.md
│   ├── Q6-collaboration-without-hidden-authority.md
│   ├── Q7-branch-and-return.md
│   ├── Q8-open-meaning-closed-law.md
│   ├── algorithms/
│   │   ├── A1-transition.md           ← Algorithm 1 (64 proof cells)
│   │   ├── A2-control-plane.md        ← Algorithm 2 (64 proof cells)
│   │   ├── A3-projection.md           ← Algorithm 3 (64 proof cells)
│   │   ├── A4-escape.md               ← Algorithm 4 (64 proof cells)
│   │   ├── A5-partition-chirality.md  ← Algorithm 5 (64 proof cells)
│   │   ├── A6-proposal-receipt.md     ← Algorithm 6 (64 proof cells)
│   │   └── A7-branch-reconciliation.md← Algorithm 7 (64 proof cells)
│   └── axioms/
│       ├── verified_execution.md       ← Verified C/Coq correspondence
│       ├── omi_pi_proof.md             ← π approximation via 1/73 weight block
│       ├── OMI_bialgebra.md            ← Bialgebraic collapse of representation/interpretation
│       ├── functorial_semantics.md     ← Functor from frames to states
│       ├── delta_orbit_theory.md       ← Algebraic Delta Law orbit properties
│       ├── coalgebraic_bisimulation.md ← Bisimulation for projection equivalence
│       └── AtomicKernel.md            ← Atomicity of transitions, proposals, branches
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

## The 448 Formula

```text
8 invariant questions define what must remain true.
7 algorithms define how the system enforces those truths.
4 citation slots frame each claim in relational space.
2 proof forms ensure each claim is both constructible and falsifiable.
8 × 7 × 4 × 2 = 448 proof cells
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

## The 4 Citation Slots

Each claim occupies a position in a 4-dimensional citation space. The slots identify the relational address at which the claim is evaluated:

| Slot | Edge Side | Address Component | Example |
|------|-----------|-------------------|---------|
| **C1** — Previous Group | top | `omi---imo` | The group from which the claim descends |
| **C2** — Previous Relation | left | `o---o/---/?---?@---@` | The relation frame that produced the claim |
| **C3** — Post Group | right | `omi---imo` | The group toward which the claim ascends |
| **C4** — Post Relation | bottom | `o---o/---/?---?@---@` | The relation frame consumed by the claim |

Every proof cell becomes a 4-slot addressable edge in the constitutional JSON Canvas:

```json
{
  "id": "Q1-A1-C1-C4-constructive",
  "fromNode": "omi---imo/Q1/A1/C1",
  "fromSide": "top",
  "toNode": "omi---imo/Q1/A1/C4",
  "toSide": "bottom",
  "toEnd": "arrow",
  "color": "4",
  "label": "constructive witness"
}
```

Where:
- `fromSide = top` = C1 (previous group)
- `fromSide = left` = C2 (previous relation)
- `toSide = right` = C3 (post group)
- `toSide = bottom` = C4 (post relation)
- `toEnd = arrow` = constructive/golden proof
- `toEnd = none` = falsification/negative proof
- `color` = gauge lane (preset 1-6) or modality (hex variant)

The 4 citation slots extend the 112 proof obligations to 448:

```text
8  ×  7  ×  4  ×  2  =  448
│     │     │     │
Q     A     C     P
u     l     i     r
e     g     t     o
s     o     a     o
t     r     t     f
i     i     i
o     t     o
n     h     n
s     m     s
            l
            o
            t
            s
```

Each Q × A cell now contains 8 sub-cells (4 citation pairs × 2 proof forms), each addressable as `Q{n}-A{m}-C{x}-C{y}-{constructive|falsification}`.

---

## The Full 448-Cell Matrix

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
> 4 citation slots frame each claim in relational space.
> 2 proof forms per lane (constructive + falsification) make every claim both buildable and break-testable.
> Therefore the framework targets **448 proofs**.

---

## Coq Proof Index

| Proof File | Primary Cells | Secondary Cells |
|-----------|--------------|-----------------|
| `axioms/verified_execution.md` | Q1A1c, Q1A1f, Q2A1c, Q2A1f, Q3A2c, Q3A2f | Q1A7c, Q1A7f |
| `axioms/omi_pi_proof.md` | Q2A1c, Q2A1f, Q4A5c, Q4A5f | Q1A5c, Q1A5f |
| `axioms/OMI_bialgebra.md` | Q8A1c, Q8A1f, Q4A3c, Q4A3f | Q8A3c, Q8A3f |
| `axioms/functorial_semantics.md` | Q6A6c, Q6A6f, Q4A3c, Q4A3f | Q1A3c, Q1A3f |
| `axioms/delta_orbit_theory.md` | Q2A1c, Q2A1f, Q1A1c, Q1A1f | Q4A1c, Q4A1f |
| `axioms/coalgebraic_bisimulation.md` | Q4A3c, Q4A3f, Q5A4c, Q5A4f, Q1A6c, Q1A6f | Q4A7c, Q4A7f |
| `axioms/AtomicKernel.md` | Q5A4c, Q5A4f, Q6A6c, Q6A6f, Q7A7c, Q7A7f | Q6A7c, Q6A7f |

---

## Cross-References to Canonical State Files

| State File | Constitutional Relevance |
|-----------|------------------------|
| `00-COSMOLOGY.md` | Documents the genesis of the 8 questions — what the author was discovering and why these invariants emerged from the void |
| `01-ONTOLOGY.md` | Names the entities — pointer, rule, proof, receipt, projection — that the constitution governs |
| `02-DOCTRINE.md` | Encodes the invariant laws that the 448 matrix formalizes as proof obligations |
| `03-FOUNDATIONS.md` | Provides the primitives (palindrome, omicron anchors, postulates, axioms) that underpin all 7 algorithms |
| `04-ATOMIC-KERNEL.md` | Defines the four irreducible objects (Null, Bit, Pair, Relation) that ground every algorithm |
| `05-PURE-ALGORITHMS.md` | Specifies the 7 canonical operations from which every algorithm is composed |
| `06-FORMAL-PROOFS.md` | Tracks the proof stack — what has been verified and what remains conjectural |
| `07-ISA.md` | Implements all 7 algorithms as an instruction set architecture — the machine that executes the constitution |
| `08-PROTOCOL.md` | Specifies the A2 control-plane and A4 escape algorithms — frame format, control markers, receipt packing |
| `09-OMI-LISP.md` | Defines the declaration surface — SExpr grammar, symbols, strings, decision tables |
| `10-BLACKBOARD.md` | Defines the evaluation surface — bitboards, bit-blips, addressed identity |
| `11-PROJECTION-FACES.md` | Specifies the A3 projection algorithm — how the invisible becomes visible |
| `12-GAUGE-INTERRUPTS.md` | Specifies the A4/A5 gauge selection surface — orientation, pleth, SOAP |
| `13-SURFACE-APPLICATIONS.md` | Derives the A1 transition algorithm (Delta Law), quadratic forms, Fano, factorial tower |
| `14-WAVE-SURFACE-INTERPRETER.md` | Applies A3 projection to analog signals — wave classification |
| `15-IMO-PORTS.md` | Applies A5/A6 to external nondeterminism — sensor, packet, file ports |
| `16-DISTRIBUTED-OPEN-WORLD.md` | Applies A6/A7 to multi-agent collaboration — proposals, receipts, reconciliation |
| `17-BUFFER-FRAMING.md` | Applies A2 control-plane to transport carriers — BLOBs, GLOBs, streams |
| `18-VERSION-CONTROL.md` | Seeds, citations, scopes, and receipts for versioning the canon |
| `19-CONSTITUTION.md` | This file — the verification grid itself, cross-referencing every state |
| `20-GLOSSARY.md` | Defines every term used in the constitutional grid — closes the vocabulary |

---

## Constitutional Amendments

The constitution may be extended through the proposal/receipt mechanism defined in A6. Any amendment must:
1. Specify which cells of the 448 matrix it affects
2. Provide both constructive and falsification proofs for each affected cell
3. Specify the 4 citation slots that frame the claim
4. Pass through the same verification grid as the original claims

The 8 invariant questions themselves are not amendable. They define what it means to be OMI. A system that changes the 8 questions is a different system.

---

## Decision Table Encoding

Each 448-cell constitutional cell may be encoded as a decision table in OMI-Lisp:

```omi
;; Q1-A1 decision table as Karnaugh map
;; 4 citation slots = 4 input variables
;; 2 proof forms = output column
(decision-table
  (name . "Q1-A1-source-of-truth-transition")
  (inputs . (C1 C2 C3 C4))
  (output . proof-form)
  (truth-operator . Vpq)  ;; Wittgenstein 14: OR — constructive over any slot
  (rules .
    ((TTTT . constructive)
     (TTTF . constructive)
     (TTFT . constructive)
     (TTFF . falsification)
     (TFTT . constructive)
     (TFTF . falsification)
     (TFFT . falsification)
     (TFFF . falsification)
     (FTTT . constructive)
     (FTTF . falsification)
     (FTFT . falsification)
     (FTFF . falsification)
     (FFTT . falsification)
     (FFTF . falsification)
     (FFFT . falsification)
     (FFFF . falsification))))
```

Each truth-gate file (FACTS.omi, RULES.omi, COMBINATORS.omi, CLOSURES.omi, CONS.omi) is a partial decision table — a Karnaugh map over the 4 citation slots. Adjacent cells in Gray-code order may be grouped for minimization, exactly as in a K-map.

---

## Compact Statement

> 8 questions ask what must remain true.
> 7 algorithms provide enforceable lanes for each answer.
> 4 citation slots frame each claim in relational space.
> 2 proof forms per lane (constructive + falsification) make every claim both buildable and break-testable.
> Therefore the framework targets **448 proofs**.

---

## Wittgenstein Alphabet

Each cell in the 448 matrix maps to one of the 16 Wittgenstein truth-functions, providing the local operator alphabet for that cell:

| Code | Operator | Tractatus | Truth | Role in Grid |
|------|----------|-----------|-------|-------------|
| 00 | ⊥ | Opq | FFFF | Contradiction — no Q×A cell can be satisfied |
| 01 | NOR | Xpq | FFFT | Joint denial — no citation slot holds |
| 02 | ↚ | Mpq | FFTF | Converse nonimplication — C1 excludes C2 |
| 03 | ¬p | Npq | FFTT | Negation — C1 is false, others irrelevant |
| 04 | ↛ | Lpq | FTFF | Material nonimplication — C1 excludes C4 |
| 05 | ¬q | Gpq | FTFT | Negation — C2 is false, others irrelevant |
| 06 | XOR | Jpq | FTTF | Exclusive disjunction — C1 xor C2 |
| 07 | NAND | Dpq | FTTT | Joint denial — not all slots hold |
| 08 | AND | Kpq | TFFF | Conjunction — all four slots hold |
| 09 | XNOR | Epq | TFFT | Equivalence — C1 iff C2 |
| 10 | q | Hpq | TFTF | Projection — C2 alone |
| 11 | p → q | Cpq | TFTT | Implication — C1 implies C2 |
| 12 | p | Ipq | TTFF | Projection — C1 alone |
| 13 | p ← q | Bpq | TTFT | Converse implication — C2 implies C1 |
| 14 | OR | Apq | TTTF | Disjunction — at least one slot holds |
| 15 | ⊤ | Vpq | TTTT | Tautology — every combination holds |

The 16-operator alphabet is the local truth code for every 448-cell constitutional claim. Each claim's operator is embedded in the node text as `o---o/FS:wittgenstein/GS:truth-table/RS:{00-15}/US:{operator}?truth@node@frame`.

---

*The algorithm is the source of truth.*
