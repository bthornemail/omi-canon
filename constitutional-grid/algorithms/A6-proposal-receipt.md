# A6 — Proposal/Receipt Algorithm

## Definition

The proposal/receipt algorithm converts interventions into inspectable deferred artifacts. It is the constitutional mechanism for auditable state change.

## Specification

```text
Proposal:
  Frame with proposal flag set in control segment
  Contents: proposed state change + issuer identifier

Receipt:
  provenance :16 | steps :8 | LL :8 | NN :16 | MM :16

  Where:
    provenance = identifier of the proposing agent
    steps      = number of ticks until commit
    LL         = lane label
    NN         = free variable (segment 2)
    MM         = free variable (segment 5)

Lifecycle:
  1. Proposer issues proposal frame
  2. System validates proposal (law compliance)
  3. If valid: system issues receipt (acceptance)
     If invalid: system issues rejection receipt
  4. On commit: system applies proposed change to canonical state
  5. On rejection: system discards proposal (no state change)

Invariants:
  - No state transition occurs without a proposal-receipt pair
  - Proposals are explicit frames, not inline control bytes
  - Commit is deferred (never same-frame as proposal)
  - Rejection produces a receipt (rejection is explicit)
```

## Proof Obligations

| # | Question | Constructive | Falsification |
|---|----------|-------------|---------------|
| Q1 | Source of truth | Proposed changes are explicit artifacts before application | Silent unreceipted mutation has no lawful proof trail |
| Q2 | System movement | Interventions move state only at lawful deferred commit points | Mid-frame direct mutation bypassing defer/commit breaks law |
| Q3 | Control vs payload | Proposals are explicit objects, not hidden inline control bytes | Inline hidden commands without artifact schema are invalid |
| Q4 | Meaning across projections | Semantic changes are explicit proposals with receipts before commit | Unreceipted semantic drift cannot be verified |
| Q5 | Intervention and replay | Intervention becomes deferred artifact, then accepted/rejected | No proposal/receipt means no lawful intervention transition |
| Q6 | Collaboration without authority | Accept/reject/commit trail is receipted and auditable | Silent acceptance or hidden commit path is invalid |
| Q7 | Branch and return | Branch differences are receipted and diffable | Undiffable branch mutation without receipts is invalid |
| Q8 | Open meaning closed law | Differences are negotiable, receipted, accountable | Free-form mutation without artifacts/receipts is invalid |

## Implementation Reference

See `06-PROTOCOL.md` for the receipt format including the 64-bit receipt structure, the slot5040 derivation, and the frame validation rules. See `08-ISA.md` for the PROBE (0x01), PROBE_ACK (0x02), SYNC_COMMIT (0x03), and SEAL (0x04) opcodes that participate in the proposal/receipt lifecycle. See `09-ECOSYSTEM.md` for the multi-agent proposal/receipt usage in the open world model.

## Dependencies

- `06-PROTOCOL.md` — Receipt format, slot5040 ring
- `08-ISA.md` — Opcodes for proposal/receipt operations
- `09-ECOSYSTEM.md` — Multi-agent collaboration model
- `truth-gates/RULES.omi` — Rule 0x07 (receipt-packing-format), Rule 0x08 (slot5040-derivation)
