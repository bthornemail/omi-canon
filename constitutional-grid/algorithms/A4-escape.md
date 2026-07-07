# A4 — Escape Algorithm

## Definition

The escape algorithm opens a bounded interrupt scope and guarantees deterministic return. It is the constitutional mechanism for bounded non-closure.

## Specification

```text
Escape sequence:
  ESC <sub-instructions> [ESC]

Where:
  ESC = 0x03BF (omicron, ο)
  sub-instructions = zero or more bytes interpreted in escape context

Semantics:
  1. ESC enters escape scope
  2. Sub-instructions are read in escape context (may differ from data context)
  3. A second ESC terminates the scope
  4. Interpreter returns to data stream at the byte after the closing ESC

Literalization:
  ESC ESC in payload = literal byte value 0x03BF (not an escape)

Invariants:
  - ESC scope is bounded by structural marker, not time
  - ESC does not modify already-committed canonical state
  - Post-ESC, interpreter returns to deterministic movement
  - Unknown ESC targets are rejected (fail-closed)
```

## Proof Obligations

| # | Question | Constructive | Falsification |
|---|----------|-------------|---------------|
| Q1 | Source of truth | Interrupt semantics are law-defined (ESC + bounded scope + return) | Implicit escape or unclosed interrupt breaks decoding |
| Q2 | System movement | Interrupt scope returns to deterministic movement after closure | Unterminated/time-closed escape causes movement ambiguity |
| Q3 | Control vs payload | ESC ESC literalization preserves payload transparency of reserved token | Unknown escape targets rejected, preventing control/payload confusion |
| Q4 | Meaning across projections | Interrupt affects interpretation window, not committed prior frame | Escape mutating prior committed meaning violates replay boundary |
| Q5 | Intervention and replay | Finite scope + deterministic closure + return-to-data are enforced | Time-based closure or open-ended escape is rejected |
| Q6 | Collaboration without authority | Collaboration inside bounded interrupt window | Permanent never-closing control mode is invalid |
| Q7 | Branch and return | Branch creation is bounded action within interrupt/commit path | Never-closing branch mode without return path is invalid |
| Q8 | Open meaning closed law | Bounded non-closure only inside explicit escape scope | Escape without deterministic return is invalid |

## Implementation Reference

See `06-PROTOCOL.md` for the escape specification including the scope layout, the role of ο at segment 1, and the NULL scope terminator at segment 7 low byte. See `04-FOUNDATIONS.md` for the palindrome boundary rules and zero-frame concept.

## Dependencies

- `06-PROTOCOL.md` — Escape scope specification
- `04-FOUNDATIONS.md` — Palindrome boundary rules
- `03-MANIFESTO.md` — Philosophical justification for bounded non-closure (Q8)
