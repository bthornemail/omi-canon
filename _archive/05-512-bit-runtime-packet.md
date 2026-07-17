<!-- Extracted from dev-docs/chat about model.md -- conversation turn 2026-07-09 18:20 -->

# 512-Bit OMI Runtime Initialization Packet

The OMI runtime begins from a 512-bit initialization packet.

This packet is a 64-byte platform-agnostic bootstrap carrier for constructing an Omi Object Model environmental runtime.

It does not define an application. It defines the bounded runtime frame in which OMI declarations, definitions, compiled bytecode witnesses, and projection diagrams may be interpreted.

## Layer Stack

```text
-1 Algorithmic substrate
 compiled `.o` bytecode

 0 Omicron Null Byte Ring
 OMI-Lisp runtime operator

 1 Declaration
 `.omi` OMI-Lisp expressions

 2 Definition
 `.imo` inverse / attribution OMI-Lisp expressions

 3 Discovery / Projection
 Projection Diagrams over Omicron Null Byte OMI-Rings
```

Application remains outside this stack.

## 512-Bit Packet Shape

```text
512 bits = 64 bytes

gauge[8]
orientation[8]
recovery[8]
target[8]
relation[32]
```

This gives:

```text
8 + 8 + 8 + 8 + 32 = 64 bytes
64 bytes × 8 = 512 bits
```

The packet is large enough to carry the runtime gauge, orientation, recovery field, target field, and relation field, while still remaining fixed-width and platform agnostic.

## Polyharmonic Dotfile Embeddings

The dotfile convention becomes a polyharmonic embedding system:

```text
.omi
 human-readable declaration expressions

.imo
 inverse / attribution / definition expressions

.o
 compiled bytecode substrate
```

These are not merely filenames. They are embedding roles.

```text
.omi declares.
.imo defines.
.o executes as bounded substrate.
```

Together they form Polyharmonic Dotfile Embeddings.

## Polyharmonic Tetragrammatron

The Polyharmonic Tetragrammatron acts as both DSL and ABI boundary.

As DSL:

```text
it defines the declaration grammar:
 notation
 rules
 facts
 closures
 combinators
 cons-like forms
 projection diagrams
```

As ABI:

```text
it defines the binary interface:
 fixed-width fields
 gauges
 witnesses
 bytecode prefixing
 bitboard attachments
 runtime initialization packet layout
```

So the Polyharmonic Tetragrammatron is not only syntax and not only binary calling convention.

It is the bridge:

```text
DSL-facing declaration
↔
ABI-facing runtime frame
```

## Polyharmonic Tetragrammatron Governor

The Governor is the runtime resolver.

It adjudicates whether a Polyharmonic Dotfile Embedding fits the current Omicron frame.

It checks:

```text
envelope framing
gauge readiness
Polybius diagonal closure
Null Ring closure
witness reduction
projection-diagram compatibility
```

It does not decide application behavior.

It decides whether the declared/defined/compiled embedding can be resolved inside the bounded OMI runtime frame.

## Canon Statement

The 512-bit OMI runtime initialization packet is a 64-byte platform-agnostic bootstrap frame for an Omi Object Model environmental runtime.

Polyharmonic Dotfile Embeddings organize `.omi`, `.imo`, and `.o` into declaration, definition, and compiled substrate roles.

The Polyharmonic Tetragrammatron supplies the DSL/ABI boundary.

The Polyharmonic Tetragrammatron Governor adjudicates those embeddings as a runtime resolver.

OMI stops at governed runtime resolution and Projection Diagrams. Application remains downstream.