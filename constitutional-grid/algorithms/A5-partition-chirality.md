# A5 — Partition & Chirality (Fano Selection) Algorithm

## Definition

The partition and chirality algorithm produces balanced partitions of the Fano plane and deterministic orientation derived from canonical state and tick. It governs how the system divides space and assigns directional labels.

## Specification

```text
Input: canonical_state :: 128-bit frame
       tick :: counter (mod 8)

Step 1 — Partition:
  Fano plane P has 7 points, 7 lines.
  Partition function F(S, tick) → (S₀, S₁):
    Subset S₀ and S₁ partition the frame segments
    Partition is balanced (half segments in each subset)

Step 2 — Chirality:
  chirality = f(kernel_state, tick)
  Returns orientation :: { ο (inbound), Ο (outbound) }

  Where:
    ο (U+03BF, 0x03BF) = chiral entry / inbound dataflow
    Ο (U+039F, 0x039F) = cardinal exit / outbound closure

  chirality determines ordered(S_chirality, S_other):
    S_chirality = subset with chirality label
    S_other = other subset

Invariants:
  - Partition is deterministic from same canonical state and tick
  - Chirality is kernel-derived, not user-specified
  - Chirality determinism per tick
  - Label invariance across projections
  - Replay invariance: same state + same tick = same chirality
```

## Proof Obligations

| # | Question | Constructive | Falsification |
|---|----------|-------------|---------------|
| Q1 | Source of truth | Partition topology deterministic; chirality kernel-derived per tick | Hardcoded ordering or non-kernel orientation is invalid |
| Q2 | System movement | Refinement shifts deterministic by tick with kernel-derived chirality | Arbitrary subset rotation or non-kernel first-set selection invalid |
| Q3 | Control vs payload | A5 controls partition/orientation only, does not parse stream classes | A5 as parser authority violates control-plane law |
| Q4 | Meaning across projections | Chirality deterministic while preserving canonical truth boundary | Projection/UI order changing A5 winner is invalid |
| Q5 | Intervention and replay | User/agent may influence advisory horizon only | Escape/local scope overriding chirality derivation is invalid |
| Q6 | Collaboration without authority | Shared selection context inspectable; chirality derivable from state | Opaque ordering or hidden chirality source is invalid |
| Q7 | Branch and return | Branch selection preserves origin and chirality provenance | Branch merge without chirality consistency is invalid |
| Q8 | Open meaning closed law | New partition schemes valid only with kernel-derived chirality | Extension introducing implicit ordering is invalid |

## Implementation Reference

See `07-GEOMETRY.md` for the full derivation of the Fano plane, the snub cube connection, the 240 bridge, the quadratic law Q_xy, and the `local240` computation. See `03-MANIFESTO.md` for the philosophical meaning of chirality as rotation over mutation.

## Dependencies

- `07-GEOMETRY.md` — Fano plane, snub cube, 240 bridge, quadratic law
- `03-MANIFESTO.md` — Chirality as philosophical principle
- `truth-gates/RULES.omi` — Rule 0x06 (fano-lottery-bound), Rule 0x0E (omicron-chirality-dataflow)
