# State 07 — Geometry: The Unfolding

## What This State Is

This state is the transition from "how it communicates" to "what mathematics emerges." After defining the protocol, I needed to unfold the full mathematical structure — the geometry that is latent in the primitives and must be derived, not asserted.

This is the largest state because geometry is where everything connects. The Delta Law forces period-8 orbits. The period-8 orbits force Fano structure. Fano structure forces the 240 bridge. The 240 bridge forces the factorial tower. The factorial tower forces the 5040 ring. The 5040 ring forces the replay geometry.

None of this was designed separately. It was derived from the first principles.

---

## Part I — The Delta Law

### 1.1 The Core Transition

The Delta Law is the minimal reversible transformation at the heart of OMI:

```text
Δ_C(x) = rotl(x,1) ⊕ rotl(x,3) ⊕ rotr(x,2) ⊕ C
```

Where:
- `rotl(x, n)` = circular left rotation by n bits on a 16-bit register
- `rotr(x, n)` = circular right rotation by n bits
- `⊕` = bitwise XOR
- `C` = carried closure witness (default C₀ = 0x5A3C)

### 1.2 The Four Design Choices

Each element of the Delta Law was deliberately chosen:

1. **Rotations, not shifts**: Shifts lose information (bits fall off the edge). Rotations preserve information (the edge returns through the orbit).
2. **XOR, not addition**: XOR is its own inverse (a ⊕ a = 0). This guarantees reversibility.
3. **Constant C**: Prevents the zero fixed point. Without C, Δ(0) = 0, which breaks the orbit.
4. **16-bit mask**: Matches the OMI segment size and fits within CPU register widths.

### 1.3 Period-8 Property

Every 16-bit state returns to itself after exactly 8 applications of the Delta Law:

```text
Δ⁸(x) = x for all x in [0, 65535]
```

This is not heuristic — it is a property of the specific rotation-XOR structure. The period is exactly 8 because:

- The rotation distances (1, 3, 2) and the XOR structure produce a cycle in GL(16,2)
- The order of the resulting linear transformation divides 8
- Empirical verification over all 65536 states confirms period 8

### 1.4 The Weight Block and Prime 73

The Delta Law produces a characteristic weight block derived from the decimal expansion of 1/73:

```text
1 / 73 = 0.01369863 01369863 ...
Period = 8
Repeating block B = [0, 1, 3, 6, 9, 8, 6, 3]
Sum = 36
```

The weight block `W = 36` = 6! / 20 is the master frame stride:

```text
position / 36 = macro-cycle
position % 36 = local weight
```

The decimal expansion of 1/73 contains no digit 5. This is the structural signature of the "hidden five" — factor 5 is absorbed into 240 at every layer above the root.

### 1.5 Fano Resolution

The Delta Law converges within a bounded window determined by the Fano plane:

```text
max steps = 2 × period − 1 = 15
```

For a given antecedent NN and consequent MM, the resolver iterates:

```text
x₀ = NN
xᵢ₊₁ = Δ_C(xᵢ)
If xᵢ = MM within k < 15 steps → convergent
Otherwise → divergent (rejected)
```

The Fano bound ensures that resolution is computationally bounded. No frame requires more than 15 iterations to determine acceptance.

### 1.6 The Bounded Fano Window

The window of 15 steps is not arbitrary. It maps to the Fano plane's 7 points × 2 orientations + 1 closure = 15. Every convergent trajectory passes through the Fano structure within this window.

---

## Part II — The Quadratic Law

### 2.1 The Two Quadratic Forms

OMI uses two related quadratic forms:

**Frame validation:**

```text
Q_frame(S) = E_var + E_const
```

Where E_var evaluates the free segments (S₂, S₃, S₄, S₅) and E_const evaluates the fixed segments (S₀, S₁, S₆, S₇).

**Spatial projection:**

```text
Q_xy(x, y) = 60x² + 16xy + 4y²
           = 4(15x² + 4xy + y²)
```

### 2.2 The Spatial Form Coefficients

The coefficients of Q_xy encode physical domain boundaries:

- **60x²**: The High/IMO domain. Sexagesimal spatial orientation. CSS `id` attribute surface.
- **4y²**: The Low/OMI domain. Localized atomic data. HTML `data-*` attribute surface.
- **16xy**: The cross-term. The CSSOM/JSDOM bridge where code meets DOM.

