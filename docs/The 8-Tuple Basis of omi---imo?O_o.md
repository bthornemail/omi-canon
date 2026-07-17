# Unary Sign Relations in `omi---imo?O_o`

## Status

Canonical working doctrine.

This document explains the sign-first reading of the OMI 8-tuple. It replaces
the earlier interpretation of the tuple as eight numerical coordinates or as
an `8 × 16-bit` quantity.

The tuple begins as a unary relation of compatible signs. Place value, nibble
encoding, machine width, and local behavior are later bindings.

---

## 1. Core Claim

OMI reads signs before quantities.

The relation:

```text
omi---imo?O_o
```

has two compatible presentations:

```text
omi---imo  folded relation sign
?O_o       readable relation sign
```

They may be composed because they share an OMI relation type. Their shared
type does not mean they have the same spelling or local interpretation.

The underlying sign tuple is:

```text
Q  Σ  L  R  δ  s  t  r
```

Before any number is assigned, its cardinality is shown as a unary tally:

```text
|  |  |  |  |  |  |  |
```

This tally means eight positions of one compatible tuple type. It does not
mean eight spatial dimensions, eight independent real coordinates, or eight
machine words.

Canonical law:

```text
Sign establishes role.
Tuple establishes compatibility.
Nesting establishes place.
Address binds place value.
Lowering supplies bits.
XOR computes the relation witness.
```

---

## 2. Unary Does Not Mean Unstructured

A unary reading does not erase the signs. It says every position is first read
as one unit of the same relation carrier:

```text
Q  = |
Σ  = |
L  = |
R  = |
δ  = |
s  = |
t  = |
r  = |
```

The signs remain distinguishable by role:

```text
Q   state or identity context
Σ   admitted sign alphabet or dialect
L   left or source relation
R   right or destination relation
δ   difference or transition relation
s   start relation
t   terminal or successful relation
r   rejected or alternative relation
```

These names do not assign numerical magnitude. They declare how one unary
position may participate in a relation.

The tuple is therefore:

```text
one carrier type
eight role signs
one ordered relation
```

---

## 3. Type-Parallel Positions

OMI may call the tuple positions **type-parallel**.

Type-parallel means:

```text
each position belongs to the same relation carrier;
each position may be compared, paired, nested, or lowered by the same family
of operations.
```

It does not automatically mean that the positions are parallel Euclidean
lines. A geometric projection may draw them as parallel lanes, but that is a
canonical visualization rather than the computational definition.

Unary array:

```text
[Q] [Σ] [L] [R] [δ] [s] [t] [r]
 |   |   |   |   |   |   |   |
```

All eight slots share a type. Their labels provide roles. Their order provides
place. A local dialect may attach additional meaning without changing the
shared carrier type.

---

## 4. Pairing Is Relation, Not Compression

The eight signs may be folded into four dotted relations:

```lisp
((Q . Σ)
 (L . R)
 (δ . s)
 (t . r))
```

Unary tally:

```text
(||) (||) (||) (||)
```

This operation does not compress eight quantities into four quantities. It
organizes eight signs as four relations.

The role aliases are:

```text
(Q . Σ)  CAR relation
(L . R)  CDR relation
(δ . s)  PAYLOAD relation
(t . r)  MASK relation
```

`CAR`, `CDR`, `PAYLOAD`, and `MASK` are relation roles. They are not required
to be 32-bit integers. A runtime may choose a bounded representation, but that
representation is downstream of the sign relation.

Correct reading:

```text
eight signs
-> four dotted relations
-> one recursively nestable Omi-Ring
```

Rejected reading:

```text
8 × 16-bit coordinates
-> 4 × 32-bit numerical compression
-> geometric dimension count
```

---

## 5. Why Lisp and Dot Notation Fit

The Lisp pair:

```lisp
(CAR . CDR)
```

is the minimal readable form of a current relation and its continuation:

```text
CAR  current sign or addressed place
CDR  remaining relation
dot  witnessed difference between them
```

