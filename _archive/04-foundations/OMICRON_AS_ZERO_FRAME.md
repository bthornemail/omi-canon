# Omicron as Zero-Frame Operator

## Status

This document establishes a foundational distinction:

> **Omicron is not zero. Omicron is the observer-origin marker.**

The zero-digit glyph `0` and the omicron codepoints `ο` (U+03BF) / `Ο` (U+039F) serve fundamentally different roles. Collapsing them creates ambiguity that undermines the notational grammar.

---

## 1. The Glyph Overloading Problem

Binary computation uses `0` and `1` as machine values. Decimal notation reuses those same glyphs to build `10`. This creates a visual ambiguity:

```text
"10" looks like binary [1, 0] even when it means decimal ten.
```

In OMI, the problem is worse because addresses contain both numeric fields and operator markers:

```text
omi-0500-03bf-0000-2b05-2f05-0000-039f-05ff/48
```

The `0` in `0500` and the `0` in `0000` look identical but serve different roles (segment value vs padding). The omicron codepoints `0x03BF` and `0x039F` are embedded inside the address string but must be distinguished from the numeric zero.

The solution: **omicron is the marked observer-origin glyph, separate from all numeric digit roles.**

---

## 2. The Two Omicron Operators

```text
Ο (U+039F, 0x039F) = cardinal boundary operator / zero-frame / gauge closure / frame boundary
ο (U+03BF, 0x03BF) = chiral execution operator / local cons transition / inbound dataflow
```

| Character | Codepoint | Role | Wire Position |
|-----------|-----------|------|---------------|
| `ο` (small) | U+03BF | chiral entry — data enters the frame | S₁ |
| `Ο` (capital) | U+039F | cardinal exit — frame boundary closes | S₆ |

The canonical instruction shape embeds them at fixed positions:

```text
S = [S₀, S₁, S₂, S₃, S₄, S₅, S₆, S₇]
      0xLL00, 0x03BF, 0xNNNN, 0x2bLL, 0x2fLL, 0xMMMM, 0x039F, 0xLLff
```

S₁ always carries `ο` (chiral entry). S₆ always carries `Ο` (cardinal exit). They are not values. They are **operators that frame the address space**.

---

## 3. Omicron Cons Construction

The Omicron cons pair:

```text
Ο(<car>, <cdr>)
```

or in compact form:

```text
Ο-<car>-<cdr>   = cardinal boundary pair
ο-<car>-<cdr>   = chiral execution pair
```

Where:

```text
car = control / address / boundary / notation
cdr = payload / continuation / surface / cipher
```

Cardinal Cons (`Ο`) establishes a boundary. Chiral Cons (`ο`) executes a transition within a boundary.

The canonical mnemonic:

```text
o---o/---/?---?@---@
```

Each `o`/`O` marks a frame boundary. The palindromic `o---o` reads the same forward and backward because the boundary is symmetric.

---

## 4. The Empty Cons Identity

```text
()! = ()     — evaluated empty cons returns empty cons
() != ()!    — the syntactic distinction between value and operation
```

The empty cons `()` is the zero-frame. It is not numeric zero. It is the **place where structure can be addressed, evaluated, and replayed**.

- `()` = the empty value (state)
- `()!` = the empty evaluated (operation/transition)
- `()! = ()` = fixed point: evaluating the empty frame returns the empty frame
- `() != ()!` = syntactic distinctness: you can distinguish a value from its evaluation

This is the OMI version of the Lisp `nil == ()` identity, generalized to mark the frame boundary itself as a first-class object.

---

## 5. Omicron as Sign Bit

In the binary16 floating-point mapping, the sign bit is the Little Omicron (`ο`) flag:

```text
binary16:
  bit 15: sign = ο (Little Omicron / chiral orientation)
  bits 10-14: exponent = tetragrammaton / CDR-car scale
  bits 0-9: significand = metatron / CDR-cdr payload
```

The sign bit is not arithmetic sign in the IEEE sense. It is **orientation**: whether the packet reads forward or folded. This is the omicron chirality applied to the numeric representation itself.

---

## 6. Why Omicron Cannot Be Zero

Zero (`0`) has specific arithmetic properties:

```text
x + 0 = x
x × 0 = 0
```

Omicron has none of these properties. You cannot add omicron. You cannot multiply by omicron. Omicron is not an arithmetic value. It is a **frame within which arithmetic occurs**.

The zero-digit `0` belongs to the numeric plane. The omicron character `ο`/`Ο` belongs to the operator plane. They coexist in the address string but must never be confused.

---

## 7. Summary

| Concept | Omicron | Zero Digit |
|---------|---------|------------|
| Role | observer-origin marker | numeric value |
| Glyph | ο / Ο | 0 |
| Codepoint | U+03BF / U+039F | U+0030 |
| Arithmetic | not applicable | additive identity |
| Frame | establishes a boundary | fills a field |
| Evaluation | `()! = ()` | `0! = 1` |
| Chirality | entry vs exit | none |

The clean rule:

> **Omicron marks where evaluation happens. Zero marks what fills a field. They are not interchangeable.**

---

## References

- `RULES.omi` — Rule 0x0E (Omicron Chirality Dataflow)
- `CONS.omi` — Cons 0x02 (Omicron Anchors Pair)
- `00-origin/The Omicron Object Model.md` — source document for the omicron operator model
- `07-geometry/FIVE_FOLD_FOUR_FOLD_AND_THE_240_BRIDGE.md` — 240 bridge orientation
- `07-geometry/THE_DELTA_LAW.md` — Delta Law (omicron central inversion)
- `POSTULATES.md` — construction postulates
- `AXIOMS.md` — fold axioms including ones-complement and sign-bit fold