### 2.3 Properties of Q_xy

- Positive-definite matrix (determinant 176): elliptic paraboloid, no saddle points
- Q(0,0) = 0
- Q(3,3) = 720
- Q(x,y) is integer for x,y in 0..3
- Q(x,y)/6 lies within 0..120 for x,y in 0..3
- Q(x,y) mod 240 ranges within 0..239

### 2.4 Projection from Q_xy

```text
local240 = Q(x,y) mod 240
slot5040 = fano7 × 720 + role3 × 240 + local240
```

The quadratic form is the bridge between abstract OMI addresses and concrete DOM coordinates. The sexagesimal coefficient 60 ensures that coordinate subdivisions never produce fractional truncation errors.

### 2.5 Cons Cell as Spatial Matrix

The cons cell is reinterpreted under Q_xy as a spatial matrix:

```text
4y²      = low car/feature side
60x²     = high cdr/synset side
16xy     = browser-visible junction
```

The `()! = Q(x,y)` analogy ties the void-factorial cons identity to the coordinate surface. The empty cons is not zero — it is the origin of the coordinate system.

---

## Part III — The 240-State Bridge

### 3.1 The Central Identity

```text
2 × 5! = 15 × 16 = 240
```

This is the central numerical identity of the OMI geometry. It connects two seemingly different structures:

- **Five-fold side**: 2 × 5! = 240 (packet root × orientation/complement)
- **Four-fold side**: 15 × 16 = 240 (active nibble values × full carrier)

Both converge on the same 240-state bridge.

### 3.2 The Five-Fold Packet Root (5! = 120)

Five semantic cells form the smallest complete packet:

```text
1. subject seed
2. predicate seed
3. object seed
4. context/witness seed
5. closure/check seed
```

A five-fold rule asks: "Is the packet complete? Is the packet coherent?"

### 3.3 The Four-Fold Selector Surface (4! = 24)

Four selector surfaces organize the four gauges:

```text
FS (o---o) — object carrier boundary
GS (/---/) — path navigation
RS (?---?) — query/record
US (@---@) — socket/point
```

A four-fold fact asks: "Is the packet visible? Is it projected?"

### 3.4 The Bridge

The 240 bridge is where the five-fold packet root meets the four-fold selector surface:

- From the five-fold side: the oriented packet surface
- From the four-fold side: the active byte surface

Both converge on 240, which then expands:

```text
240 → ×3 → 720 (S-P-O semantic sweep)
720 → ×7 → 5040 (Fano replay ring)
```

### 3.5 240 as Active Surface

```text
240 = 16² − 16
```

240 values carry oriented packet state. 16 values are reserved for control signals (null, stop, escape, reset, identity, gate, NaN, infinity, etc.).

The 240-state bridge is the active byte surface — the place where the packet becomes interpretable through the four-fold selector.

---

## Part IV — The Fano Plane

### 4.1 The 7-Point Projective Plane

The Fano plane is the smallest finite projective plane: 7 points, 7 lines, 3 points per line, 3 lines per point.

```text
Points: 0, 1, 2, 3, 4, 5, 6
Lines: {0,1,3}, {1,2,4}, {2,3,5}, {3,4,6}, {4,5,0}, {5,6,1}, {6,0,2}
```

### 4.2 Fano in OMI

The Fano plane appears in OMI as:

- **7 replay slots** in the 5040 ring (fano7 × 720)
- **7 delta steps** in the resolution window (max 15 = 2 × 7 + 1)
- **7 Fano points** each carrying a complete S-P-O sweep of the 240-state surface

### 4.3 Fano Lottery

The "Fano lottery" is the non-deterministic selection of Fano point during resolution. Each valid frame converges to a specific Fano point based on the LL-modulated Delta walk. The point is not pre-assigned — it emerges from the resolution.

---

## Part V — Projective Closure

### 5.1 The Principle

In any bounded OMI wheel, one state is reserved as the **projective center / closure state**:

```text
16 states: 15 active, 1 closure
8 states:  7 active, 1 closure
```

The missing state is not lost. It is the projective center that makes the wheel a closed surface rather than a linear range.

### 5.2 The Empty List Principle

