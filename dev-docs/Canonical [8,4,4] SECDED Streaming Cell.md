# Canonical [8,4,4] SECDED Streaming Cell

## 1. Supersession Rule

The previous physical rail-storage presentation:

```text
LOW  = 2 4 6 Delta
HIGH = 1 3 5 Delta

logical ring:
Delta 1 2 3 4 5 6 Delta
```

is superseded as the canonical streaming representation.

It may remain as a historical visualization of odd/even branch ordering, but it
is not the executable streaming-cell layout.

The canonical executable word is the systematic extended Hamming `[8,4,4]`
cell:

```text
[LOGOS NOMOS FS PATHOS GS RS US OMINO]
```

The bit positions are fixed:

```text
bit 0  LOGOS
bit 1  NOMOS
bit 2  FS
bit 3  PATHOS
bit 4  GS
bit 5  RS
bit 6  US
bit 7  OMINO
```

## 2. Canonical Nomenclature

### OMINO Unified-Name Lock

There is one canonical name:

```text
OMINO
```

OMINO has two interpretations, produced by two views of the same OMI Object
Model structure:

```text
OMINO
├── Concentric Slide Rule interpretation
└── 3D Knowledge Cube interpretation
```

These are not two objects, identities, authorities, or centroids.

### Concentric Slide Rule Interpretation

Within the Concentric Slide Rule, OMINO is the fixed balance and orientation
reference:

```text
OMINO Centroid
pinch point: 0x00
azimuth: 0 degrees
```

In the extended Hamming streaming cell, the same OMINO appears at bit 7 as the
complete-cell balance hinge:

```text
bit 7
  OMINO
  overall parity coordinate
  perfect-balance hinge
```

Thus:

```text
Concentric Slide Rule OMINO
  fixed centroid reference
  complete circular balance
  overall parity closure
```

### 3D Knowledge Cube Interpretation

Within the 3D Knowledge Cube, OMINO is the poly-omino tile of the OMI Object
Model.

```text
OMINO
  one unified poly-omino tile
  self-contained 16-bit word-axis substrate
  16 Blackboard Face Planes
  18 Local240 Blackboard Faces
  72 Circular Slide Rulers
  4,320 local incidences
```

Thus:

```text
3D Knowledge Cube OMINO
  object-relative poly-omino
  unified local coordinate surface
  spatial interpretation of the same balance law
```

### Unified Meaning

```text
Concentric Slide Rule
  presents OMINO as circular balance and parity closure

3D Knowledge Cube
  presents OMINO as spatial poly-omino structure
```

The views are related as:

```text
one canonical OMINO
  -> circular interpretation
  -> spatial interpretation
```

Neither interpretation creates an additional object.

## 3. Nested CONS Cell

The cell is interpreted through two simultaneous CONS boundaries.

### Epistemic CONS

```text
Epistemic CONS
=
CAR(Feature Quartet)
.
CDR(Check Triad)
```

where:

```text
CAR:
  FS
  GS
  RS
  US

CDR:
  LOGOS
  NOMOS
  PATHOS
```

OMINO closes the complete seven-coordinate interior:

```text
OMINO
=
LOGOS
XOR NOMOS
XOR FS
XOR PATHOS
XOR GS
XOR RS
XOR US
```

### Stream CONS

```text
Stream CONS
=
CAR(active run)
.
CDR(continuation)
```

The Epistemic CONS defines one protected cell.

The Stream CONS connects the current protected cell to the next run without
converting the stream into a sequential semantic interpreter.

## 4. Absolute Bit-Vector Map

| Bit | Canonical coordinate | Hamming role   | OMI file alignment                   |
| --: | -------------------- | -------------- | ------------------------------------ |
|   0 | `LOGOS`              | `P1` parity    | Omnicron cadence                     |
|   1 | `NOMOS`              | `P2` parity    | Omnicron axis invariant              |
|   2 | `FS`                 | `D1` data      | `FACTS.omi`, `FACTS.imo`             |
|   3 | `PATHOS`             | `P4` parity    | Omnicron target stream               |
|   4 | `GS`                 | `D2` data      | `RULES.omi`, `RULES.imo`             |
|   5 | `RS`                 | `D3` data      | `COMBINATORS.omi`, `COMBINATORS.imo` |
|   6 | `US`                 | `D4` data      | `CLOSURES.omi`, `CLOSURES.imo`       |
|   7 | `OMINO`             | overall parity | `CONS.omi`, `CONS.imo`               |

The systematic Hamming positions are therefore:

```text
P1 P2 D1 P4 D2 D3 D4 P0
```

or canonically:

```text
LOGOS NOMOS FS PATHOS GS RS US OMINO
```

## 5. Check-Triad Equations

The parity coordinates are:

```text
LOGOS
=
FS XOR GS XOR US

NOMOS
=
FS XOR RS XOR US

PATHOS
=
GS XOR RS XOR US
```

During retrieval, the syndrome coordinates are:

```text
sLOGOS
=
LOGOS XOR FS XOR GS XOR US

sNOMOS
=
NOMOS XOR FS XOR RS XOR US

sPATHOS
=
PATHOS XOR GS XOR RS XOR US
```

The syndrome index is:

```text
syndrome
=
sLOGOS
OR (sNOMOS << 1)
OR (sPATHOS << 2)
```

Its range is:

```text
0..7
```

