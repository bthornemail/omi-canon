# Tangential Block Geometry

## A First-Principles Foundation for OMI, OMINO, and Circular Projective Computation

**Status:** Foundational Whitepaper Draft
**Scope:** Geometry, incidence, projection, encoding, and deterministic execution
**Primary principle:** Geometry defines the system; encodings and implementations realize it
**Implementation relationship:** The existing OMI/OMINO architecture is treated as a concrete bounded realization, not as the definition of the geometry

---

## Abstract

This paper proposes **Tangential Block Geometry**, a finite projective framework for representing expressions, observations, computations, and conceptual relations.

The central claim is not that every concept is reducible to an ordinary geometric shape. The claim is that every concept that can be finitely expressed may be represented through:

1. a set of distinguishable points;
2. a family of blocks describing admissible relations among those points;
3. a tangent operation selecting how two relational structures meet;
4. a projection determining the point of view from which the structure is read;
5. a residual witness recording the difference between an intended projection and a realized projection.

The resulting object may be rendered as a graph, expression, byte sequence, block design, tensor, circular slide ruler, polytope register, or executable coordinate transformation.

This establishes the general form:

[
\boxed{
\text{Expression}
=================

\text{Block Design}
+
\text{Tangent Operation}
+
\text{Projection}
+
\text{Residual Witness}
}
]

The earlier OMI, OMINO, and Omnicron systems discovered much of this geometry through implementation. They introduced a fixed centroid, circular slide rulers, low and high character planes, Hamming and Fano incidence, `.omi` and `.imo` surfaces, and branchless coordinate transformations.

The present work reverses that direction.

Rather than deriving geometry from code, it derives code from geometry.

---

# Part I — Foundational Position

## 1. The problem

Software systems usually begin with one of the following:

* values;
* objects;
* functions;
* instructions;
* syntax trees;
* records;
* memory;
* files;
* messages.

Each beginning assumes that the structure of the world has already been divided into computational objects.

Tangential Block Geometry begins earlier.

It asks:

> What structure must exist before something can be interpreted as an object, operation, observer, message, or expression?

The proposed answer is:

* distinction;
* relation;
* incidence;
* orientation;
* projection;
* closure.

A thing cannot be represented until it is distinguishable.

A relation cannot be represented until at least two distinctions can be compared.

A structure cannot be interpreted until a point of view selects how its distinctions and relations are read.

A result cannot be trusted until the difference between input intention and output realization can be witnessed.

These requirements are more primitive than a programming language.

---

## 2. Foundational thesis

A finitely conceptualizable object may be represented as a projected incidence structure.

Let:

[
\mathfrak T=(P,\mathcal B,\tau,\Lambda,\Pi,\mathcal R)
]

where:

* (P) is a finite or bounded set of points;
* (\mathcal B) is a family of blocks over (P);
* (\tau) is a tangency relation;
* (\Lambda) is a tangent-selection or tangent-composition operation;
* (\Pi) is a family of projections;
* (\mathcal R) is a residual or witness space.

An expression is then:

[
E=\Pi_\omega\left(\Lambda(B_i,B_j)\right)
]

where:

* (B_i,B_j\in\mathcal B);
* (\omega) is an orientation or observer position;
* (E) is the projected expression.

Its residual witness is:

[
R=
E_{\mathrm{realized}}
\ominus
E_{\mathrm{intended}}
]

The operator (\ominus) need not mean arithmetic subtraction. It denotes a declared comparison law appropriate to the representation, such as:

* XOR difference;
* parity mismatch;
* graph difference;
* block-incidence difference;
* projection difference;
* orientation mismatch.

---

## 3. Epistemic status discipline

This paper distinguishes four kinds of statements.

### 3.1 Standard mathematical fact

A statement already established in conventional mathematics.

Examples:

* the Fano plane is a (2\text{-}(7,3,1)) design;
* a tetrahedron has four vertices;
* the octonions form an eight-dimensional real algebra;
* the Cayley–Dickson process doubles algebra dimension;
* the Leech lattice is 24-dimensional.

### 3.2 OMI-defined construction

A new interpretation or operation introduced by this architecture.

Examples:

* Fano pinch point;
* tangent lambda block;
* OMINO centroid;
* circular character gauge;
* a tetrahedron whose vertices are registers for dual polytope families.

### 3.3 Encoding choice

A conventional symbol or numeric coordinate assigned to a geometric role.

Examples:

* assigning `0x00` to the centroid;
* assigning `0x20` to the projection hinge;
* assigning `0x80` to a remote-plane reflection boundary.

### 3.4 Implementation claim

A statement about how the geometry is executed.

Examples:

* using XOR to calculate a residual;
* using a rotate operation to advance a circular ruler;
* using Hamming encoding to protect four scope coordinates.

These levels must not be collapsed.

The fact that `0x00` encodes the centroid does not mean that ASCII defines the centroid.

The fact that a Fano plane can represent a seven-point controller does not mean that every seven-byte sequence is intrinsically a Fano plane.

The fact that a tetrahedron has four vertices does not make every four-register structure a literal Euclidean tetrahedron.

---

# Part II — Primitive Concepts

## 4. Distinction

A **distinction** is the minimal act by which one state can be told apart from another.

A distinction does not yet require an object.

It requires only:

[
a\neq b
]

A point is the geometric representation of one declared distinction.

Therefore:

[
\boxed{
\text{Point}
============

\text{addressable distinction}
}
]

In implementation, a point may be represented by:

* a bit position;
* an integer;
* a byte;
* a coordinate;
* a symbol;
* a node identifier.

The representation is secondary.

---

## 5. Relation

A relation exists when two or more distinctions participate in one declared structure.

For two points (p,q\in P), a relation may be written:

[
p\sim q
]

A line is the simplest geometric mnemonic for relational connection.

Therefore:

[
\boxed{
\text{Line}
===========

\text{addressable relation}
}
]

A relation does not necessarily imply direction.

Directed and undirected relations are different projections of the same underlying incidence possibility.

---

## 6. Incidence

Incidence records that a point participates in a relational structure.

If (p) belongs to block (B), write:

[
p,I,B
]

or:

[
p\in B
]

Incidence is more primitive than graph traversal.

It does not say that a computation moves from one point to another.

It says that the points and relation belong to one bounded structure.

This distinction is essential.

