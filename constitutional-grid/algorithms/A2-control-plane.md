# A2 — Control-Plane Algorithm

## Definition

The control-plane algorithm separates structural channels and lanes from payload. It defines the typed marker set that governs how a frame is parsed.

## Specification

```text
Control markers:
  FS     0x05            Frame start        (segment 0 high byte)
  GS     0x2B            Group start         (segment 3 high byte)
  RS     0x2F            Record start        (segment 4 high byte)
  US     0x039F          Unit start          (segment 6)
  ESC    0x03BF (ο)      Escape prefix       (segment 1)
  NULL   0xFF            Scope terminator    (segment 7 low byte)

Interpretation state tuple:
  (channel :: lane :: mode :: scope :: numsys)

Channel/lane encoding (16-bit):
  channel 8 bits, lane 8 bits

Control-plane invariants:
  1. Control markers are typed — a byte IS its type, not "represents" it
  2. Control markers are fixed in position — segment i always means the same role
  3. No hidden control state — parser state is derivable from stream position
  4. Ambiguous bytes are rejected fail-closed
```

## Proof Obligations

| # | Question | Constructive | Falsification |
|---|----------|-------------|---------------|
| Q1 | Source of truth | Interpretation state is explicit in canonical tuple | Hidden parser state not derivable from stream is non-canonical |
| Q2 | System movement | Movement encoded within bounded symbolic control substrate | Out-of-band motion control not in stream is non-replayable |
| Q3 | Control vs payload | FS/GS/RS/US/ESC/NULL semantics are explicit and typed | Ambiguous control token interpretation rejected fail-closed |
| Q4 | Meaning across projections | Structural boundaries preserve semantic grouping | Boundary loss merges scopes and breaks invariants |
| Q5 | Intervention and replay | ESC is explicit structural access introducer | Implicit interrupt access without ESC is rejected |
| Q6 | Collaboration without authority | Scopes/roles are explicit in control context | Private unshared control channel is non-canonical |
| Q7 | Branch and return | Structural scopes preserve separation between layers | Cross-layer scope leakage causes fragmentation |
| Q8 | Open meaning closed law | Structural boundaries are bounded, interpretation is plural | Unbounded parser ambiguity destroys legal closure |

## Implementation Reference

See `06-PROTOCOL.md` for the full frame format specification, the 8 × 16-bit segment layout, and the control marker positions. See `04-FOUNDATIONS.md` for the palindrome structure and omicron anchors.

## Dependencies

- `06-PROTOCOL.md` — Frame format
- `04-FOUNDATIONS.md` — Primitives
- `truth-gates/RULES.omi` — Rule 0x02 (LL coherence), Rule 0x03 (constant alignment)
