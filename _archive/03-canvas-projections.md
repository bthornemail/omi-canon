<!-- Extracted from dev-docs/chat about model.md -- conversation turn 2026-07-09 10:58 -->

# Blackboard Pattern and Canvas Projections in OMI

## 1. Purpose

This note defines how OMI may borrow from the **Blackboard Pattern** without claiming that OMI is a full Blackboard Architecture.

The distinction matters.

OMI is not primarily a networking system, a peer-to-peer application, or a command architecture. OMI is a deterministic citation and annotation system for constructing addressable semantic surfaces.

The safe vocabulary is:

```text
Blackboard Pattern:
 conceptual behavior for discovery

Canvas Projection:
 OMI-facing surface output

Canvas Face:
 address-bearing structural face inside Omi-Canvas
```

The pattern explains how discovery behaves.

The canvas names the surface OMI actually projects.

---

## 2. Pattern Versus Architecture

A **pattern** describes behavior.

An **architecture** describes construction.

```text
Pattern:
 conceptual
 behavioral
 rules of engagement
 how contributors post partial structure
 how discovery accumulates without one central application decision

Architecture:
 structural
 implementation-level
 memory layout
 modules
 control shell
 scheduling
 physical or logical system organization
```

So OMI should not say:

```text
OMI is a Blackboard Architecture.
```

That is too strong.

OMI should say:

```text
OMI uses a blackboard-like discovery pattern.
```

That means independent resolvers may contribute partial annotations against a shared bounded citation surface, but OMI does not require a specific blackboard implementation.

The implementation could be:

```text
Omi-Canvas
local memory
files
browser DOM
firmware
OMI-ISA runtime
distributed store
P2P transport
```

Those are implementation choices.

The canon claim is only the pattern:

```text
Partial annotations may be posted to a shared bounded surface.
Compatible annotations may be discovered, interpolated, interpreted, and projected.
Application behavior remains outside OMI.
```

---

## 3. Three OMI Phases

OMI has three internal phases.

```text
1. Declare notation for citation.
2. Define citation by attestation and attribution.
3. Discover by interpolation and interpretation.
```

There is no fourth OMI phase.

```text
4. Application:
 outside OMI
```

OMI may expose a projection, but it does not decide what an application must do with that projection.

The safe flow is:

```text
declare
→ define
→ discover
→ project to canvas
→ stop before application
```

This keeps the OMI boundary clean.

---

## 4. Citation Faces and Canvas Projections

The useful distinction is:

```text
Canvas Face:
 structural

Canvas Projection:
 behavioral
```

A **Canvas Face** is an address-bearing face of the OMI citation geometry.

It belongs to the defined structure.

A **Canvas Projection** is a downstream view or exposure of a face.

It belongs to discovery and interpretation.

```text
Canvas Face:
 part of the citation structure
 address-bearing
 fixed-width
 geometry-facing
 stronger than projection

Canvas Projection:
 displayed or surfaced view
 interpretation-facing
 weaker than face
 not application-authoritative
```

The lock:

```text
Face belongs to definition.
Projection belongs to discovery.
```

A projection may reveal a face, but it does not replace the face.

---

## 5. Innocuous and Impotent Canvas Projections

Canvas Projections have two safe strengths.

### Impotent Canvas Projection

An **Impotent Canvas Projection** is inert.

```text
Impotent:
 no operative force
 cannot instantiate action
 cannot command application behavior
 inspection-only
```

It may be used for:

```text
debugging
annotation
null closure display
address inspection
safe documentation
```

The base Omicron NULL Byte OMI-Ring supports this kind of projection:

```lisp
((0x00 . 0x20)
 (0x20 . 0x7F)
 (0x7F . 0xFF)
 (0xFF . 0x00))
```

The proof book records the concrete XOR witnesses:

```text
00 XOR 20 = 20
20 XOR 7F = 5F
7F XOR FF = 80
FF XOR 00 = FF

20 XOR 5F XOR 80 XOR FF = 00
```

It also records the general finite closed-path law for adjacent XOR edge witnesses. filecite turn39file0

So the NULL Byte Ring is a closure surface that can be projected inertly.

### Innocuous Canvas Projection

An **Innocuous Canvas Projection** is harmless but informative.