Tangential Block Geometry is primarily spatial and relational, not sequential.

---

## 7. Block

A **block** is a bounded collection of mutually interpreted points.

For:

[
B={p_1,p_2,\ldots,p_k}
]

the block means that these points participate in one declared relational context.

A block is not merely a list.

Order may be added by a projection, but membership exists before order.

Examples of possible blocks include:

* observer, observation, observer;
* operation, declaration, definition;
* CONS, CAR, CDR;
* input, residual, output;
* file, group, record, unit.

---

## 8. Block design

A block design is a system:

[
\mathcal D=(P,\mathcal B)
]

where:

* (P) is a point set;
* (\mathcal B) is a collection of blocks over (P).

A block design records which relations are permitted or meaningful.

In this architecture, a concept is not identified with one block alone.

It may include:

* an observation block design;
* an observer block design;
* an operation block design;
* a scope block design;
* an input/output block design.

Multiple block designs may share a tangent.

---

## 9. Tangency

Tangency is the declared condition under which two relational structures meet without becoming indistinguishable.

Geometrically, two shapes may share a point or boundary condition.

Architecturally, two expressions may share:

* a scope;
* a witness;
* a separator;
* a continuation;
* a centroid-relative orientation.

Tangency preserves both:

1. contact;
2. distinction.

This is why tangency is more appropriate than simple merging.

A merge can erase boundaries.

A tangent records that two things meet while remaining individually addressable.

---

## 10. Lambda

The symbol (\Lambda) denotes the selected tangent operation.

It may act as:

* a constructor;
* a mediator;
* a branch point;
* a scope selector;
* an observer-relative projection;
* a composition hinge.

The general form is:

[
\Lambda(L,M,R)
]

where:

* (L) is the incoming or left relational boundary;
* (M) is the tangent mediator;
* (R) is the outgoing or right relational boundary.

This should not be confused with ordinary untyped lambda calculus unless a specific projection establishes that interpretation.

The Tangential Lambda is more general.

It precedes any particular programming-language syntax.

---

## 11. Projection

A relational structure may admit multiple valid views.

Projection chooses one.

Let:

[
\Pi_\omega:\mathfrak T\rightarrow E_\omega
]

where (\omega) identifies the observer position, orientation, scope, or chart.

Projection does not create the entire underlying structure.

It selects the expression visible from one orientation.

Therefore:

[
\boxed{
\text{Expression}
=================

\text{projected relational structure}
}
]

Two observers may produce different expressions from one shared incidence structure without either expression being false.

The difference may be perspectival rather than contradictory.

---

## 12. Residual

Every projection suppresses information.

Every implementation may also differ from its intended result.

The residual records what is not conserved by the projection.

Let:

[
R_\omega =
\Pi_\omega(\mathfrak T)
\ominus
\widehat{\Pi}_\omega(\mathfrak T)
]

where:

* (\Pi_\omega) is the intended projection;
* (\widehat{\Pi}_\omega) is the realized projection.

The residual may encode:

* error;
* uncertainty;
* unresolved incidence;
* parity mismatch;
* incomplete closure;
* unconsumed input;
* projection loss.

Residuals are not merely failures.

They are witnesses.

---

# Part III — The Lambda Cube

## 13. Four corresponding relational triples

The architecture identifies four related triples.

### 13.1 Epistemic triple

[
\Lambda(
\text{Observer}*{in},
\text{Observation},
\text{Observer}*{out}
)
]

This represents the transformation of an observation from one observer-relative state to another.

### 13.2 Language triple

[
\Lambda(
\text{Declaration},
\text{Definition},
\text{Operation}
)
]

A declaration identifies a symbol or relation.

A definition constrains its meaning.

An operation realizes it in a projected context.

### 13.3 Lisp triple

[
\Lambda(
\operatorname{CAR},
\operatorname{CONS},
\operatorname{CDR}
)
]

Here CONS is the tangent mediator joining the left and right relational surfaces.

### 13.4 Process triple

[
\Lambda(
\operatorname{STDIN},
\operatorname{STDERR},
\operatorname{STDOUT}
)
]

STDIN supplies the incoming projection.

STDOUT carries the realized outgoing projection.

STDERR carries the residual witness.

---

## 14. Why STDERR belongs in the center

Ordinary process diagrams often place STDERR beside STDOUT as a second output channel.

Tangential Block Geometry gives it a deeper role.

STDERR is the mediating witness between intended input interpretation and realized output interpretation.

Therefore:

[
\boxed{
\operatorname{STDERR}
=====================

\operatorname{STDOUT}
\ominus
\Lambda(\operatorname{STDIN})
}
]

This does not require that every byte sent to STDERR be a mathematical error.

It means STDERR is the natural channel for:

* projection mismatch;
* incomplete interpretation;
* residual context;
* diagnostic witness;
* rejected incidence;
* unresolved expression.

---

## 15. Lambda Cube formulation

The four triples form four views of one relational cube:

[
\mathcal L=
\left[
\begin{array}{c}
\Lambda(O_{in},X,O_{out})\
\Lambda(D_{cl},D_{fn},Op)\
\Lambda(CAR,CONS,CDR)\
\Lambda(STDIN,STDERR,STDOUT)
\end{array}
\right]
]

The cube does not mean there are literally twelve unrelated coordinates.

It means one relational form can be interpreted in four domains:

* epistemic;
* linguistic;
* structural;
* operational.

A valid implementation should declare which mappings between these views are exact, partial, metaphorical, or representation-dependent.

---

# Part IV — Fano Incidence and the Seven-Point Controller

## 16. The Fano plane

The Fano plane is the finite projective plane of order two.

It contains:

* seven points;
* seven lines;
* three points on every line;
* three lines through every point;
* exactly one line through every pair of points.

It is the block design:

[
2\text{-}(7,3,1)
]

This makes it a natural carrier for a seven-coordinate controller.

---

## 17. The controller point set

Define:

[
C_7=
{
0x00,
0x1B,
0x1C,
0x1D,
0x1E,
0x1F,
0x20
}
]

with the encoding interpretation:

|  Point | ASCII name | Geometric role                         |
| -----: | ---------- | -------------------------------------- |
| `0x00` | NUL        | origin or null centroid                |
| `0x1B` | ESC        | escape from the current chart          |
| `0x1C` | FS         | enclosing file or field scope          |
| `0x1D` | GS         | group or lambda mediator               |
| `0x1E` | RS         | record or relation scope               |
| `0x1F` | US         | atomic unit tangent                    |
| `0x20` | SPACE      | visible separator and projective hinge |

