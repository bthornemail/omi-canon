# OMI Relational Access Envelope

Status: Definitive canon doctrine  
Layer: Citation / protocol core / object model  
Verification target: constitutional grid, later pass

## Core Rule

The citation identity is:

```text
|OMI---IMO>
```

No hash, checksum, digest, signature, metadata object, cache key,
fingerprint, encrypted label, or overloaded OMI-native object is protocol
identity.

The protocol core needs only:

```text
addressed relation
gauge preheader
place-value frame
```

Everything else is carrier behavior, projection behavior, debugging metadata,
or external compatibility material.

## Algebraic Core

The relational access envelope reduces to:

```text
|OMI---IMO>
=
Gauge
+
Place Value
+
Relation
```

Where:

```text
Gauge:
F* 00 1C 1D 1E 1F 20 F*

Place Value:
o---o/---/?---?@---@

Relation:
S0..S7?PAYLOAD?MASK@CAR@CDR
```

The 512-bit envelope is the carrier/access realization of this smaller
algebraic core.

## Canonical Relational Access Envelope

The canonical envelope is:

```text
|OMI---IMO>
  -> gauge_preheader: F* 00 1C 1D 1E 1F 20 F*
  -> place_value_frame: o---o/---/?---?@---@ / S0..S7?PAYLOAD?MASK@CAR@CDR
```

The fixed OMI carrier prefix header is:

```text
FF 00 1C 1D 1E 1F 20 FF
```

Readable:

```text
GAUGE NUL FS GS RS US SP GAUGE
```

The active gauge preheader is:

```text
F* 00 1C 1D 1E 1F 20 F*
```

`F*` selects the local Wittgenstein operator lane. The carrier prefix uses
`FF` as the canonical sealed prefix. A different active `F*` may stage a local
operator lane, but it does not introduce another identity channel.

## 512-Bit Relational Access Envelope

OMI standardizes a 512-bit relational access envelope:

```text
512 bits = 64 bytes
```

It divides into two 256-bit halves:

```text
first 256 bits  = prefix / gauge / orientation half
second 256 bits = OMI-IMO place-value frame half
```

The first half orients access:

```text
carrier prefix
active gauge lane
FS/GS/RS/US scope staging
stream/frame orientation
```

The second half stages the addressed frame:

```text
S0 S1 S2 S3 S4 S5 S6 S7 PAYLOAD MASK CAR CDR
```

Expanded:

```text
S0..S7?PAYLOAD?MASK@CAR@CDR
```

The envelope stages access. It does not accept state.

Validation determines.

Omi-Attestation witnesses.

Accepted Omi-State may be recorded.

## Place-Value Frame

The readable minimal frame is:

```text
o---o/---/?---?@---@
```

The expanded place-value frame is:

```text
S0..S7?PAYLOAD?MASK@CAR@CDR
```

Together:

```text
o---o/---/?---?@---@ / S0..S7?PAYLOAD?MASK@CAR@CDR
```

This is the addressable relation surface. It is not a label for an object. It
is the relation by which the citation can be staged, validated, carried
forward, and later projected.

## Definitive Object Model

Avoid the overloaded phrase:

```text
OMI-native object
```

Use the definitive primitive:

```text
monotonic unary array compose operation
```

In the protocol core, an object is not:

```text
metadata
hash label
arbitrary carrier record
projection node
external storage handle
```

An object is:

```text
a composed unary relation over the addressed frame
```

This keeps object behavior inside the citation relation instead of adding an
extra object metadata channel beside it.

## CAR/CDR Composition Rule

Loading `CAR` means loading one full addressed envelope:

```text
CAR = |OMI---IMO>
      + F* 00 1C 1D 1E 1F 20 F*
      + o---o/---/?---?@---@ / S0..S7?PAYLOAD?MASK@CAR@CDR
```

Attaching `CDR` means attaching continuation over two full addressed
envelopes:

```text
CDR = envelope_a . envelope_b
```

Neither `CAR` nor `CDR` adds external metadata to identity.

The pair is lawful only because both sides remain reducible to addressed
relations.

## Primitive Operation Doctrine

The definitive operation classification is:

```text
Primitive object behavior:
monotonic unary array compose operations over addressed frames.

Primary reversible operator:
XOR.

Valid orbit-preserving movement:
rotation.

Narrow staging-only movement:
shift.

Invalid:
using shift as general protocol identity, address authority, attestation authority,
or object behavior.
```

XOR witnesses difference.

Rotation preserves orbit.

Unary compose builds object behavior.

Shift only stages the next frame.

Validation determines.

Omi-Attestation witnesses.

Accepted Omi-State may be recorded.

Shift is not a protocol primitive.