The CDR may contain another pair:

```lisp
(A . (B . (C . D)))
```

The same rule therefore survives at every finite depth:

```text
A is related to the tail beginning at B.
B is related to the tail beginning at C.
C is related to D.
```

No new operation is required when the tail grows. The relation remains unary
and recursive.

Canonical sentence:

```text
CONS does not add another kind of object.
CONS adds another place at which the same relation type may be read.
```

---

## 6. XOR-Balanced Pairs

After compatible signs are lowered to equal-width bit representations, the dot
relation is computed by bitwise XOR:

```text
witness(A . B) = encode(A) XOR encode(B)
```

An arbitrary pair does not have to produce zero. It produces a reversible
difference:

```text
W = A XOR B

A XOR W = B
B XOR W = A
```

The complete relation balances when its path closes:

```text
(A XOR B)
XOR (B XOR C)
XOR (C XOR D)
XOR (D XOR A)
= 0
```

Every shared boundary occurs twice and cancels. The number of intermediate
tail positions does not change the law:

```text
(x0 XOR x1)
XOR (x1 XOR x2)
XOR ...
XOR (xn XOR x0)
= 0
```

This is the computational reason dotted lists fit the Null Ring.

```text
pair             local reversible difference
tail             recursive continuation
closed tail      global XOR balance
NULL             folded zero closure
```

---

## 7. The Null Ring

The folded form is:

```lisp
(NULL . NULL)
```

The unfolded byte ring is:

```lisp
((0x00 . 0x20)
 (0x20 . 0x7F)
 (0x7F . 0xFF)
 (0xFF . 0x00))
```

Its local witnesses are:

```text
0x00 XOR 0x20 = 0x20
0x20 XOR 0x7F = 0x5F
0x7F XOR 0xFF = 0x80
0xFF XOR 0x00 = 0xFF
```

Its complete closure is:

```text
0x20 XOR 0x5F XOR 0x80 XOR 0xFF = 0x00
```

The byte values are one canonical lowering of the relation. The deeper law is
the cancellation of repeated boundaries in a closed XOR path.

---

## 8. Sign Value and Place Value

OMI distinguishes two readings.

### Sign value

Sign value answers:

```text
what role may this mark play?
what relation type does it share?
which dialect may read it?
```

Examples:

```text
Q Σ L R δ s t r
omi---imo
?O_o
FS GS RS US
o / ? @
```

### Place value

Place value answers:

```text
where is this sign nested?
which address position binds it?
which gauge lane lowers it?
which local attestation applies?
```

Place value is not intrinsic to the glyph. It is assigned by:

```text
order
nesting
address
gauge
nearest attestation
local binding
```

Therefore:

```text
same sign type + different place = different addressed interpretation
different visible dialect + compatible type = composable relation
```

---

## 9. Nibble-Based Lowering

OMI uses hexadecimal notation because each hexadecimal sign has an exact
four-bit lowering:

```text
one nibble sign
-> one value in 0x0..0xF
-> one four-bit pattern
```

The nibble is the local computational alphabet. Larger addresses are nested or
concatenated nibble places.

The visible sign language may have multiple dialects:

```text
folded notation
readable notation
workbook annotation
canvas projection
local runtime alias
```

Every OMI dialect form is computationally compatible because it lowers through
the same hexadecimal nibble carrier:

```text
visible form A
  -> canonical nibble stream A'

visible form B
  -> canonical nibble stream B'

canonical place normalization
  -> equal-width A'' and B''

A'' XOR B''
  -> bitwise relation witness
```

Different lengths or visible shapes do not create different computational
types. Canonical place-value normalization supplies the shared width and
alignment. Every position remains a nibble position, and every nibble has the
same exact four-bit carrier.

Conventional computers execute binary operations rather than hexadecimal
glyphs internally. Hexadecimal is the exact portable notation used by OMI:
each hex sign names one four-bit value without approximation. This is the sense
in which OMI relations are compatible across computers.

---

## 10. `omi---imo` and `?O_o`