This assignment is an encoding choice over a seven-point incidence carrier.

The mathematical Fano plane does not itself identify one point as NULL or GS.

---

## 18. Proposed lambda point

The most natural lambda encoding is:

[
\lambda=0x1D=\mathrm{GS}
]

because Group Separator lies conceptually between:

* the larger enclosing file scope;
* the smaller record and unit scopes.

This gives:

[
FS\leftarrow GS\rightarrow RS
]

with US providing atomic termination or tangency.

However, the geometry must permit other designated lambda points under other projections.

The Fano design is symmetric.

The designation of one point as lambda is observer- or chart-relative unless the encoding authority freezes it.

---

## 19. Fano pinch

A **Fano pinch** is an OMI-defined contraction:

[
\operatorname{pinch}*\lambda:
\mathcal D_7\rightarrow p*\lambda
]

It contracts the current seven-point incidence interpretation toward one selected projective point.

The pinch does not destroy the other points.

It changes the active view so the selected point becomes the branch or tangent reference.

This supports expressions such as:

* pinch at NULL;
* pinch at GS;
* pinch at SPACE;
* pinch at US.

---

## 20. Input and output Fano projections

Define two Fano projections:

[
\mathcal F_{in}
]

and:

[
\mathcal F_{out}
]

They may contain the same abstract incidence design under different point assignments or orientations.

The residual block design is:

[
\mathcal B_{err}
================

\mathcal F_{out}
\ominus
\Lambda(\mathcal F_{in})
]

This yields:

```text
Input plane      -> STDIN
Output plane     -> STDOUT
Residual design  -> STDERR
```

Two Fano planes do not automatically form a mathematical biplane.

The term **biplane** should be reserved for a design with the appropriate (\lambda=2) incidence property.

Until that is explicitly constructed, the safe term is:

> paired Fano projection

or:

> dual Fano input/output design.

---

# Part V — Centroid, Ball, Sphere, and Circumscription

## 21. Centroid

The centroid is the selected origin relative to which projection, orientation, and distance are interpreted.

In the existing OMINO realization:

[
\boxed{
\text{OMINO centroid}=0x00,\quad 0^\circ
}
]

The prior architecture explicitly defines local transitions relative to this fixed centroid and requires identical declared inputs and starting coordinates to produce identical outputs.

The centroid is not another moving agent.

It is a fixed object-relative reference.

---

## 22. One centroid, multiple orientations

There must be only one canonical centroid within one bounded object.

Antipodal orientation does not create a second centroid.

Instead:

[
\omega
\quad\text{and}\quad
-\omega
]

are opposing orientations relative to one centroid.

This distinction prevents a dual view from being mistaken for a second authority.

The former OMI architecture already states that the concentric slide ruler and the 3D knowledge cube are two interpretations of the same OMINO, not two independent objects or centroids.

---

## 23. Ball and sphere

For an (n)-dimensional bounded space:

* the (n)-ball is its interior;
* the ((n-1))-sphere is its boundary.

The OMI interpretation is:

```text
Centroid = fixed branch or reference point
N-ball   = bounded computation or incidence interior
N-sphere = projective boundary visible to an observer
```

This creates the containment:

[
\text{Centroid}
\subset
N\text{-ball}
\subseteq
\partial N\text{-sphere interpretation}
]

More precisely, the sphere is the boundary of the ball, not an outer volume containing the ball as another ordinary subset.

---

## 24. Tangent circumscription

A tangent circumscription places boundary elements around an interior object so that each boundary element meets the interior under a declared tangency rule.

The system interprets:

* centroid as branch origin;
* ball as bounded internal relation;
* sphere as observable projective closure;
* tangent spheres as externally addressable neighboring projections.

This may be used to define kissing configurations, but any claimed equality with a known lattice kissing arrangement requires a separate proof.

---

# Part VI — Tetrahedral Relational Spaces

## 25. Why tetrahedra

A tetrahedron is the simplest three-dimensional simplex.

It contains:

* four vertices;
* six edges;
* four triangular faces;
* one enclosed volume.

It is therefore a natural register for:

* four scopes;
* four views;
* four files;
* four duality assignments;
* four incidence sectors.

The tetrahedron should be treated as a relational carrier.

It does not mean all assigned objects are literal tetrahedral vertices in Euclidean space.

---

## 26. Four spatial interpretations

### 26.1 Tangent tetrahedron

The Tangent Tetrahedron represents the user-facing or interface-relative projection.

It is the surface at which a relational structure is selected, viewed, or cited.

Recommended role:

[
N_0=\text{projection-selection surface}
]

rather than another ordinary graph norm.

### 26.2 Regular tetrahedron

The Regular Tetrahedron represents local relational closure.

Recommended interpretation:

[
N_1=\text{local graph}
]

### 26.3 Stellated tetrahedron

The Stellated Tetrahedron introduces intersecting or antipodal tetrahedral orientations.

Recommended interpretation:

[
N_2=\text{remote or paired multigraph}
]

### 26.4 Triakis tetrahedron

The Triakis Tetrahedron expands each face into a pyramidal incidence structure.

Recommended interpretation:

[
N_4=\text{network hypergraph or graph-of-incidences}
]

This gives the doubling sequence:

[
1\rightarrow2\rightarrow4
]

as a projective norm progression.

---

## 27. Norm forms

The proposed norm interpretation is:

```text
Norm 0  Tangent selection or user projection
Norm 1  Local graph
Norm 2  Paired or remote multigraph
Norm 4  Network hypergraph
```

The word “norm” here is OMI-defined unless an explicit algebraic norm is supplied.

It means degree of projected relational multiplicity, not necessarily Euclidean length.

---

## 28. Polytope registers

The following should be interpreted as register assignments, not literal geometric vertex identities.

### Tangent tetrahedron register

```text
V1 Archimedean family, orientation 1
V2 Catalan family, orientation 1
V3 Archimedean family, orientation 2
V4 Catalan family, orientation 2
```

This captures primal and dual semiregular forms under two orientations.

### Regular tetrahedron register

A duality-preserving assignment is:

```text
V1 Cube
V2 Octahedron
V3 Dodecahedron
V4 Icosahedron
```

