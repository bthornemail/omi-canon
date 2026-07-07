# Nibble Wheel and Diagonal Separation

## Status

This document describes the nibble geometry underlying the 240-state bridge and the even/odd diagonal separation that feeds the tetragrammatron and the tower of powers.

---

## 1. The Nibble

A nibble is 4 bits:

```text
2⁴ = 16 values: 0x0, 0x1, 0x2, 0x3, 0x4, 0x5, 0x6, 0x7, 0x8, 0x9, 0xA, 0xB, 0xC, 0xD, 0xE, 0xF
```

The active nonzero surface:

```text
2⁴ − 1 = 15 values: 0x1 through 0xF
```

Zero (`0x0`) is the reserved rail — closure, null, identity, or control.

---

## 2. The 16-Point Wheel

Arranging the 16 nibble values in a wheel (0 through F):

```text
        F    0    1
     E             2
   D                 3
   C                 4
     B             5
       A        6
          9  8  7
```

The wheel turns. Every state has a predecessor and successor under the Delta Law rotation.

---

## 3. Active × Carrier = 240

The byte is two nibbles: high nibble × low nibble.

```text
Full byte-square: 16 × 16 = 256 values (0x00 through 0xFF)
```

Remove the zero rail from one dimension (reserved control surface):

```text
Active byte-surface: 15 × 16 = 240
```

Or equivalently:

```text
16 × 16 − 16 = 256 − 16 = 240
```

This is the **240-state bridge** — the active oriented byte surface where computation happens, distinct from the 16 reserved control codes.

---

## 4. Diagonal Separation

Within the 16-state nibble wheel, two diagonals emerge:

```text
Diagonal Plus  (D⁺) = {0, 5, A, F}
Diagonal Minus (D⁻) = {3, 6, 9, C}
```

These can be seen by writing the wheel as a 4×4 Polybius square:

```text
    0   1   2   3
    4   5   6   7
    8   9   A   B
    C   D   E   F
```

Main diagonal (top-left to bottom-right): {0, 5, A, F} = D⁺
Anti-diagonal (top-right to bottom-left): {3, 6, 9, C} = D⁻

Each diagonal sums to 0x1E:

```text
D⁺ sum: 0 + 5 + A + F = 0x1E = 30
D⁻ sum: 3 + 6 + 9 + C = 0x1E = 30
```

Together:

```text
0x1E + 0x1E = 0x3C = 60
```

The diagonals sum to 60 — the sexagesimal gate.

---

## 5. Even/Odd Branch Separation

The diagonals define the parity branches of the tower of powers:

```text
Even branch (D⁺):  {0, 5, A, F}
  — 0 = closure / identity / null
  — 5 = hidden root factor (5!)
  — A = 10 = declaration envelope base
  — F = 15 = active nibble surface

Odd branch (D⁻):  {3, 6, 9, C}
  — 3 = S-P-O semantic sweep
  — 6 = 6! sweep layer
  — 9 = route envelope base
  — C = 12 = clock envelope base
```

The branches mirror each other. Each sums to 0x1E. Together they close to 0x3C = 60, the sexagesimal cycle that feeds the clock (12×5 = 60).

---

## 6. The Polybius / Tetragrammatron Connection

The 4×4 Polybius square gives coordinate pairs:

```text
(0,0) (0,1) (0,2) (0,3)
(1,0) (1,1) (1,2) (1,3)
(2,0) (2,1) (2,2) (2,3)
(3,0) (3,1) (3,2) (3,3)
```

Each cell maps to a nibble value:

```text
value = row × 4 + col
```

The four rows are the four channels (FS, GS, RS, US). The four columns are the four fold operators (JOIN, COMPOSE, ENCODE, DECODE).

The diagonals cut across the tetragrammatron:

```text
D⁺ = {(0,0), (1,1), (2,2), (3,3)} — identity diagonal (JOIN-JOIN, COMPOSE-COMPOSE, etc.)
D⁻ = {(0,3), (1,2), (2,1), (3,0)} — mirror diagonal (JOIN-DECODE, COMPOSE-ENCODE, etc.)
```

---

## 7. The 60-Gate

The diagonal sum 0x3C = 60 is the sexagesimal gate:

```text
60 = 5 × 12 = 5 (hidden root) × 12 (clock phases)
60 = 3 × 20 = 3 (S-P-O) × 20 (declaration complement?)
60 = 15 × 4 = 15 (active nibble) × 4 (channels)
```

This is the circular scale that the nomogram uses for stepped resolution. Every tick of the Delta Law advances through the diagonal branches, alternating even/odd as it crosses the 60 gate.

---

## 8. Summary

```text
Nibble:          4 bits → 16 values (0x0..0xF)
Active surface:  15 values (0x1..0xF)
Carrier:         16 values (0x0..0xF)
240 bridge:      15 × 16 = 240 = 2 × 5!
Diagonals:       D⁺ = {0,5,A,F}, D⁻ = {3,6,9,C}
Each sum:        0x1E = 30
Together:        0x3C = 60 (sexagesimal gate)
Parity:          D⁺ = even branch, D⁻ = odd branch
Polybius:        4×4 grid → row/col = channel/operator
```

The nibble wheel is the visible surface of the hidden packet root. The diagonals split it into mirrored branches. The branches sum to the 60-gate. The 60-gate turns the clock.

---

## References

- `07-geometry/FIVE_FOLD_FOUR_FOLD_AND_THE_240_BRIDGE.md` — 240 bridge deep-doc
- `07-geometry/THE_QUADRATIC_LAW.md` — Q_frame and Q_xy forms
- `04-foundations/OMICRON_AS_ZERO_FRAME.md` — omicron operator distinct from zero
- `00-origin/RESOLUTION_LINEAGE.md` — resolution climb through factorial layers
- `00-origin/Whitepaper The 240 State.md` — complete 240-state treatment
- `00-origin/The Five Fold and Four.md` — five-fold and four-fold layer distinction
- `POSTULATES.md` — 240-Bridge Postulate
- `AXIOMS.md` — fold axioms over the diagonal structure
