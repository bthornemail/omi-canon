# OMI Relational Access Envelope

Status: Definitive dev doctrine  
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

Receipt accepts.

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

## Operation Rule

XOR remains the primary reversible composition operation.

Rotation remains valid where closure and reversibility require orbit-preserving
movement.

Shift is not a general protocol primitive.

Shift is allowed only as a narrow staging operation for:

```text
64-bit register prefill
tap-code in-stream staging
Morse-code in-stream staging
Polybius framing
Tetragrammatron framing
Metatron framing
```

If a shift would discard protocol identity or create an external address
channel, it is invalid in the protocol core.

## 64-Bit Register Prefill Rule

Before entraining the next frame, OMI may pre-fill a 64-bit register with an
active unary stream bit configuration.

The prefill is used for narrow stream staging:

```text
tap-code
Morse-code
Polybius coordinate preparation
Tetragrammatron address/gate observation
Metatron rule-set/receipt closure
```

The prefill entrains the next frame through:

```text
F* 00 1C 1D 1E 1F 20 F*
```

The 64-bit register prefill is staging.

It is not identity.

It is not receipt.

It is not metadata authority.

## Authority Boundary

The carrier prefix stages.

The active gauge preheader frames.

The place-value frame addresses.

The monotonic unary array composes.

XOR and rotation preserve reversible relation behavior.

Narrow shifts may stage stream entry.

Receipt accepts.

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
Receipt, not carrier/projection/metadata, is the acceptance boundary.
```