with dual pairs:

[
\text{Cube}\leftrightarrow\text{Octahedron}
]

[
\text{Dodecahedron}\leftrightarrow\text{Icosahedron}
]

### Four-dimensional registers

The 8-cell and 16-cell form a dual pair.

The 24-cell is self-dual.

The 120-cell and 600-cell form a dual pair.

These may be arranged as register values around a 4-simplex or 24-cell projection, but the phrase “vertices of the 24-cell” should not be used unless the construction literally assigns them to its 24 vertices.

---

## 29. Lambda block centroid

The expression:

[
(\operatorname{Snub}(\operatorname{Archimedean}\cdot\operatorname{Catalan}))
]

may be interpreted as a chiral mediation between a primal polyhedral family and its dual.

This is an OMI-defined symbolic operation.

A formal definition would require:

1. a domain of Archimedean and Catalan pairs;
2. a duality mapping;
3. a snub or chirality operator;
4. a result space;
5. invariants preserved by the transformation.

Until then it should be labeled:

> geometric construction schema

rather than established polyhedral identity.

---

# Part VII — The Relational Dimension Ladder

## 30. Signed relational levels

The proposed sequence is not ordinary geometric dimension.

It is a relational or incidence ladder.

|  Level | Geometric mnemonic             | Relational interpretation                            |
| -----: | ------------------------------ | ---------------------------------------------------- |
| (\pm1) | point                          | node, symbol, entity                                 |
| (\pm2) | line                           | edge, relation                                       |
| (\pm3) | triangle                       | graph, closed context                                |
| (\pm4) | square or tetrahedral volume   | incidence among relations                            |
| (\pm5) | pentagon or tesseract mnemonic | multigraph or graph-of-graphs                        |
| (\pm6) | hexagon                        | hypergraph                                           |
| (\pm7) | Fano plane                     | finite projective incidence closure                  |
| (\pm8) | octagon or octonion            | eight-coordinate multiplication or incidence carrier |

Positive and negative signs may represent:

* outward versus inward projection;
* primal versus dual;
* local versus remote;
* declaration versus definition;
* clockwise versus counterclockwise orientation.

The sign semantics must be frozen by the relevant project.

---

## 31. Existing 17-tier correspondence

The previous project already contains a closely related negative hierarchy:

```text
-1 RULES          Point / Node / 0-Sphere
-2 FACTS          Line / Edge / Sphere
-3 CLOSURES       Triangle / Graph / Plane / Tetrahedron
-4 COMBINATORS    Square / Incidence / Volume / Cube
-5 CONS           Pentagon / Multigraph / Solid / Tesseract
-6 CONFIGURATIONS Hexagon / Hypergraph / Hyper-Volume
-7 CLAUSES        Fano Plane
-8 MODULES        Octagon / Octonion / COBS-CONS
```

The new geometry therefore does not discard the prior ladder.

It provides a clearer foundational explanation of it.

---

# Part VIII — Circular Character Geometry

## 32. Character codes as a coordinate surface

ASCII and byte values do not define the geometry.

They provide a compact finite coordinate surface on which the geometry can be realized.

The full byte board is:

[
0x00\ldots0xFF
]

or:

[
{0,\ldots,255}
]

This forms a (16\times16) board:

[
\text{row}=\text{high nibble}
]

[
\text{column}=\text{low nibble}
]

The previous architecture already treats this as a COBS-CONS blackboard divided into local and remote macro-surfaces.

---

## 33. Low and high planes

Define:

[
L={0x00,\ldots,0x7F}
]

and:

[
H={0x80,\ldots,0xFF}
]

with reflection:

[
h(x)=x\oplus0x80
]

for (x\in L).

Then:

[
H=h(L)
]

The earlier OMINO specification already defines the high plane as the exact XOR reflection of the low plane.

This produces:

```text
low plane  = local or CAR projection
high plane = remote or CDR projection
```

This is an OMI encoding convention, not a property of Unicode itself.

---

## 34. Thirty-two-coordinate bars

A 32-coordinate bar is:

[
T=[T_0,T_1,\ldots,T_{31}]
]

partitioned into:

[
OMI(T)=[T_0,\ldots,T_{15}]
]

[
IMO(T)=[T_{16},\ldots,T_{31}]
]

Thus:

[
T=OMI(T)\oplus IMO(T)
]

where (\oplus) here means paired concatenation or direct-sum interpretation, not necessarily bitwise XOR.

A one-based notation may instead use:

[
[T_1,\ldots,T_{16}]
]

and:

[
[T_{17},\ldots,T_{32}]
]

but zero-based and one-based forms must not be mixed.

---

## 35. The role of SPACE

Assign:

[
0x20=\text{projective separator}
]

SPACE is useful because it is simultaneously:

* a character;
* a gap;
* a separator;
* a visible absence;
* the first conventional printable ASCII coordinate.

This gives:

[
0x00=\text{null origin}
]

[
0x20=\text{visible projective hinge}
]

The distinction is:

```text
0x00 = no projected expression
0x20 = separation between completed projected expressions
```

SPACE does not mean “nothing.”

It means a completed relational separation that remains addressable.

---

## 36. The control envelope

The sequence:

```text
0x1B ESC
0x1C FS
0x1D GS
0x1E RS
0x1F US
0x20 SPACE
```

forms a natural control-to-projection transition:

[
ESC
\rightarrow
FS
\rightarrow
GS
\rightarrow
RS
\rightarrow
US
\rightarrow
SPACE
]

A possible interpretation is:

```text
ESC   leave current interpretation
FS    select enclosing field
GS    select relational group
RS    select relation or record
US    select atomic unit
SPACE close and separate projection
```

This is one of the strongest concrete structures connecting the geometry to an existing encoding system.

---

## 37. The F-column nomogram

Define:

[
F(n)=16n+15
]

for:

[
n\in{0,1,\ldots,7}
]

This gives:

| (n) |    Hex | Symbol |
| --: | -----: | ------ |
|   0 | `0x0F` | SI     |
|   1 | `0x1F` | US     |
|   2 | `0x2F` | `/`    |
|   3 | `0x3F` | `?`    |
|   4 | `0x4F` | `O`    |
|   5 | `0x5F` | `_`    |
|   6 | `0x6F` | `o`    |
|   7 | `0x7F` | DEL    |

