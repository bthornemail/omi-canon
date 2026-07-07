# OMI Resolution Lineage

## Status

This document traces the **resolution climb** from the hidden packet root to the outermost interpretive envelopes.

The central claim:

> The 128-bit OMI wire frame is the immutable physical surface.
> Every higher factorial layer is an interpretive envelope derived deterministically from that frame.
> Increasing resolution does not change the frame. It changes the reading.

---

## omi — The Declaration Side

The resolution climb. Each step multiplies by a semantically meaningful integer.

### Layer 5! — The Hidden Packet Root (120)

```text
5! = 120 = 2³ × 3 × 5
```

Five is the hidden factor. It never appears as a visible stepping digit.

Role: **packet root / 5-cell simplex core** — the smallest complete semantic enclosure before orientation, sweep, replay, or clock phases.

Five semantic cells:

```text
1. subject seed
2. predicate seed
3. object seed
4. context/witness seed
5. closure/check seed
```

The 5! packet is a complete semantic unit:

```text
subject + predicate + object + context + closure
```

A five-fold rule asks: *Is the packet complete? Is the packet coherent?*

84

### Layer ×2 — Orientation / Complement

```text
×2 → 240 = 2 × 5! = 15 × 16 = 16² − 16
```

Role: **orientation bridge**. The hidden packet root acquires a binary complement/chirality. The five-fold becomes double-faced: every packet can be read forward or folded.

The 240-state bridge is where the five-fold packet root meets the four-fold nibble selector surface:

```text
five-fold side:  2 × 5! = 240     (packet root × orientation)
four-fold side:  15 × 16 = 240    (active nibble × full carrier)
```

Central equality:

```text
2 × 5! = 15 × 16 = 240
```

The 240 bridge is the active byte surface. 240 values carry oriented packet state. 16 values are reserved for control signals (null, stop, escape, reset, identity, gate, NaN, infinity, etc.).

### Layer ×3 — S-P-O Semantic Sweep (720)

```text
×3 → 720 = 3 × 240 = 6!
```

Role: **semantic sweep**. Each oriented packet state may be read through three roles:

```text
Subject — Predicate — Object
```

The S-P-O triple sweeps the 240-state surface. Every packet now has a grammatical position.

### Layer ×7 — Fano Replay Ring (5040)

```text
×7 → 5040 = 7 × 3 × 240 = 7!
```

Role: **Fano projective replay**. Seven Fano points, each carrying a complete S-P-O sweep of the 240-state surface.

Canonical slot formula:

```text
slot5040 = fano7 × 720 + role3 × 240 + local240

fano7    ∈ 0..6
role3    ∈ 0..2
local240 ∈ 0..239
```

### Layer ×8 — Physical Address Frame (40320)

```text
×8 → 40320 = 8 × 7 × 3 × 240 = 8!
```

Role: **physical 128-bit wire frame**. The 8-segment OMI address:

```text
S = [S₀, S₁, S₂, S₃, S₄, S₅, S₆, S₇]
```

Each segment is 16 bits. The frame is validated by the quadratic error function:

```text
Q_frame(S) = E_var + E_const
Q_frame(S) = 0  → valid
Q_frame(S) > 0  → malformed
```

This is the physical permutation universe. All 8 segments may be permuted. The frame is the immutable surface.

---

## --- — The Relational Bridge

The bridge between physical frame and interpretive envelopes is **derivation by modular arithmetic**.

The frame segments S₂, S₃, S₄, S₅ carry free variables (NNNN, LL-binding, LL-binding, MMMM). The Delta Law applied to these segments, reduced modulo {9, 10, 11, 12}, produces the four interpretive envelopes:

```text
route9       = Δ_C(S₂) mod 9
declaration10 = Δ_C(S₃) mod 10
witness11    = Δ_C(S₄) mod 11
phase12      = Δ_C(S₅) mod 12
```

These are **not stored** in the frame. They are **derived** from the frame. The same 128-bit wire generates the same four envelopes deterministically.

General formula for n ≥ 8:

```text
n! = (n × (n-1) × ... × 8) × 7 × 3 × 240
```

Every factorial from 8! upward is a product of the 240 bridge and a multiplier chain. The 128-bit frame anchors the chain.

---

## imo — The Mirror Side (Interpretive Envelopes)

The envelopes are the mirror. They wrap around the physical frame without changing it.

### Layer 9! — Route Envelope (362880)

```text
×9 → 362880 = 9 × 8 × 7 × 3 × 240
```

Role: **route/gate envelope**. Nine routing positions (including one closure). Derivation:

```text
route9 = Δ_C(S₂) mod 9
```

The route envelope selects which of nine paths a frame may take through the protocol layer.