The two forms:

```text
omi---imo
?O_o
```

may share an OMI relation type while presenting different dialects:

```text
omi---imo  folded root dialect
?O_o       readable F-column dialect
```

Their composition is not textual XOR. It is:

```text
1. recognize both signs;
2. resolve the applicable dialect and nearest attestation;
3. lower both to the universal nibble carrier;
4. normalize both by canonical place and width;
5. compute pointwise bitwise XOR;
6. preserve the witness or reduce a closed path to zero.
```

Only step 5 is the primitive relation computation. The preceding steps
determine where each universally compatible nibble belongs.

Canonical form:

```text
encode(omi---imo) XOR encode(?O_o) = relation witness
```

Canonical normalization guarantees the shared computational shape.

---

## 11. Computational and Canonical Approaches

OMI separates the computational protocol from its canonical interpretation.

### Computational approach

The computational protocol is restricted to deterministic bitwise laws over
bounded compatible encodings:

```text
mask
shift
compare
bitwise XOR
XOR reduction
fixed nibble lookup
exact boundary test
```

The central relation operation is XOR.

```text
No floating interpretation decides the relation.
No projection changes the relation.
No local meaning changes the bitwise witness.
```

### Canonical approach

The canonical approach may:

```text
name a sign
explain a role
draw a geometry
associate a Hopf projection
bind an address to a local function
render a Canvas
annotate a workbook
connect a proof or historical source
```

These interpretations may explain, organize, or project a relation. They are
not primitive protocol computation.

Canonical sentence:

```text
XOR computes.
Canon interprets.
```

---

## 12. Tetragrammatron, Omnicron, and Metatron

The role boundary remains:

```text
Omnicron
  frames universally compatible signs and their gauge context

Tetragrammatron
  validates the exact nibble and XOR closure conditions

Metatron
  interpolates and scribes the visible difference

Receipt
  records the accepted decision
```

Neither sign compatibility nor a visible pairing independently validates a
relation.

---

## 13. Workbook and Canvas Consequence

OMI Canvas and OMI Workbook do not need to transport functions.

They carry:

```text
sign
relation type
nesting
place-value address
gauge
nearest attestation
optional local binding
```

A local environment may bind one compatible address to:

```text
a note
a proof
a page
a function
a command
an entity
a projection
```

The portable object is the addressed relation, not the bound behavior.

Canvas may draw type-parallel signs as lanes, points, or nested regions. That
geometry is a projection of the relation structure. The computational
authority remains the canonical nibble lowering and deterministic XOR law.

---

## 14. Hopf Language Boundary

Hopf language may describe the intuition that one relation presentation
projects into another while preserving a witness.

It is not derived from:

```text
eight tuple signs
four dotted pairs
16-bit or 32-bit storage widths
```

Those are not dimensional proofs.

The current exact foundation is:

```text
unary signs in one universal nibble carrier
recursive dotted pairing
canonical nibble lowering
bitwise XOR witness
closed-path XOR cancellation
```

A literal Hopf-fibration claim would require a separately defined topological
space, normalization, projection map, fibers, and proof.

---

## 15. Final Canon

```text
OMI reads sign before magnitude.

Every tuple position is one unary unit of a shared relation type.

The signs remain distinct by role.

Dot notation pairs a current sign with its continuation.

CONS repeats the same relation through any finite tail.

Nesting and address assign place value.

Gauge and dialect lower compatible signs to equal nibble shapes.

Bitwise XOR computes the relation witness.

A closed XOR path reduces to NULL because every shared boundary occurs twice.

Tetragrammatron validates exact closure.

Omnicron frames.

Metatron scribes.

Canvas and workbook notation project and annotate.

Anything beyond the deterministic bitwise law belongs to canonical
interpretation until separately implemented or proved.
```

Shortest form:

```text
Signs share type.
Pairs witness difference.
Tails preserve relation.
Addresses assign place.
Nibbles lower signs.
XOR computes.
Closure returns NULL.
Canon explains the rest.
```