The architecture interprets:

[
0x0F
]

as an entry or lower gauge pointer,

[
0x1F\ldots0x6F
]

as six interior nomographic stations,

and:

[
0x7F
]

as terminal deletion, reversal, or return boundary.

Placed on a circle, `0x7F` may return tangentially to `0x0F`.

---

## 38. Four 32-position sectors

The low plane naturally partitions into four sectors:

```text
Sector 0: 0x00–0x1F
Sector 1: 0x20–0x3F
Sector 2: 0x40–0x5F
Sector 3: 0x60–0x7F
```

The earlier project defines a common XOR witness:

[
0x00\oplus0x1B\oplus0x1C\oplus0x1F=0x18
]

[
0x20\oplus0x3B\oplus0x3C\oplus0x3F=0x18
]

[
0x40\oplus0x5B\oplus0x5C\oplus0x5F=0x18
]

[
0x60\oplus0x7B\oplus0x7C\oplus0x7F=0x18
]

The sector prefix cancels because it appears an even number of times under XOR.

This creates a translation-invariant local boundary witness.

---

## 39. Twenty-eight plus four partition

Each 32-position sector may be decomposed as:

[
28+4=32
]

with:

```text
body          = positions *0 through *B
terminal hinge = positions *C through *F
```

For example:

```text
0x00–0x1B | 0x1C–0x1F
0x20–0x3B | 0x3C–0x3F
0x40–0x5B | 0x5C–0x5F
0x60–0x7B | 0x7C–0x7F
```

The four terminal positions may carry:

* file scope;
* group scope;
* record scope;
* unit scope;

or another declared four-coordinate control system.

---

## 40. Signed position around a hinge

For a selected hinge (h), define:

[
\delta_h(x)=x-h
]

Around `0x20`:

[
0x1F=-1
]

[
0x1E=-2
]

[
0x1D=-3
]

[
0x1C=-4
]

This gives a signed local coordinate without changing the underlying byte value.

Different operations must remain distinct:

[
x-1
]

means arithmetic predecessor;

[
\rho^{-1}(x)
]

means previous circular ruler station;

[
x^\ast
]

means projective dual;

[
\bar x
]

means declared inverse, complement, or palindromic reversal.

---

# Part IX — Palindromic Expressions and the Zero Witness

## 41. Palindromic notation

Let an expression be represented by coefficients:

[
p(x)=a_0+a_1x+\cdots+a_nx^n
]

Define its reversal:

[
p^\ast(x)
=========

x^n p(x^{-1})
]

A palindromic expression satisfies:

[
p(x)=p^\ast(x)
]

An anti-palindromic expression satisfies:

[
p(x)=-p^\ast(x)
]

over an appropriate coefficient structure.

---

## 42. Zero polynomial interpretation

The zero polynomial does not conventionally imply STDERR.

The architecture may, however, define a balanced projection law:

[
p(x)\oplus p^\ast(x)=0
]

meaning the forward and inverse projections cancel under the selected operation.

If the semantic content cancels while the execution remains observable, what remains is the witness that the comparison occurred.

This motivates:

[
\boxed{
\text{balanced zero result}
\rightarrow
\text{residual witness channel}
}
]

Therefore the system may treat STDERR as the canonical witness channel for balanced or unresolved projection.

This must be declared as an OMI operational law, not presented as a universal fact about polynomials.

---

# Part X — Hamming and Miquel Incidence

## 43. Seven-coordinate Hamming structure

The Hamming ([7,4,3]) code protects four data bits with three parity bits.

The existing system maps:

```text
Parity:
LOGOS
NOMOS
PATHOS

Data:
FS
GS
RS
US
```

This creates a seven-coordinate structure compatible with a Fano-plane incidence representation.

The correspondence is meaningful because the parity-check relations of the Hamming code can be represented through Fano incidence.

---

## 44. Eight-coordinate completed cell

Adding an overall parity coordinate gives an extended Hamming ([8,4,4]) SECDED cell.

The former system uses:

```text
Bit 0 LOGOS
Bit 1 NOMOS
Bit 2 FS
Bit 3 PATHOS
Bit 4 GS
Bit 5 RS
Bit 6 US
Bit 7 OMINO
```

The OMINO bit is the overall balance hinge.

The previous architecture explicitly defines this streaming map and its error outcome matrix.

The complete balance equation is:

[
OMINO=
LOGOS\oplus NOMOS\oplus FS\oplus PATHOS\oplus GS\oplus RS\oplus US
]

The complete-cell mismatch is:

[
m=
LOGOS\oplus NOMOS\oplus FS\oplus PATHOS\oplus GS\oplus RS\oplus US\oplus OMINO
]

This supplies a concrete residual witness.

---

## 45. Miquel interpretation

A Miquel configuration may provide a geometric visualization for the eight-coordinate extended cell.

However, the exact claimed incidence structure must be explicitly defined.

The words:

* Miquel configuration;
* cube face circles;
* rhombic dodecahedral Levi graph;
* extended Hamming cell;

must not be assumed identical without a construction showing:

1. the point set;
2. the block or circle set;
3. the incidence relation;
4. the code generator matrix;
5. the code parity-check matrix;
6. the mapping between geometric incidence and code coordinates.

---

# Part XI — Circular Slide Rulers

## 46. Ruler definition

A Circular Slide Ruler is a finite cyclic coordinate system:

[
\mathcal C_n=\mathbb Z/n\mathbb Z
]

with advancement:

[
\rho_k(x)=x+k\pmod n
]

It may support:

* forward rotation;
* inverse rotation;
* antipodal mapping;
* sector selection;
* projection lookup;
* finite coordinate composition.

The ruler is spatially represented.

It need not be executed through sequential traversal.

---

## 47. Algorithmic clock

An Algorithmic Clock advances logical position, not physical time.

Let:

[
c_{t+1}=F(c_t)
]

where (F) is deterministic and bounded.

The subscript (t) denotes logical step count, not wall-clock time.

The core requirement is:

[
c_0=c'_0
\land
I=I'
\Rightarrow
c_n=c'_n
]

for all bounded permitted steps (n).

The prior agent mandate already defines deterministic circular ruler advancement and prohibits dependence on wall-clock time, randomness, network state, thread scheduling, and external human interpretation.

---

## 48. Existing OMINO ruler geometry

The existing project defines one OMINO tile as containing:

* 16 blackboard face planes;
* 18 Local240 blackboard faces;
* four quadrants per Local240 face;
* 72 circular slide rulers;
* 60 ruler positions per ruler;
* 4,320 local incidences.

The accounting is:

[
18\times4=72
]

[
72\times60=4320
]

The geometry-first project should not initially assume these counts are universal.

It should derive the conditions under which this particular OMINO realization is selected.

---

# Part XII — Thirty-Two- and Sixty-Four-Dimensional Carriers

## 49. Cayley–Dickson dimensional sequence

The Cayley–Dickson process doubles dimensions:

[
1,2,4,8,16,32,64,\ldots
]

A 32-coordinate vector may be interpreted as coefficients:

[
X=\sum_{i=0}^{31}x_i e_i
]

A 64-coordinate vector may be interpreted as:

[
Y=\sum_{i=0}^{63}y_i e_i
]

This does not mean every byte is itself a trigintaduonion.

It means a 32-byte or 32-coordinate bar can carry one coefficient vector for a 32-dimensional algebraic element.

---

## 50. Blackboard interpretation

A 64-coordinate blackboard may interleave two surfaces:

```text
even positions or rows = tensor/state coordinates
odd positions or rows  = gauge/citation/witness coordinates
```

Formally:

[
\mathcal B=
\bigoplus_{r=0}^{31}
(T_r\oplus G_r)
]

where:

* (T_r) is a state or expression coordinate;
* (G_r) is its gauge, citation, residual, or annotation coordinate.

The term **blackboard pattern** is useful because the structure may support reading and writing.

The deeper geometric object is a circular scoping and projection surface.

---

## 51. Nonassociativity boundary

Higher Cayley–Dickson algebras lose familiar algebraic properties.

Therefore any implementation using 32- or 64-dimensional multiplication must declare:

* multiplication order;
* basis order;
* sign table;
* bracketing;
* conjugation;
* norm interpretation;
* whether zero divisors are permitted;
* which identities remain valid.

The algebraic dimension is not by itself an execution specification.

---

# Part XIII — Four-Quadrant 32-Bit Space

## 52. Exact partition

The unsigned 32-bit coordinate domain is:

[
0x00000000\ldots0xFFFFFFFF
]

Its four equal quadrants are:

```text
Q0 0x00000000–0x3FFFFFFF
Q1 0x40000000–0x7FFFFFFF
Q2 0x80000000–0xBFFFFFFF
Q3 0xC0000000–0xFFFFFFFF
```

The selector is:

[
q(x)=x\gg30
]

producing:

```text
00 Q0
01 Q1
10 Q2
11 Q3
```

Possible assignments include:

```text
Q0 user
Q1 local
Q2 remote
Q3 network
```

or:

```text
Q0 FS
Q1 GS
Q2 RS
Q3 US
```

The assignment must be explicit.

---

# Part XIV — Leech and Lorentzian Analogies

## 53. Standard structures

The Leech lattice is a 24-dimensional positive-definite even unimodular lattice with no vectors of squared length two.

The lattice commonly denoted:

[
II_{25,1}
]

is an even unimodular Lorentzian lattice of signature ((25,1)).

There is a deep relation between null directions in the Lorentzian lattice and 24-dimensional positive-definite quotient structures related to the Leech lattice.

---

## 54. OMI interpretation

A safe architectural analogy is:

```text
II_25,1 ambient space
    -> signed remote or projective horizon

null vector
    -> selected tangent or gauge direction

orthogonal complement modulo null direction
    -> centroid-relative observable quotient

Leech lattice
    -> 24-dimensional residual or boundary incidence field
```

This can motivate a model of:

* ambient authority;
* null tangent;
* quotient projection;
* finite observable coordinate field.

It does not prove that a Triakis tetrahedron kissing configuration is the Leech lattice.

---

## 55. Retrieval, not search

High-dimensional lattice language should describe a fixed coordinate retrieval boundary, not justify an unbounded nearest-neighbor search.

The previous system explicitly treats its Leech and (II_{25,1}) language as a coordinate retrieval boundary and forbids using it as permission for search loops.

Any implementation must distinguish:

[
\text{fixed bounded coordinate extraction}
]

from:

[
\text{unbounded optimization or lattice search}
]

---

# Part XV — Geometry-to-Encoding Mapping

## 56. Canonical mapping table

A proposed first mapping is:

| Geometric concept       | Encoding realization |
| ----------------------- | -------------------- |
| null centroid           | `0x00`               |
| escape from chart       | `0x1B`               |
| file or field scope     | `0x1C`               |
| group/lambda scope      | `0x1D`               |
| record/relation scope   | `0x1E`               |
| unit tangent            | `0x1F`               |
| projective separator    | `0x20`               |
| local terminal boundary | `0x7F`               |
| remote reflection       | `x ^ 0x80`           |
| full byte closure       | `0xFF`               |

This table is provisional until the geometry and encoding authorities formally freeze it.

---

## 57. Empty, complete, and annotated states

A useful three-stage interpretation is:

### Empty notation

[
0x00
]

No active projected expression.

### Complete notation

[
0x20
]

The expression has reached a visible separating hinge.

### Annotated or remote notation

[
0x80
]

The coordinate has crossed into the reflected high-plane interpretation.

This should not be confused with standard Unicode plane boundaries.

It is an OMI byte-plane convention.

---

# Part XVI — Relationship to Existing OMI Projects

## 58. Historical direction

The prior project discovered the geometry through implementation.

Its direction was approximately:

```text
bytes
-> registers
-> scope bits
-> circular rulers
-> blackboard faces
-> Fano and Hamming incidence
-> polytope and lattice interpretation
```

The new project reverses the derivation:

```text
distinction
-> incidence
-> block design
-> tangency
-> projection
-> finite ruler
-> coordinate encoding
-> executable register law
```

---

## 59. Existing repository boundaries

The previous workspace is a collection of separate repositories with isolated roles.

Its own workspace map states that they should not be treated as duplicates and that the correct existing compiler/declaration path must be inspected before creating a new emitter.

Therefore the new geometry project should not initially replace:

* the Omnicron compiler;
* the OMI---IMO compiler;
* Omnicron ISA;
* Omnicron Lisp;
* Omnicron Port;
* Omnicron Canon;
* OMINO executable surfaces.