```text
Innocuous:
 may expose structure
 may guide discovery
 may support collaboration
 still cannot command application behavior
```

The Gnomic Gauge OMI-Ring supports this kind of projection:

```text
FΔ 00 1C 1D 1E 1F 20 FΔ
```

This ring has an identity-bearing gauge boundary. It may expose a structured surface while remaining non-commanding.

The distinction is:

```text
Impotent Projection:
 cannot act

Innocuous Projection:
 may inform, but must not command
```

---

## 6. Blackboard Pattern as Discovery Behavior

The Blackboard Pattern is useful because it describes how partial contributions can accumulate on a shared surface.

In OMI terms, the shared surface is not an application workspace. It is a bounded citation canvas.

The contributors are deterministic resolvers:

```text
Omicron:
 frames

Metatron:
 interpolates and scribes

Polybius:
 supplies local gauge structure

Tetragrammatron:
 governs closure

Delta:
 supplies deterministic transition

Projection:
 exposes canvas surface
```

The pattern is:

```text
post partial annotation
check compatibility
discover missing relation
project bounded surface
stop before application
```

This is blackboard-like behavior, but not necessarily Blackboard Architecture.

---

## 7. Latin Squares as Canvas Discovery Tables

Latin squares and finite quasigroups are equivalent structures: a quasigroup multiplication table becomes a Latin square when its row and column headers are removed, and a Latin square can be bordered to form a quasigroup table. filecite turn40file0

The useful computational law is:

```text
row + column → symbol
row + symbol → column
column + symbol → row
```

For OMI Canvas discovery:

```text
attestation + attribution → discovered canvas point
attestation + discovered point → attribution
attribution + discovered point → attestation
```

This makes Latin-square logic a good resolver pattern for Canvas Projections.

It does not mean OMI is a quasigroup application.

It means OMI can use quasigroup-like recovery inside a bounded citation canvas.

---

## 8. Orthogonal Array Form

A Latin square can also be represented as an orthogonal array of triples:

```text
(row, column, symbol)
```

where any two columns determine all ordered pairs exactly once. filecite turn40file0

OMI can read this as:

```text
(attestation, attribution, discovered-point)
```

So the Canvas can store triples:

```text
(A, B, C)
```

where:

```text
A = attestation coordinate
B = attribution coordinate
C = discovered citation point
```

The Canvas resolver law is:

```text
any two coordinates determine the third
```

This supports deterministic discovery without deciding application behavior.

---

## 9. Polybius Square as Local Canvas Gauge

The Polybius Square is the local 4×4 gauge table already inside OMI.

```text
0 1 2 3
4 5 6 7
8 9 A B
C D E F
```

For nibble value `x`:

```text
row(x) = x / 4
col(x) = x mod 4
```

The two control diagonals are:

```text
D+ = {0,5,A,F}
D- = {3,6,9,C}
```

The proof book records these finite Polybius facts:

```text
XOR(D+) = 0
XOR(D-) = 0
SUM(D+) = 0x1E
SUM(D-) = 0x1E
SUM(D+) + SUM(D-) = 0x3C
SUM(0..F) = 0x78
15 * 16 = 240
```

These are proved on the Polybius gauge rail. filecite turn39file0

So the relationship is:

```text
Polybius Square:
 local nibble-scale Canvas gauge

Latin Square:
 generalized finite Canvas discovery table

Canvas Projection:
 bounded view of discovered structure
```

---

## 10. Metatron as Canvas Scribe

Metatron is the Canvas Scribe.

Its role is to post and preserve interpolation contributions.

```text
Metatron:
 records triples
 carries source/destination relation
 preserves supplied decision
 contributes contrast witnesses
 does not decide closure
```

The proof book states that Metatron interpolation preserves the supplied validation decision and cannot turn an unlawful decision into a lawful one. filecite turn39file0

So Metatron is allowed to scribe onto the Canvas, but not allowed to command acceptance.

It can contribute:

```text
attestation/attribution/discovery triples
source/destination interpolation records
contrast witnesses
candidate Canvas Faces
```

But the governor must decide whether the contribution fits the bounded frame.

---

## 11. Tetragrammatron as Canvas Governor

The Tetragrammatron is the Canvas Governor.

