# A7 — Branch/Reconciliation Algorithm

## Definition

The branch/reconciliation algorithm preserves the canonical reference while supporting persistent divergence and return. It is the constitutional mechanism for parallel exploration without fragmentation.

## Specification

```text
Branch record:
  base_index :: tick in canonical trace where branch began
  deltas :: set of receipted proposals applied on branch
  label :: optional human-readable branch name

Reconciliation input:
  canonical_tip :: canonical state at current tick
  branch :: { base_index, deltas, label }
  strategy :: { apply, squash, selective }

Reconciliation output:
  merged_state :: canonical_tip + select(deltas, strategy)

Merge strategies:
  apply     — Apply each delta sequentially to canonical_tip
  squash    — Compute net change of all deltas, apply once
  selective — Apply only selected deltas, reject others

Reconciliation invariants:
  - Canonical trace is never modified by reconciliation
  - Reconciliation produces a new canonical state (not an overlay)
  - Pre-reconciliation canonical state is preserved for replay
  - Receipted deltas are the only admissible branch contributions
```

## Proof Obligations

| # | Question | Constructive | Falsification |
|---|----------|-------------|---------------|
| Q1 | Source of truth | Canonical trace remains reference; branches explicitly anchored | Branch overwrite of canonical without merge law is invalid |
| Q2 | System movement | Canonical and branch traces each move lawfully from explicit roots | Untracked fork without base/root cannot be replayed |
| Q3 | Control vs payload | Deltas scoped by layer (canonical/branch/shared) | Cross-scope leakage of control intent without law is invalid |
| Q4 | Meaning across projections | Branch meaning diffable against canonical reference | Unanchored branch semantics without base comparison is invalid |
| Q5 | Intervention and replay | Interrupt can materialize fork without mutating canonical trace | Direct canonical overwrite via branch intent is invalid |
| Q6 | Collaboration without authority | Shared deltas published as explicit artifacts | Unscoped propagation without artifact law is invalid |
| Q7 | Branch and return | base_index + deltas + return remains explicit and replayable | Untracked irreconcilable fork without lineage metadata is invalid |
| Q8 | Open meaning closed law | Multiplicity of worlds preserves canonical center and return | Loss of canonical return path is fragmentation is invalid |

## Implementation Reference

See `09-ECOSYSTEM.md` for the branch and reconciliation architecture in the open world model, including agent collaboration patterns. See `08-ISA.md` for STREAM_SPLIT (0x1D) and STREAM_MERGE (0x1E) opcodes that implement branch/reconciliation at the machine level.

## Dependencies

- `09-ECOSYSTEM.md` — Open world model, agent collaboration
- `08-ISA.md` — Stream split/merge opcodes
- `02-DOCTRINE.md` — Invariant rules for reconciliation
- `truth-gates/RULES.omi` — All rules apply to both canonical and branch traces
