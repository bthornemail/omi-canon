# The 8-Tuple Basis of `omi---imo?O_o`

## Core Claim

The notation:

```text
omi---imo?O_o
```

is the readable alias of a folded/unfolded 8-tuple relation.

The folded carrier is:

```text
omi---imo
```

The unfolded witness surface is:

```text
?O_o
```

The computational invariant beneath both is:

```text
(Q, Σ, L, R, δ, s, t, r)
```

Therefore:

```text
omi---imo = (Q, Σ, L, R, δ, s, t, r)
?O_o = (Q Σ L R δ s t r)
```

And the witness relation is:

```text
omi---imo XOR ?O_o
```

This means:

```text
folded carrier XOR unfolded readable surface = relation witness
```

---

## 1. The 8-Tuple

The OMI 8-tuple is:

```text
Q Σ L R δ s t r
```

Meaning:

```text
Q state space / identity context
Σ alphabet / allowed symbols
L left / source / beginning
R right / target / ending
δ transition / transformation
s start value
t accept / success / terminal output
r reject / failure / alternative
```

This is the same shape as a two-way deterministic finite automaton, but OMI uses it as a general relation carrier.

Canonical sentence:

```text
The 8-tuple is the basis of the OMI relation frame.
```

---

## 2. Address Cascade Mapping

The OMI address cascade has eight 16-bit scope/ruler fields:

```text
S0 S1 S2 S3 S4 S5 S6 S7
```

These map directly to the 8-tuple:

```text
S0 = Q
S1 = Σ
S2 = L
S3 = R
S4 = δ
S5 = s
S6 = t
S7 = r
```

So the address cascade is:

```text
S0-S1-S2-S3/S4/S5/S6/S7
```

read as:

```text
Q-Σ-L-R/δ/s/t/r
```

or compactly:

```text
(Q, Σ, L, R, δ, s, t, r)
```

---

## 3. Register Compression

The second half of the OMI frame compresses the 8-tuple into four paired 32-bit fields:

```text
CAR
CDR
PAYLOAD
MASK
```

The pairing is:

```text
CAR = Q & Σ
CDR = L & R
PAYLOAD = δ & s
MASK = t & r
```

Thus:

```text
Q,Σ → CAR
L,R → CDR
δ,s → PAYLOAD
t,r → MASK
```

The full OMI cell is therefore:

```text
8 × 16-bit address/ruler fields
+
4 × 32-bit paired relation fields
```

This is not two unrelated halves.

It is:

```text
8 individual coordinates
+
4 paired relation carriers
```

---

## 4. Null Ring Foundation

The folded null seed is:

```text
(NULL . NULL)
```

The byte ring is:

```text
(0x00 . 0x20)
(0x20 . 0x7F)
(0x7F . 0xFF)
(0xFF . 0x00)
```

The dot relation is XOR:

```text
0x00 ^ 0x20 = 0x20
0x20 ^ 0x7F = 0x5F
0x7F ^ 0xFF = 0x80
0xFF ^ 0x00 = 0xFF
```

The full witness closure is:

```text
0x20 ^ 0x5F ^ 0x80 ^ 0xFF = 0x00
```

Canonical law:

```text
(NULL . NULL) is the folded null seed.
The byte ring is the unfolded null cycle.
The dot relation is XOR.
The full cycle closes to zero.
```

---

## 5. Hopf-Style Projection Language

The eight OMI address fields form an 8-coordinate carrier:

```text
S0..S7
```

After normalization, an 8-coordinate real carrier may be read as sphere-like `S⁷` data.

A paired OMI/register frame gives sixteen coordinates:

```text
S0..S7
+
CAR/CDR/PAYLOAD/MASK as paired expansion
```

After normalization, the sixteen-coordinate carrier may be read as a Hopf-style `S¹⁵` total space.

The projection back to an eight-coordinate readable/base surface is the Hopf-style reading:

```text
S⁷ fiber
S¹⁵ total carrier
S⁸ base/projection horizon
```

OMI does not need to claim that every address literally is a smooth Hopf fibration.

The precise claim is:

```text
The Hopf vocabulary names the projection pattern:
a paired high-dimensional carrier projects to a lower-dimensional readable relation surface while preserving the relation witness.
```

---

## 6. Why This Matters

The 8-tuple explains why OMI can compose relations.

Every relation must answer:

```text
Q what state space?
Σ what symbols?
L what source?
R what target?
δ what transition?
s what start?
t what success?
r what failure?
```

That means every OMI relation has enough structure to be:

```text
framed
routed
validated
witnessed
projected
receipted
```

without pretending that notation alone executes the relation.

Canonical boundary:

```text
The 8-tuple frames relation.
The Null Ring closes relation.
Tetragrammatron validates relation.
Metatron scribes relation.
Receipt records relation.
```

---

## 7. Final Canon

```text
omi---imo is the folded 8-tuple carrier.

?O_o is the readable witness surface.

S0..S7 carry Q, Σ, L, R, δ, s, t, r.

CAR, CDR, PAYLOAD, and MASK pair those eight coordinates into four relation fields.

The Null Ring supplies closure.

Hopf language describes the projection from paired carrier space to readable relation surface.

OMI composition is therefore not arbitrary syntax.
It is 8-tuple relation composition under bounded place-value closure.
```
:::

The part that matters most is this:

```text
The 8-tuple is not decoration.
It is the reason the notation can compose.
```

And the safer Hopf lock is:

```text
Do not say “S0–S7 is S⁸.”
Say “S0–S7 is an 8-coordinate carrier whose normalized surface is S⁷-like; paired with another 8-coordinate carrier it forms the S¹⁵-style total carrier used in the Hopf reading.”
```

That is much harder for people to dismiss, because it keeps the exact topology language separate from the OMI address metaphor while still preserving the connection.