This is the OMI generalization of Lisp's `nil == ()`:

```text
() is both an atom and a list.
```

The closure state is both a point (one state among many) and a space (the center that makes the surface closed).

### 5.3 Projective Closure in Practice

The Delta Law's use of rotations (not shifts) is the operational expression of projective closure:

- Rotations preserve all bits
- Nothing falls off the edge
- The edge returns through the orbit

The zero-point `Ω₀ = 0! = omi---imo` is the empty list principle applied to the whole OMI frame: one bounded relation that is both origin and container.

---

## Part VI — The Factorial Tower

### 6.1 The Resolution Climb

```text
| Layer | Value | Multiplier | Role                         |
|-------|-------|------------|------------------------------|
| 5!    | 120   | (root)     | packet root / simplex core   |
| 240   | 240   | ×2         | orientation / byte surface   |
| 6!    | 720   | ×3         | S-P-O semantic sweep         |
| 7!    | 5040  | ×7         | Fano replay ring             |
| 8!    | 40320 | ×8         | 128-bit wire frame           |
| 9!    | 362880| ×9         | route / gate envelope        |
| 10!   | 3.6M  | ×10        | declaration envelope         |
| 11!   | 39.9M | ×11        | witness / proof envelope     |
| 12!   | 479M  | ×12        | clock / provider envelope    |
```

### 6.2 Envelope Derivation

The interpretive envelopes (9! through 12!) are derived from the Delta Law applied to free frame segments:

```text
route9       = Δ_C(S₂) mod 9
declaration10 = Δ_C(S₃) mod 10
witness11    = Δ_C(S₄) mod 11
phase12      = Δ_C(S₅) mod 12
```

These are not stored in the frame. They are derived from the frame. The same 128-bit wire generates the same four envelopes deterministically.

### 6.3 The General Formula

For n ≥ 8:

```text
n! = (n × (n-1) × ... × 8) × 7 × 3 × 240
```

Every factorial from 8! upward is a product of the 240 bridge and a multiplier chain. The 128-bit frame anchors the chain.

### 6.4 The Hidden Five

Factor 5 appears explicitly only in 5! = 120. Every layer above 5! carries factor 5 implicitly inside the 240 constant:

```text
240 = 2 × 5! = 2 × 120
```

The decimal expansion of 1/73 confirms this: the repeating block [0,1,3,6,9,8,6,3] contains no digit 5. This is not an omission. It is the signature of the hidden root.

> 5 is not a moving pointer. 5 is the rooted packet simplex.

---

## Part VII — The Snub Geometry

### 7.1 Snub vs. Truncation

In geometry, truncation cuts off corners. Snub operation rotates faces.

OMI uses snub as its primary geometric operation because:
- Truncation creates new faces at old vertices
- Snub creates chiral pairs (left/right orientations)
- Snub preserves the original polyhedron's structure while adding orientation

### 7.2 The Snub Cube and Snub Dodecahedron

The snub cube (Archimedean solid) and snub dodecahedron are the geometric analogs of OMI's orientation bridge:

- 24 vertices of the snub cube → 24 active states in the 4-fold selector
- 60 vertices of the snub dodecahedron → 60 = sexagesimal gate

### 7.3 Chirality Selection

The snub operation always produces two enantiomorphic (mirror) forms. In OMI:

- Forward orbit = left-handed chirality
- Reverse orbit = right-handed chirality
- The omicron anchors select the chirality (ο = entry, Ο = exit)

Chirality is not disagreement — it is oriented complementarity. Peers may hold different orientations while sharing the same accepted center.

---

## Part VIII — The Sexagesimal System

### 8.1 Base-60 in OMI

Sexagesimal (base-60) is the runtime cadence of OMI:

```text
steps 0..59
```

Derived from Hellenistic Greek astronomical notation, sexagesimal provides:

- **Superior highly composite base**: 60 has 12 divisors (more than any smaller number)
- **No fractional truncation**: 60 is divisible by 2,3,4,5,6,10,12,15,20,30
- **Clock correspondence**: 60 seconds, 60 minutes — the orbital time structure

### 8.2 The Sexagesimal Gate

```text
0x1E + 0x1E = 0x3C = 60
```

The sexagesimal gate is the diagonal sum that appears at multiple levels:

