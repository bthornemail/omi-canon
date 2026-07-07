# A1 — Transition Algorithm

## Definition

The transition algorithm advances canonical state under deterministic law. It is the core state machine of OMI.

## Specification

```text
Given: prior_state S at tick T
Law: Δ_C(x) = rotl(x,1) ⊕ rotl(x,3) ⊕ rotr(x,2) ⊕ C
      where C = 0x5A3C (or optionally a carried witness)

Compute: next_state = Δ_C(S, C)
Period: Δ_C^8(x) = x for all x in [0, 65535]

Envelope: Q_frame(S) = 0 must hold before transition
Receipt: Transition produces a receipt:
          provenance | steps:8 | LL:8 | NN:16 | MM:16
```

## Proof Obligations

| # | Question | Constructive | Falsification |
|---|----------|-------------|---------------|
| Q1 | Source of truth | Canonical state derived only from deterministic Δ_C over prior state + constants | Manual overwrite bypassing Δ_C yields replay mismatch |
| Q2 | System movement | delta/replay yields same next state for same input | Nondeterministic next-state fails parity/replay |
| Q3 | Control vs payload | State machine does not conflate parser mode with payload value | Mixed undecidable token semantics causes undefined transition |
| Q4 | Meaning across projections | Same seed/tick reproduces same canonical basis for interpretation | Same-input different-state falsifies deterministic anchor |
| Q5 | Intervention and replay | Post-interrupt continuation resumes at lawful next frame | Current-frame mutation bypassing transition causes replay drift |
| Q6 | Collaboration without authority | No collaborator bypasses law-defined transition mechanics | Direct state write outside transition path is invalid |
| Q7 | Branch and return | Each trace follows same Δ_C semantics | Branch with undefined transition basis is invalid |
| Q8 | Open meaning closed law | Law remains deterministic regardless of interpretive overlays | Interpretive layer altering Δ_C falsifies closure |

## Implementation Reference

See `08-ISA.md` for the C99 implementation of the Delta Law as opcodes `STATE_COMMIT` (0x1B) and `STATE_REVERT` (0x1C). See `07-GEOMETRY.md` for the mathematical derivation including period-8 verification, the weight block, and the prime 73 structure.

## Dependencies

- `07-GEOMETRY.md` — Delta Law specification
- `08-ISA.md` — Machine implementation
- `02-DOCTRINE.md` — Invariant rules (RULES.omi 0x05: delta-law-orbit)