A nonzero syndrome identifies one of the seven interior Hamming positions.

## 6. OMINO Overall-Parity Law

The expected extended parity coordinate is:

```text
computed_omino
=
LOGOS
XOR NOMOS
XOR FS
XOR PATHOS
XOR GS
XOR RS
XOR US
```

The complete-cell parity witness is:

```text
overall_mismatch
=
OMINO XOR computed_omino
```

Equivalent full-byte reduction:

```text
overall_mismatch
=
LOGOS
XOR NOMOS
XOR FS
XOR PATHOS
XOR GS
XOR RS
XOR US
XOR OMINO
```

Interpretation:

```text
overall_mismatch = 0
  even complete-cell parity

overall_mismatch = 1
  odd complete-cell parity
```

Do not name this value `parity_valid` inside the arithmetic kernel. The name
`overall_mismatch` preserves the exact algebra and prevents inverted outcome
logic.

## 7. Complete SECDED Outcome Matrix

| Syndrome | Overall mismatch | Meaning                            | Deterministic action                              |
| -------: | ---------------: | ---------------------------------- | ------------------------------------------------- |
|      `0` |              `0` | no detected error                  | preserve word                                     |
|  nonzero |              `1` | single error in bits `0..6`        | flip syndrome-selected bit                        |
|      `0` |              `1` | single error in bit `7` (`OMINO`) | flip bit 7                                        |
|  nonzero |              `0` | detected double error              | preserve received word and emit double-error code |

The missing case in the earlier draft was:

```text
syndrome == 0
and
overall_mismatch == 1
```

This identifies an isolated error in the `OMINO` overall-parity bit.

A double error is:

```text
syndrome != 0
and
overall_mismatch == 0
```

It is detectable but not uniquely correctable by the `[8,4,4]` cell.

## 8. Branchless Retrieval Recipe

```text
INPUT:
  raw_8bit_stream_word

EXTRACT:
  LOGOS  = (word >> 0) & 1
  NOMOS  = (word >> 1) & 1
  FS     = (word >> 2) & 1
  PATHOS = (word >> 3) & 1
  GS     = (word >> 4) & 1
  RS     = (word >> 5) & 1
  US     = (word >> 6) & 1
  OMINO = (word >> 7) & 1

SYNDROME:
  sLOGOS  = LOGOS  XOR FS XOR GS XOR US
  sNOMOS  = NOMOS  XOR FS XOR RS XOR US
  sPATHOS = PATHOS XOR GS XOR RS XOR US

  syndrome =
      sLOGOS
      OR (sNOMOS << 1)
      OR (sPATHOS << 2)

OVERALL:
  computed_omino =
      LOGOS
      XOR NOMOS
      XOR FS
      XOR PATHOS
      XOR GS
      XOR RS
      XOR US

  overall_mismatch =
      OMINO XOR computed_omino
```

The interior correction mask is:

```text
interior_mask
=
overall_mismatch
AND nonzero(syndrome)
```

The OMINO correction mask is:

```text
omino_mask
=
overall_mismatch
AND zero(syndrome)
```

The correctable bit index is selected from:

```text
interior:
  syndrome - 1

overall:
  7
```

The double-error indicator is:

```text
double_error
=
nonzero(syndrome)
AND NOT overall_mismatch
```

`nonzero` and `zero` must be implemented using the project's declared
fixed-width mask law rather than a semantic branch inside the core kernel.

## 9. Core Versus Outside Form

The SECDED arithmetic belongs to the deterministic core:

```text
bit extraction
syndrome formation
OMINO reduction
correction-mask derivation
corrected-word derivation
error-class code derivation
```

Outside form may:

```text
display no error
display corrected
display OMINO corrected
display double error
stop an external stream
request retransmission
log a diagnostic
```

The deterministic core does not `HALT_CORE` as a semantic branch.

Instead, it emits a bounded algebraic classification code.

For example:

```text
00  no error
01  interior single error corrected
10  OMINO single error corrected
11  double error detected
```

The outside carrier or runtime policy determines what to do with that code.

## 10. Canonical File Alignment

```text
FS
  FACTS.omi
  FACTS.imo

GS
  RULES.omi
  RULES.imo

RS
  COMBINATORS.omi
  COMBINATORS.imo

US
  CLOSURES.omi
  CLOSURES.imo

LOGOS / NOMOS / PATHOS
  Omnicron cadence and Hamming check triad

OMINO
  CONS.omi
  CONS.imo
  extended overall-parity hinge
```

The tri-layer surface remains:

```text
*.omi
  declaration surface

*.imo
  definition surface

*.o
  condensed immutable target
```

## 11. Final Lock

```text
The Delta 1 2 3 4 5 6 Delta rail presentation is no longer
the canonical executable stream layout.

The canonical word is the systematic [8,4,4] SECDED cell:

  [LOGOS NOMOS FS PATHOS GS RS US OMINO]

FS, GS, RS, and US form the Feature Quartet.

LOGOS, NOMOS, and PATHOS form the Check Triad.

OMINO is the overall-parity balance hinge at bit 7.

OMINO remains the poly-omino tile and fixed 0x00 / 0-degree Centroid.

Circular balance and spatial form are two interpretations
of the same OMINO, not separate canonical names.

Every SECDED result is derived through fixed-width algorithmic
determinism.

Any reaction to the derived result enters from the outside in.
```