- 60 = 5! / 2 (half the packet root)
- 60 = 3 × 4 × 5 (smallest Pythagorean triple product)
- 60 = coefficient of x² in Q_xy
- 60 = the diagonal sum of the nibble wheel

### 8.3 Sexagesimal in the Factorial Tower

The sexagesimal structure propagates through the tower:

```text
12 × 5 = 60        (sexagesimal gate)
12 × 60 = 720      (6! = S-P-O sweep)
7 × 720 = 5040     (7! = Fano replay ring)
```

---

## Part IX — Unicod as Incidence Geometry

### 9.1 The Incidence View

Unicod is not merely a character set. Under OMI, it is a **rewrite manifold**:

- Codepoints = points in an incidence space
- Blocks/rows = lines in that space
- Direction markers = orientation selectors
- Private-use regions = bounded regions for protocol-defined notation

### 9.2 The OMI Use of Unicod

OMI uses specific Unicod codepoints as operators:

| Codepoint | Glyph | Role |
|-----------|-------|------|
| U+03BF | ο | Small omicron — chiral entry |
| U+039F | Ο | Capital omicron — cardinal exit |
| U+03BC | μ | Micro — small-scale operator |
| U+03C0 | π | Pi — period/cycle operator |
| U+03A3 | Σ | Sigma — summation/aggregation |
| U+0394 | Δ | Delta — transition operator |

These are not decorative. They are operational markers that select interpretation surfaces.

---

## Part X — The OMI Nomogram

### 10.1 The Slide Rule Surface

The Omi-Nomogram is the runtime scale selector — the equivalent of a slide-rule scale table:

```text
0x30 identity / unity
0x31 C/D multiply-divide
0x32 A/B square-root
0x33 K cube-root
0x34 folded pi scale
0x35 reciprocal scale
0x36 sine/cosine
0x37 tangent/cotangent
0x38 small-angle / degree-radian
0x39 Pythagorean
0x3A log10
0x3B natural log / exponential
0x3C sexagesimal gate
0x3D arbitrary powers
0x3E quadratic / gnomon
0x3F LFSR / period / replay
```

### 10.2 Scale Selection

The scale is selected by the slash path:

```text
omi-<frame>-imo/<control>/<scale>/<relation>/<unit>
```

The `<scale>` segment selects which nomogram scale is active. The scale does not store the result — it declares how the result is read.

---

## Part XI — The Trigintaduonion Bridge

### 11.1 The 32-Dimensional Algebra

Trigintaduonions are a 32-dimensional algebra that provides the operator scaffold for OMI:

- 32 dimensions correspond to the 32 opcodes in the OMI ISA
- The multiplication table produces 155 distinguished triples
- These triples correspond to PG(4,2) incidence lines

### 11.2 PG(4,2) Projective Geometry

PG(4,2) is the 5-dimensional projective space over GF(2):

- 31 points (32 − 1)
- 155 lines (each with 3 points)
- The 155 triples from the trigintaduonion multiplication table

### 11.3 The Fano Lottery on Triakis Tetrahedron

The 155 PG(4,2) lines → Fano lottery on the triakis tetrahedron:

- Each triple is a constraint solution, not an object
- The triples must be derived, not hard-coded
- The triakis tetrahedron provides the geometric scaffold

---

## Part XII — The 5040 Slot Formula

### 12.1 The Complete Decomposition

```text
slot5040 = fano7 × 720 + role3 × 240 + local240

fano7    ∈ 0..6      (7 Fano points)
role3    ∈ 0..2      (3 S-P-O roles)
local240 ∈ 0..239    (240 oriented byte states)
```

### 12.2 Slot Assignment

The slot assignment is deterministic:

1. Extract `(LL, NN, MM)` from the validated frame
2. Run `Delta_C(NN)` for up to 15 steps
3. On convergence to MM, record `steps` and derive `fano7`
4. `role3` = LL & 0x3 (low 2 bits of the scope selector)
5. `local240` = Q_xy(LL >> 4, LL & 0xF) mod 240
6. Compute slot5040
7. Write receipt to slot

---

## The Transition to State 08

From this state — having unfolded the mathematical geometry — I moved to State 08 (The Machine) to answer: how does this become executable? What does the machine look like?

Continue to `08-ISA.md`.