Shift may appear only as:

```text
1. implementation support for rotation
2. explicit mask/register layout
3. 64-bit unary register prefill
4. tap-code or Morse-code in-stream staging
5. Polybius coordinate preparation
6. Tetragrammatron address/gate observation
7. Metatron rule-set/projection framing
```

Any other use of shift is suspect until proven to be staging-only.

If a shift would create identity, authority, address creation, attestation creation,
or object behavior, it is invalid in the protocol core.

## 64-Bit Register Prefill Rule

Before entraining the next frame, OMI may pre-fill a 64-bit register with an
active unary stream bit configuration.

The prefill is used for narrow stream staging:

```text
tap-code
Morse-code
Polybius coordinate preparation
Tetragrammatron address/gate observation
Metatron rule-set / attestation framing
```

The prefill entrains the next frame through:

```text
F* 00 1C 1D 1E 1F 20 F*
```

The 64-bit register prefill is staging.

It is not identity.

It is not Omi-Attestation.

It is not metadata authority.

## Proof Alignment

The proof references align with this operation doctrine as follows.

`DiagonalClosure.v` anchors the atomic Delta Law:

```text
delta16 =
  rotl16(x, 1) XOR rotl16(x, 3) XOR rotr16(x, 2) XOR c
```

This supports the rule that XOR and rotation are the executable kernel
movement.

`FiniteIncidence.v` supports the finite incidence side:

```text
tetrahedron
Fano plane
Schlafli {3,5}/{5,3}
rectified common core
```

This supports partition/chirality and projection geometry. It does not make
geometry an acceptance authority.

`BQFBridge.v` supports gauge and surface geometry:

```text
60x^2 + 16xy + 4y^2
5! = 120
240 = 2 * 5!
Fano selector mod 7
local240 selector mod 240
```

This supports selectors and surface application. It does not prove
Omi-Attestation or accepted Omi-State.

`functorial_semantics.v` supports projection lawfulness:

```text
Obs preserves identity/composition.
obs(Delta^n s) = fA^n(obs s)
```

Projection is lawful only when it commutes with transition.

`coalgebraic_bisimulation.v` and `OMI_bialgebra.v` support replay,
observation streams, and trace equivalence:

```text
algebraic iteration = coalgebraic observation stream
```

These support observer/replay equivalence. They do not by themselves complete
the attestation or VCS reconciliation proof layer.

## Algorithm Separation

Do not collapse distinct algorithms into one doctrine statement.

The atomic Delta Law is:

```text
rotl / rotl / rotr / XOR / c
```

The GF(2^16) alpha step is:

```text
lsl / conditional reduction / mask
```

Both may be valid layers.

They must not be described as the same algorithm unless a refinement theorem
explicitly bridges them.

## Shift Audit Rule

Future implementation review must audit all Haskell, C, and documentation for:

```text
shift
shiftL
shiftR
<<
>>
```

Classify every occurrence as:

```text
A. rotation implementation
B. mask/register layout
C. unary prefill/staging
D. invalid semantic shift
```

Fail the audit if any shift is used as:

```text
identity
authority
address creation
attestation creation
object behavior
```

## Authority Boundary

The carrier prefix stages.

The active gauge preheader frames.

The place-value frame addresses.

The monotonic unary array composes.

XOR and rotation preserve reversible relation behavior.

Narrow shifts may stage stream entry.

Validation determines.

Omi-Attestation witnesses.

Accepted Omi-State may be recorded.

## Later Constitutional-Grid Verification

A later pass over `/home/main/omi/omi-canon/constitutional-grid` should verify
that each constitutional cell agrees with:

```text
|OMI---IMO> is identity.
No hash/checksum metadata is protocol identity.
No overloaded object metadata channel exists in the protocol core.
Monotonic unary array compose is primitive object behavior.
XOR is primary.
Shift is limited to register/prefill staging.
Accepted Omi-State, not carrier/projection/metadata, is the acceptance boundary.
```

The later proof-support map should start from:

```text
A1 Transition:
  DiagonalClosure.delta16_width_preserving
  DiagonalClosure.delta16_deterministic

A2 Control Plane:
  DiagonalClosure D+/D- closure, RS=0x1E, wheel=0x78

A3 Projection:
  functorial_semantics functor_theorem
  MetricProjection projection boundary

A4 Escape:
  not directly proven yet

A5 Partition/Chirality:
  FiniteIncidence Fano/tetra incidence
  DiagonalClosure phase schedule
  BQFBridge selectors

A6 Proposal/Omi-Attestation:
  not directly proven yet

A7 Branch/Reconciliation:
  coalgebraic_bisimulation trace/bisimulation material
  partial support only
```