### Layer 10! — Declaration Envelope (3628800)

```text
×10 → 3628800 = 10 × 9 × 8 × 7 × 3 × 240
```

Role: **declaration envelope**. Ten declaration positions:

```text
POSTULATE, AXIOM, RULE, FACT, DECLARATION,
TEST, REPLAY, PROJECTION, FAILURE, COMPLEMENT
```

Derivation:

```text
declaration10 = Δ_C(S₃) mod 10
```

### Layer 11! — Witness Envelope (39916800)

```text
×11 → 39916800 = 11 × 10 × 9 × 8 × 7 × 3 × 240
```

Role: **semantic/proof witness envelope**. Eleven witness positions carry the proof trail through the protocol stack.

Derivation:

```text
witness11 = Δ_C(S₄) mod 11
```

### Layer 12! — Clock Envelope (479001600)

```text
×12 → 479001600 = 12 × 11 × 10 × 9 × 8 × 7 × 3 × 240
```

Role: **clock/provider phase envelope**. Twelve phase positions correspond to the twelve regular divisors of 60 (the sexagesimal clock).

Derivation:

```text
phase12 = Δ_C(S₅) mod 12
```

---

## The Hidden Five

The factor 5 appears explicitly only in 5! = 120 = 2³ × 3 × 5. Every layer above 5! carries factor 5 implicitly inside the 240 constant:

```text
240 = 2 × 5! = 2 × 120
```

The decimal carrier of 1/73 confirms this:

```text
1 / 73 = 0.01369863 01369863 ...
Period = 8
Repeating block B = [0, 1, 3, 6, 9, 8, 6, 3]
Sum = 36
```

The period block contains **no digit 5**. This is not an omission. It is the signature of the hidden root: factor 5 is absorbed into 240 because 5 divides the base (10). The decimal stepping walks the residue structure after removing base factors.

Root vs step:

```text
5 is not a moving pointer.
5 is the rooted packet simplex.
```

---

## Why Resolution Increases Without Changing the Frame

The 128-bit wire frame is the physical surface. It carries S₀–S₇, each 16 bits. The Delta Law operates on this surface. The free variable segments (S₂, S₃, S₄, S₅) carry the seeds for the interpretive envelopes.

Resolution increases by:

```text
1. Validating the frame (Q_frame = 0)
2. Applying the Delta Law to free variable segments
3. Reducing modulo envelope size (9, 10, 11, 12)
4. Reading the oriented packet state (240 bridge)
5. Selecting the S-P-O role (3)
6. Selecting the Fano point (7)
7. Projecting the result through Q_xy
```

At no point does the frame mutate. The reading changes. The resolution increases. The source remains.

---

## Summary Table

```text
| Layer | Value | Multiplier | Derivation | Role                         |
|-------|-------|------------|------------|------------------------------|
| 5!    | 120   | (root)     | (hidden)   | packet root / simplex core   |
| 240   | 240   | ×2         | active     | orientation / byte surface   |
| 6!    | 720   | ×3         | from 240   | S-P-O semantic sweep         |
| 7!    | 5040  | ×7         | from 720   | Fano replay ring             |
| 8!    | 40320 | ×8         | (physical) | 128-bit wire frame           |
| 9!    | 362880| ×9         | Δ_C(S₂)    | route / gate envelope        |
| 10!   | 3.6M  | ×10        | Δ_C(S₃)    | declaration envelope         |
| 11!   | 39.9M | ×11        | Δ_C(S₄)    | witness / proof envelope     |
| 12!   | 479M  | ×12        | Δ_C(S₅)    | clock / provider envelope    |
```

The frame stays. The resolution climbs. The envelopes are derived, not stored.

---

## References

- `07-geometry/FIVE_FOLD_FOUR_FOLD_AND_THE_240_BRIDGE.md` — 240 bridge deep-doc
- `07-geometry/THE_DELTA_LAW.md` — Delta Law specification
- `07-geometry/THE_QUADRATIC_LAW.md` — Q_frame and Q_xy forms
- `04-foundations/OMICRON_AS_ZERO_FRAME.md` — omicron operator distinct from zero
- `04-foundations/NIBBLE_WHEEL_AND_DIAGONALS.md` — nibble carrier geometry
- `00-origin/Walking Tower of Powers Rooted.md` — source document for envelope derivation
- `00-origin/The Prime Factor Signature of 5 factorial and 73.md` — hidden five proof
- `00-origin/Whitepaper The 240 State.md` — 240-state complete treatment
- `AXIOMS.md` — fold axioms over the resolution stack
- `POSTULATES.md` — construction postulates including 240-Bridge
- `DECLARATIONS.md` — rule-to-fact derivation template
