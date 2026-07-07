# State 13 — Surface Applications: The Rendered World

## What This State Is

This state is the transition from "which interpretation is selected" to "what world is rendered." After the gauge selects an orientation, the surface application is the mathematical geometry that drives the rendered projection — the Delta Law, the quadratic forms, the Fano incidence structure, and the 240-state bridge.

Surface applications are where the pure mathematics of the kernel and algorithms projects onto a readable world.

---

## Part I — The Delta Law

### 1.1 The Core Transition

The Delta Law is the minimal reversible transformation at the heart of OMI:

```
Δ_C(x) = rotl(x, 1) ⊕ rotl(x, 3) ⊕ rotr(x, 2) ⊕ C
```

Where:
- `rotl(x, n)` = circular left rotation by n bits on a 16-bit register
- `rotr(x, n)` = circular right rotation by n bits
- `⊕` = bitwise XOR
- `C` = carried closure witness (default C₀ = 0x5A3C)

### 1.2 The Four Design Choices

1. **Rotations, not shifts**: Shifts lose information. Rotations preserve information.
2. **XOR, not addition**: XOR is its own inverse (a ⊕ a = 0). This guarantees reversibility.
3. **Constant C**: Prevents the zero fixed point. Without C, Δ(0) = 0 breaks the orbit.
4. **16-bit mask**: Matches the OMI segment size.

### 1.3 Period-8 Property

Every 16-bit state returns to itself after exactly 8 applications of the Delta Law:

```
Δ⁸(x) = x for all x in [0, 65535]
```

This is not heuristic. The specific rotation distances (1, 3, 2) and XOR structure produce a cycle in GL(16,2) whose order divides exactly 8. Empirical verification over all 65536 states confirms period 8.

### 1.4 The Weight Block and Prime 73

The Delta Law produces a characteristic weight block:

```
1 / 73 = 0.01369863 01369863 …
Period = 8
Repeating block = [0, 1, 3, 6, 9, 8, 6, 3]
Sum = 36
```

The weight block W = 36 = 6! / 20 is the master frame stride:

```
position / 36 = macro-cycle
position % 36 = local weight
```

The decimal expansion of 1/73 contains no digit 5. This is the structural signature of the "hidden five."

### 1.5 Fano Resolution

The Delta Law converges within a bounded window determined by the Fano plane:

```
max steps = 2 × period − 1 = 15
```

For a given antecedent NN and consequent MM:

```
x₀ = NN
xᵢ₊₁ = Δ_C(xᵢ)
If xᵢ = MM within k < 15 steps → convergent
Otherwise → divergent (rejected)
```

The window of 15 steps maps to the Fano plane's 7 points × 2 orientations + 1 closure. Every convergent trajectory passes through the Fano structure within this window.

---

## Part II — The Quadratic Law

### 2.1 The Two Quadratic Forms

OMI uses two related quadratic forms:

**Frame validation:**

```
Q_frame(S) = E_var + E_const
```

Where E_var evaluates the free segments (S₂, S₃, S₄, S₅) and E_const evaluates the fixed segments (S₀, S₁, S₆, S₇).

**Spatial projection:**

```
Q_xy(x, y) = 60x² + 16xy + 4y²
           = 4(15x² + 4xy + y²)
```

### 2.2 The Spatial Form Coefficients

- **60x²**: The High / IMO domain. Sexagesimal spatial orientation.
- **4y²**: The Low / OMI domain. Localized atomic data.
- **16xy**: The cross-term. The bridge where projection meets data.

### 2.3 Properties of Q_xy

- Positive-definite matrix (determinant 176): elliptic paraboloid, no saddle points
- Q(0,0) = 0
- Q(3,3) = 720
- Q(x,y) is integer for x,y in 0..3
- Q(x,y) mod 240 ranges within 0..239

### 2.4 Projection from Q_xy

```
local240 = Q(x,y) mod 240
slot5040 = fano7 × 720 + role3 × 240 + local240
```

### 2.5 Cons Cell as Spatial Matrix

The cons cell is reinterpreted under Q_xy as a spatial matrix:

```
4y²      = low car/feature side
60x²     = high cdr/synset side
16xy     = browser-visible junction
```

---

## Part III — The 240-State Bridge

### 3.1 The Central Identity

```
2 × 5! = 15 × 16 = 240
```

This connects:
- **Five-fold side**: 2 × 5! = 240 (packet root × orientation/complement)
- **Four-fold side**: 15 × 16 = 240 (active nibble values × full carrier)

### 3.2 The Five-Fold Packet Root (5! = 120)

Five semantic cells form the smallest complete packet:

```
1. subject seed
2. predicate seed
3. object seed
4. context/witness seed
5. closure/check seed
```

### 3.3 The Four-Fold Selector Surface (4! = 24)

Four selector surfaces organize the four gauges:

```
FS (o---o) — object carrier boundary
GS (/---/) — path navigation
RS (?---?) — query/record
US (@---@) — socket/point
```

### 3.4 The Factorial Tower

```
0!  = 1      — identity
1!  = 1      — fixed point
2!  = 2      — distinction (Bit)
3!  = 6      — orientation
4!  = 24     — selector surface
5!  = 120    — packet root
6!  = 720    — Fano orbit
7!  = 5040   — master replay ring
8!  = 40320  — meta-operator shell (enter)
9!  = 362880 — meta-operator shell (examine)
10! = 3628800 — meta-operator shell (resolve)
11! = 39916800 — meta-operator shell (compose)
12! = 479001600 — projection limit
```

Above 12!, factorial values exceed 32-bit representation and are handled through the gauge's modular selection.

---

## Doctrine Sentence

> Surface applications are what the rendered world is made of: the Delta Law drives the orbit, the quadratic law locates the position, and the 240-state bridge maps the packet root onto the selector surface. The gauge orients. The geometry renders.