It should define an upstream geometric authority that these projects may implement or reference.

---

## 60. Proposed authority chain

```text
Tangential Block Geometry
    geometric source authority
        |
        v
OMI / OMINO Canon
    encoding and naming authority
        |
        v
OMI-Lisp / Omnicron-Lisp
    readable declaration surfaces
        |
        v
OMI ISA / Omnicron ISA
    bounded deterministic operation semantics
        |
        v
OMI---IMO / Omnicron compiler
    lowering and artifact generation
        |
        v
OMINO / Omnicron runtime
    coordinate execution and projection
```

The geometry project should not generate downstream files until explicit mapping contracts exist.

---

## 61. Preserved implementation principles

The following principles should be preserved.

### Determinism

For identical inputs and starting coordinates, the result must be identical.

### Fixed centroid

All local orientations resolve relative to one canonical centroid.

### Bounded execution

The core operates over declared finite coordinate domains.

### Exact transforms

Inner arithmetic uses declared operations such as:

* XOR;
* shift;
* rotate;
* mask;
* bounded addition;
* bounded carry;
* table or bit extraction.

### Outside-in interpretation

Human semantics, policies, adapters, filesystems, networking, and user interfaces approach from outside the deterministic core.

The existing agent mandate already states that the OMI core is algorithmic determinism only and that other forms approach from the outside as carriers, adapters, scaffolds, proofs, views, and tests.

---

# Part XVII — Proposed Formal Object Model

## 62. Tangential block system

Define a Tangential Block System as:

[
\mathfrak T=
(P,\mathcal B,I,\tau,\Lambda,\Omega,\Pi,\mathcal R)
]

where:

* (P): point set;
* (\mathcal B): block family;
* (I\subseteq P\times\mathcal B): incidence;
* (\tau): tangency relation;
* (\Lambda): tangent-selection operation;
* (\Omega): orientation set;
* (\Pi={\Pi_\omega\mid\omega\in\Omega}): projection family;
* (\mathcal R): residual witness domain.

---

## 63. Required laws

### Law 1 — Point distinguishability

[
p_i=p_j
]

only when they are the same declared coordinate under the active chart.

### Law 2 — Block boundedness

Every active block has finite declared membership.

### Law 3 — Tangent preservation

If:

[
\tau(B_i,B_j)
]

then the tangent operation preserves the identities of (B_i) and (B_j) while exposing their shared relation.

### Law 4 — Projection determinism

For fixed (\omega):

[
\Pi_\omega(X)
]

must produce the same result for the same (X).

### Law 5 — Centroid uniqueness

One bounded object has one canonical centroid.

### Law 6 — Antipodal relativity

An antipode is an orientation relative to the centroid, not a second centroid.

### Law 7 — Residual visibility

Every lossy or failed projection must produce a bounded residual witness or an explicit declaration that no witness is retained.

### Law 8 — Encoding reversibility

Where an encoding claims losslessness:

[
decode(encode(X))=X
]

### Law 9 — Scope explicitness

Every projected expression must either declare its scope or inherit scope through an explicit rule.

### Law 10 — Representation separation

Geometric identity must not depend on one specific byte, filename, syntax, or programming language unless that dependence is explicitly part of the object definition.

---

# Part XVIII — Expression Semantics

## 64. Observer expression

The expression:

[
\Lambda(
Observer_{in},
Observation,
Observer_{out}
)
]

does not require that the two observers are different people.

They may be:

* the same observer at two logical steps;
* local and remote views;
* input and output states;
* producer and consumer;
* declaration and reconstruction contexts.

The observation is the tangent mediator.

---

## 65. Operation expression

The expression:

[
\Lambda(
Declaration,
Definition,
Operation
)
]

means:

* declaration selects what is addressable;
* definition constrains its relation;
* operation projects the relation into an executable result.

An operation without a declaration is unaddressed.

A declaration without a definition is underconstrained.

A definition without an operation may remain potential rather than realized.

---

## 66. CONS expression

The expression:

[
CONS(CAR,CDR)
]

is interpreted geometrically as tangential pairing.

CAR and CDR are not merely memory fields.

They are opposing or complementary projected surfaces joined through one CONS relation.

This gives:

[
CONS=
\Lambda(CAR,CDR)
]

with a selected orientation deciding which side is read as local, remote, declaration, definition, input, or continuation.

---

# Part XIX — Nonclaims and Safety Boundaries

## 67. This paper does not claim

This paper does not claim that:

* every idea is literally a Euclidean polytope;
* every seven-point structure is a Fano plane;
* paired Fano planes automatically form a biplane;
* ASCII was historically designed for OMI;
* Unicode spans every 32-bit value;
* a Triakis tetrahedron is the Leech lattice;
* the OMINO coordinate system proves universal (P=NP);
* a 32-byte string automatically implements trigintaduonion multiplication;
* a geometric analogy is a proof of algebraic equivalence;
* fixed-width constant-time extraction solves arbitrary unbounded search problems.

The previous OMI mandate also explicitly limits its constant-time claims to fixed declared local surfaces and rejects inflating those claims into universal (P=NP).

---

## 68. Required proof discipline

Every strong relation should be labeled as one of:

```text
proved
implemented
defined_model
interpretation
encoding_choice
open_conjecture
historical_motivation
```

For example:

```text
The Fano plane has seven points.
Status: proved mathematical fact.

C7 assigns NULL, ESC, FS, GS, RS, US, and SPACE to those points.
Status: encoding_choice.

GS is the lambda point.
Status: defined_model.

The resulting controller is implemented with a [7,4,3] Hamming syndrome.
Status: implemented, when code and tests exist.

The Triakis network projection corresponds exactly to II_25,1.
Status: open_conjecture unless an explicit isomorphism is proved.
```

---

# Part XX — Validation Program

## 69. Geometry validation

The new project should first verify:

1. all primitive terms are defined;
2. all point and block sets are finite or bounded;
3. every incidence relation is explicit;
4. every tangent operation has a declared domain and codomain;
5. every projection specifies its orientation;
6. every claimed duality is involutive where required;
7. centroid uniqueness is preserved;
8. residual behavior is defined.

---

## 70. Encoding validation

The encoding layer should verify:

1. no byte is assigned incompatible canonical meanings;
2. low/high reflection is exactly defined;
3. zero-based and one-based indices are not mixed;
4. sector boundaries are exact;
5. circular wrap behavior is exact;
6. signed hinge offsets are distinguished from byte values;
7. control values retain their declared names;
8. round-trip encoding succeeds where losslessness is claimed.

---

## 71. Implementation validation

The runtime should test:

* deterministic repetition;
* boundary positions;
* inverse rotations;
* antipodal orientation;
* Fano incidence;
* Hamming syndrome correction;
* extended parity;
* COBS framing;
* CONS linkage;
* low/high reflection;
* residual generation;
* zero and full closure states;
* malformed projection rejection.

---

## 72. Proof validation

Formal proofs should be limited to exact finite claims.

Suitable proof targets include:

```text
centroid uniqueness
projection determinism
sector witness invariance
XOR high-plane involution
Hamming correction correctness
extended parity outcome classification
circular rotation closure
antipodal involution
finite block membership
encoding round-trip
```

Unsuitable inflated conclusions include:

```text
universal cognition is solved
all concepts are isomorphic
all geometry is computationally equivalent
P equals NP
the Leech lattice identity follows from a visual analogy
```

---

# Part XXI — Proposed Project Structure

## 73. Geometry-first repository

A clean initial repository might contain:

```text
README.md
WHITEPAPER.md
GLOSSARY.md
STATUS.md

00-FOUNDATIONS.md
01-POINTS-AND-DISTINCTIONS.md
02-BLOCKS-AND-INCIDENCE.md
03-TANGENCY-AND-LAMBDA.md
04-PROJECTION-AND-RESIDUAL.md
05-FANO-CONTROLLER.md
06-TETRAHEDRAL-SPACES.md
07-CIRCULAR-GAUGE.md
08-ENCODING-MAP.md
09-OMI-COMPATIBILITY.md
10-CONFORMANCE.md
```

The first implementation should be a verifier, not a compiler.

It should answer questions such as:

```text
Is the point set valid?
Are all blocks legal?
Does the Fano design satisfy incidence?
Is the selected lambda point present?
Is the projection deterministic?
Does the byte mapping collide?
Does XOR reflection return to the original coordinate?
Does the circular ruler close?
```

---

## 74. Separation from prior repositories

The new repository should not initially:

* import implementation code from existing projects;
* regenerate `.omi`, `.imo`, or `.o` files;
* rename OMINO components;
* replace the existing compilers;
* claim authority over old runtime behavior;
* mutate previous proof registries.

Instead it should publish mapping documents.

For example:

```text
TBGeometry::Centroid
    maps to
OMINO_CENTROID_POINT

TBGeometry::Antipode
    maps to
omino_resolve_antipode_*

TBGeometry::Residual
    maps to
overall_mismatch or STDERR projection

TBGeometry::UnitTangent
    maps to
US / 0x1F
```

---

# Part XXII — Consolidated System

## 75. Minimal system tuple

The complete bounded realization may be summarized as:

[
\boxed{
\mathcal O=
(C_7,F_8,T_{32},Q_4,\mathfrak T)
}
]

where:

* (C_7) is the seven-point controller;
* (F_8) is the eight-station F-column ruler;
* (T_{32}) is the OMI/IMO coordinate bar;
* (Q_4) is the four-quadrant 32-bit projection space;
* (\mathfrak T) is the underlying tangential block system.

---

## 76. Execution cycle

A complete conceptual execution cycle is:

```text
1. Begin at the centroid.
2. Select an orientation.
3. Choose or inherit a scope.
4. Select the active block design.
5. Pinch or branch at the lambda point.
6. Project the structure into an expression.
7. Encode the expression into a bounded coordinate surface.
8. Apply the deterministic transformation.
9. Compare realized and intended projections.
10. Emit the residual witness.
11. Close at the separator or deletion boundary.
12. Return circularly to the next centroid-relative state.
```

In symbolic form:

[
p_0
\overset{\omega}{\longrightarrow}
B
\overset{\Lambda}{\longrightarrow}
E
\overset{encode}{\longrightarrow}
c
\overset{F}{\longrightarrow}
c'
\overset{decode}{\longrightarrow}
E'
\overset{\ominus}{\longrightarrow}
R
]

---

# Part XXIII — Central Conclusions

## 77. First conclusion

The new project is not a replacement implementation.

It is the missing geometry-first authority beneath the existing implementation.

---

## 78. Second conclusion

The earlier OMI/OMINO project discovered a real and coherent structure:

* one fixed centroid;
* paired local and remote planes;
* circular coordinate systems;
* Fano and Hamming incidence;
* scope separators;
* residual witnesses;
* deterministic bounded transformations.

The new project should preserve these discoveries while separating them from the historical implementation vocabulary.

---

## 79. Third conclusion

The strongest concrete bridge is the control sequence:

```text
NULL
ESC
FS
GS
RS
US
SPACE
```

combined with:

* the seven-point Fano carrier;
* the `?F` hexadecimal column;
* four 32-position sectors;
* the `^ 0x80` low/high reflection;
* the 32-coordinate OMI/IMO bar.

These are sufficiently precise to support formal definitions and executable tests.

---

## 80. Fourth conclusion

The polytope, octonion, Leech lattice, and Lorentzian structures should remain in the project, but with explicit status labels.

They may serve as:

* interpretation models;
* coordinate inspirations;
* proof targets;
* retrieval structures;
* duality registers.

They should not be treated as established equivalences until maps and invariants are proved.

---

## 81. Final statement

Tangential Block Geometry begins from the proposition that expression is not fundamentally a string, object, instruction, or function.

Expression is a bounded projection of relational incidence.

The basic form is:

[
\boxed{
E=
\Pi_\omega
\left(
\Lambda(B_i,B_j)
\right)
}
]

The basic witness is:

[
\boxed{
R=
E_{\mathrm{realized}}
\ominus
E_{\mathrm{intended}}
}
]

The basic computational discipline is:

[
\boxed{
\text{same bounded input}
+
\text{same centroid}
+
\text{same orientation}
\Rightarrow
\text{same projected result}
}
]

The basic architectural direction is:

[
\boxed{
\text{Geometry}
\rightarrow
\text{Incidence}
\rightarrow
\text{Projection}
\rightarrow
\text{Encoding}
\rightarrow
\text{Execution}
}
]

The previous project reached this geometry from the outside inward.

The new project begins at the center and builds outward.