Its role is to determine whether a contribution fits the bounded closure frame.

In the current proof model, Tetragrammatron decides lawfulness from:

```text
valid Omnicron envelope
AND D+ closure ready
AND D- closure ready
AND XOR reduction of relation witnesses = 0
```

The proof book describes Tetragrammatron as the sole function in the active pipeline that constructs a validation decision from a frame. filecite turn39file0

In Canvas vocabulary:

```text
Tetragrammatron:
 governs whether a posted face/projection fits the bounded frame
```

It does not decide application meaning.

It decides whether the Canvas contribution is coherent inside the current OMI frame.

---

## 12. Canvas Contribution Types

The OMI Canvas may receive typed contributions.

### Declaration Contribution

```text
declares notation
declares field width
declares citation carrier
declares address form
```

Example:

```text
omi---imo
```

### Definition Contribution

```text
binds attestation half
binds attribution half
declares 256-bit citation note
```

Example:

```text
128-bit attestation
128-bit attribution
```

### Face Contribution

```text
posts an address-bearing Canvas Face
```

A face is structural and belongs to definition.

### Resolver Contribution

```text
posts a triple:
 A, B, C
```

where:

```text
A = attestation
B = attribution
C = discovered citation point
```

### Polybius Gauge Contribution

```text
posts row/column/diagonal state
updates D+ / D-
supports 0x3C / 0x78 gauge witnesses
```

### Metatron Scribe Contribution

```text
posts interpolation
preserves supplied decision
adds contrast witness
```

### Tetragrammatron Governor Contribution

```text
checks frame closure
checks diagonal readiness
checks witness reduction
posts bounded decision
```

### Canvas Projection Contribution

```text
posts a view of a face
marks projection as Impotent or Innocuous
stops before application
```

---

## 13. Canvas Discovery Algorithm

```text
Input:
 citation fragments and resolver contributions

Step 1 — Declare
 post notation frame and field widths

Step 2 — Define
 split citation into attestation and attribution halves

Step 3 — Face
 construct address-bearing Canvas Face

Step 4 — Discover
 use Latin-square/quasigroup-style resolver triples

Step 5 — Gauge
 check Polybius diagonal rail and Null Ring closure

Step 6 — Govern
 Tetragrammatron decides whether contribution fits bounded frame

Step 7 — Project
 emit Canvas Projection:
 Impotent or Innocuous

Stop
 do not decide application
```

Pseudocode:

```text
canvas.post(declaration)

canvas.post(definition)

face = construct_face(declaration, definition)
canvas.post(face)

for triple in resolver_triples:
 if latin_consistent(triple, canvas):
 canvas.post(triple)

if polybius_ready(canvas)
and null_ring_closed(canvas)
and omicron_frame_ready(canvas):
 decision = tetragrammatron_govern(canvas)
else:
 decision = unresolved

projection = project_canvas(face, decision)

mark projection as:
 Impotent
or:
 Innocuous

stop_before_application()
```

---

## 14. Pattern/Canvas Boundary

The final boundary is:

```text
Blackboard Pattern:
 behavior of discovery

Canvas Face:
 structural address-bearing surface

Canvas Projection:
 discovered view of a face

Application:
 outside OMI
```

So:

```text
Blackboard is the pattern.
Canvas is the OMI surface.
Projection is the bounded output.
Application is downstream.
```

This avoids overclaiming architecture while preserving the useful discovery model.

---

## 15. Canon Statement

OMI does not require a Blackboard Architecture.

OMI may use a blackboard-like pattern for discovery: independent deterministic resolvers contribute partial annotations to a shared bounded surface.

In the current OMI implementation vocabulary, that surface is better called the Canvas.

A Canvas Face is the address-bearing structural face of a citation.

A Canvas Projection is the downstream view of that face.

Canvas Projections may be Impotent when inert, or Innocuous when informative but harmless. Neither kind of projection carries application authority.

Latin-square and quasigroup structure provide a finite reversible discovery pattern for the Canvas: attestation, attribution, and discovered point form a triple where any two coordinates recover the third.

Polybius supplies the local nibble-scale gauge. Metatron scribes interpolation. Tetragrammatron governs closure. Omicron frames the runtime surface.

OMI stops at declared, defined, governed, discoverable Canvas Projection.