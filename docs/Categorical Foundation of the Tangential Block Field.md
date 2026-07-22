# Categorical Foundation of the Tangential Block Field

## 1. Purpose

The Tangential Block Field is a categorical model for autonomous contextual structures that become jointly observable through bounded projection and declared composition.

Its primitive language is:

```text
object
morphism
context
block
interface
tangency
projection
chart
gluing
overlap
residual
field
```

It does not begin with:

```text
memory
pointers
CAR
CDR
CONS
ASCII
registers
hardware boards
Lisp cells
files
network nodes
```

Those may later implement the theory, but they do not define it.

The central equivalence is:

[
\boxed{
\text{Blackboard Pattern}
=========================

\text{Tangential Block Field viewed computationally}
}
]

Categorically, this becomes:

[
\boxed{
\text{Shared Field}
===================

\text{a colimit of context-block contributions}
}
]

with overlap detected through pullbacks and unresolved structure retained in a residual object.

---

# 2. Base category

Let:

[
\mathcal T
]

denote the **category of tangential blocks**.

An object of (\mathcal T) is a bounded context block.

A morphism in (\mathcal T) is a structure-preserving contextual transformation.

For the initial finite theory, the safest concrete model is a category of finite structured sets:

[
\mathcal T\subseteq\mathbf{FinSet}_{\Sigma}
]

where (\Sigma) denotes whatever finite incidence, orientation, scope, and boundary structure has been declared.

This supplies ordinary categorical constructions without claiming that every possible Tangential Block Field must be set-based.

The first implementation may therefore use:

* finite sets as carriers;
* injective morphisms for inclusions;
* functions for transformations;
* products for paired context;
* pullbacks for common incidence;
* pushouts for gluing;
* coproducts for disjoint composition;
* quotients or coequalizers for identified projections.

---

# 3. Tangential block

A **Tangential Block** is an object:

[
B\in\operatorname{Ob}(\mathcal T)
]

equipped with enough declared structure to distinguish:

[
B=
(
|B|,
I_B,
\partial B,
\Omega_B
)
]

where:

* (|B|) is the finite carrier;
* (I_B) is its internal incidence structure;
* (\partial B) is its available interface or boundary;
* (\Omega_B) is its set of permitted orientations or viewpoints.

A block is autonomous.

It exists independently of whether it is currently projected into a shared field.

Therefore:

[
B\neq\Pi(B)
]

in general.

A projection of a block is a view of the block, not necessarily the complete block.

---

# 4. Context block

A **Context Block** is a Tangential Block together with a chosen interpretive context.

Write:

[
(B,\kappa)
]

where:

[
\kappa:B\rightarrow C
]

maps the block into a context object (C).

The context may specify:

* scope;
* orientation;
* observer position;
* ownership;
* admissible interfaces;
* resolution profile;
* projection target.

The context is not hidden global state.

It is an explicit morphism.

Two uses of the same underlying block may therefore be different contextual objects:

[
(B,\kappa_1)
\neq
(B,\kappa_2)
]

even when their underlying carrier is the same.

---

# 5. Interface object

Tangency is represented through an **interface object**:

[
A
]

together with morphisms into two blocks:

[
A\xrightarrow{i}B
]

[
A\xrightarrow{j}C
]

This forms a span:

[
B\xleftarrow{i}A\xrightarrow{j}C
]

The interface (A) specifies exactly what the blocks share.

It may represent:

* a common boundary;
* a shared point;
* a common scope;
* an agreed incidence;
* a translation surface;
* a comparison witness.

This is the categorical normalization of a tangent.

The tangent is not merely a point at which two shapes visually touch. It is a declared common object through which two blocks are related.

---

# 6. Tangency

Two blocks (B) and (C) are **tangent along (A)** when there exists a span:

[
B\xleftarrow{i}A\xrightarrow{j}C
]

whose legs preserve the required boundary and incidence structure.

Write:

[
B\mathrel{\tau_A}C
]

Tangency preserves distinction:

[
B\neq C
]

while exposing common structure through (A).

This is preferable to an unrestricted merge because it states exactly:

* what is shared;
* how it enters each block;
* which identities remain separate;
* what may be glued.

The word **tangent** therefore denotes a structured interface relation.

---

# 7. Tangential gluing

Given:

[
B\xleftarrow{i}A\xrightarrow{j}C
]

the blocks may be glued by constructing a pushout:

[
B\sqcup_A C
]

represented by:

[
\begin{array}{ccc}
A & \xrightarrow{j} & C\
\downarrow i & & \downarrow\
B & \longrightarrow & B\sqcup_A C
\end{array}
]

The pushout is the universal object obtained by joining (B) and (C) along the declared interface (A).

This operation is called **Tangential Gluing**.

It replaces implementation-specific terms for pair construction or shared-board composition.

The notation may be:

[
B\otimes_A C
]

provided the project explicitly states that (\otimes_A) denotes pushout-style tangential gluing and not an ordinary tensor product.

The canonical notation should preferably remain:

[
B\sqcup_A C
]

because it states the construction clearly.

---

# 8. Disjoint composition

When the interface is initial:

[
A=0
]

the gluing reduces to a coproduct:

[
B\sqcup_0 C
\cong
B\sqcup C
]

This is **disjoint composition**.

It is appropriate when two context blocks contribute independently and share no active incidence.

The injections are:

[
\iota_B:B\rightarrow B\sqcup C
]

[
\iota_C:C\rightarrow B\sqcup C
]

Disjoint composition preserves the identity and origin of both contributors.

In a concrete Boolean or bit-set realization, this corresponds to disjoint union under the condition:

[
B\cap C=\varnothing
]

but the categorical definition is the coproduct, not a bitwise operation.

---

# 9. Overlap

The shared content of two contributions is represented by a pullback.

Given projection or inclusion morphisms:

[
f:B\rightarrow F
]

[
g:C\rightarrow F
]

their overlap is:

[
B\times_F C
]

with the pullback square:

[
\begin{array}{ccc}
B\times_F C & \longrightarrow & C\
\downarrow & & \downarrow g\
B & \xrightarrow{f} & F
\end{array}
]

The pullback contains the pairs of elements that become identified in the common field (F).

Thus:

[
\boxed{
\text{Overlap}
==============

\text{pullback over the shared field}
}
]

In a finite-set realization:

[
B\times_F C
===========

{
(b,c)\mid f(b)=g(c)
}
]

Overlap is not inherently a failure.

Its interpretation depends on the declared composition policy.

It may represent:

* agreement;
* common incidence;
* collision;
* ambiguity;
* duplicated ownership;
* an intended tangent.

---

# 10. Projection

A **projection** is a morphism:

[
\pi_B:B\rightarrow F
]

from a context block (B) into a shared field (F).

The field coordinate:

[
\pi_B(b)
]

is the visible image of (b), not necessarily its full identity.

Projection may be non-injective.

Therefore:

[
\pi_B(b_1)=\pi_B(b_2)
]

does not imply:

[
b_1=b_2
]

unless (\pi_B) is declared monic.

This gives the categorical form of the earlier law:

[
\boxed{
\text{Projected position is a view, not complete identity.}
}
]

A faithful identity-preserving representation requires either:

* a monomorphism;
* an attached provenance object;
* a factorization preserving the source;
* a jointly monic family of projections.

---

# 11. Projection factorization

A projection should be factored into distinct stages:

[
B
\xrightarrow{q_B}
\operatorname{Im}(\pi_B)
\xrightarrow{m_B}
F
]

where:

* (q_B) maps the complete block onto its visible image;
* (m_B) includes that image into the shared field.

In a regular category, this is the image factorization:

[
\pi_B=m_B\circ q_B
]

This separates:

1. information removed by projection;
2. the resulting visible contribution;
3. the placement of that contribution in the field.

The kernel pair of (q_B) identifies elements that the projection cannot distinguish.

That kernel pair formally captures projection aliasing.

---

# 12. Chart

A **chart** is a bounded projection:

[
\chi_i:F_i\rightarrow U_i
]

or, depending on orientation:

[
\chi_i:U_i\rightarrow F
]

where (U_i) is a coordinate object.

A family of charts:

[
{\chi_i}_{i\in I}
]

covers the field when their images jointly include all visible positions.

Categorically, the family is jointly epimorphic when:

[
\coprod_{i\in I}U_i\rightarrow F
]

is an epimorphism.

The older selector rectangles can therefore be normalized as an indexed chart family:

[
\mathcal U=
{U_0,U_1,\ldots,U_7}
]

without making hexadecimal boundaries part of the foundational theory.

The eight-region layout in the source material is one concrete chart decomposition, not the definition of the field.

---

# 13. Chart selector

A selector is not fundamentally a hardware switch or table index.

It is an indexing morphism or classification functor.

Let (I) be a discrete category of chart indices.

A chart assignment is a functor:

[
U:I\rightarrow\mathcal T
]

where:

[
i\mapsto U_i
]

A point or contribution may be classified by:

[
\sigma:F\rightarrow I
]

when each field element has one unique chart, or by a relation when charts overlap.

The selector therefore answers:

> Through which chart is this field element currently represented?

The forward chart map and reverse classification map should be distinguished:

[
e_i:U_i\rightarrow F
]

[
\sigma:F\rightarrow I
]

A strict inverse exists only when the decomposition is genuinely disjoint and exhaustive.

---

# 14. Orientation

An orientation is represented by an automorphism or equivalence:

[
\alpha:F\rightarrow F
]

An antipodal orientation satisfies:

[
\alpha\circ\alpha=1_F
]

Such an (\alpha) is an involution.

This replaces foundational use of “local” and “remote.”

Instead, the theory has:

[
F^+
]

and:

[
F^-
]

as two oriented subobjects or two fibers exchanged by (\alpha).

If:

[
\alpha(F^+)=F^-
]

and:

[
\alpha(F^-)=F^+
]

then they are opposing views of one field.

The terms **local** and **remote** may later label these orientations in a computational realization, but they are not category-theoretic primitives.

---

# 15. Tangential Block Field

A **Tangential Block Field** is a structured object:

[
\mathbb F=
(
F,
\mathcal B,
\Pi,
\mathcal A,
\mathcal G,
\mathcal R
)
]

where:

* (F) is the shared field object;
* (\mathcal B) is a category or indexed family of context blocks;
* (\Pi) is a family of projection morphisms into (F);
* (\mathcal A) is a family of interface objects;
* (\mathcal G) is a family of permitted gluing constructions;
* (\mathcal R) is a residual assignment.

For each block (B_i):

[
\pi_i:B_i\rightarrow F
]

is its field projection.

For each declared tangent between (B_i) and (B_j), there is an interface span:

[
B_i\leftarrow A_{ij}\rightarrow B_j
]

and, where permitted, a gluing object:

[
B_i\sqcup_{A_{ij}}B_j
]

---

# 16. Field as a colimit

Let:

[
D:J\rightarrow\mathcal T
]

be a diagram containing the active context blocks and their declared interfaces.

The shared field is:

[
F=\operatorname{colim}D
]

when that colimit exists.

This is the categorical normalization of the computational blackboard.

Each active block has a canonical cocone morphism:

[
\iota_j:D(j)\rightarrow F
]

The universal property says that any other object (X) receiving a compatible family of maps from the same diagram receives one unique map from (F):

[
\operatorname{Hom}(F,X)
\cong
\operatorname{Cocone}(D,X)
]

Thus the field is not merely a container.

It is the universal compatible composition of the active block diagram.

---

# 17. Tangential field contribution

A **field contribution** is a morphism:

[
c_i:B_i\rightarrow F
]

together with its source identity.

The source morphism must remain known, because the image alone may not identify its origin.

A contribution can therefore be represented as an object of the slice category:

[
\mathcal T/F
]

whose objects are arrows into the field:

[
(B_i\xrightarrow{c_i}F)
]

This is a particularly natural standardization.

The category:

[
\mathcal T/F
]

is the category of blocks contextualized by their projection into the shared field.

A morphism between two contributions is a commuting triangle:

[
\begin{array}{ccc}
B_i & \xrightarrow{h} & B_j\
& \searrow c_i & \downarrow c_j\
& & F
\end{array}
]

such that:

[
c_j\circ h=c_i
]

This means the transformation preserves field placement.

---

# 18. Tangential context

A **Tangential Context** may therefore be defined as an object in the slice category:

[
(B\xrightarrow{\pi}F)\in\mathcal T/F
]

This should replace the less precise phrase “Blackboard Context Block.”

The recommended canonical term is:

[
\boxed{
\text{Tangential Context Block}
}
]

A Tangential Context Block consists of:

1. an autonomous block (B);
2. a declared field (F);
3. a projection (\pi:B\rightarrow F);
4. optional interface spans to other blocks;
5. a residual assignment for lost or conflicting incidence.

The computational blackboard contribution is one implementation of this categorical object.

---

# 19. Compatibility

A family of contributions:

[
\pi_i:B_i\rightarrow F
]

is **compatible** when the projections agree on every declared interface.

For:

[
B_i\xleftarrow{u}A\xrightarrow{v}B_j
]

compatibility requires:

[
\pi_i\circ u
============

\pi_j\circ v
]

This commuting condition is the exact categorical meaning of agreement along a tangent.

If the equality fails, the contributions do not glue over that interface without additional resolution.

---

# 20. Conflict

A conflict is a failure of a required diagram to commute.

For the interface:

[
B_i\xleftarrow{u}A\xrightarrow{v}B_j
]

the two induced maps are:

[
\pi_i\circ u:A\rightarrow F
]

and:

[
\pi_j\circ v:A\rightarrow F
]

Compatibility requires equality.

Conflict occurs when:

[
\pi_i\circ u
\neq
\pi_j\circ v
]

This is more general than set overlap.

Two contributions may overlap and still agree.

They conflict only when they assign incompatible images to structure that was required to be shared.

---

# 21. Residual object

The **Residual Object** records the failure of required compatibility or the information discarded by projection.

There is no single universal residual construction in every category.

The project should therefore distinguish several forms.

## 21.1 Projection residual

For:

[
\pi:B\rightarrow F
]

the kernel pair:

[
B\times_F B
]

records which source elements become indistinguishable after projection.

This is the residual of identification.

## 21.2 Interface residual

For two interface maps:

[
f,g:A\rightrightarrows F
]

their equalizer:

[
E\rightarrow A
]

contains the part on which they agree.

The complement of (E), when the category supports complements, contains the disagreement.

## 21.3 Overlap residual

For two field contributions:

[
B\rightarrow F
]

and:

[
C\rightarrow F
]

their pullback:

[
B\times_F C
]

records common field incidence.

Whether this common incidence is accepted or residual depends on the policy.

## 21.4 Quotient residual

A coequalizer:

[
A
\overset{f}{\underset{g}{\rightrightarrows}}
F
\rightarrow
Q
]

may identify disagreements according to a declared resolution law.

The quotient (Q) is the resolved field, while the coequalized distinction is retained in the provenance of the construction.

---

# 22. Resolution policy

A **Resolution Policy** is a declared choice of categorical construction.

It is not hidden behavior.

Examples include:

| Intent                         | Categorical construction |
| ------------------------------ | ------------------------ |
| preserve independent blocks    | coproduct                |
| glue along shared interface    | pushout                  |
| find common incidence          | pullback                 |
| retain only agreement          | equalizer                |
| identify equivalent images     | coequalizer              |
| pair without identification    | product                  |
| classify contribution by field | slice object             |
| combine an indexed family      | colimit                  |
| inspect a compatible family    | limit                    |

No one construction should be called the universal composition operation.

The chosen construction depends on the intended relation.

---

# 23. Disjoint field family

A family:

[
{B_i\xrightarrow{\pi_i}F}_{i\in I}
]

is field-disjoint when the pullback of every distinct pair is initial:

[
B_i\times_F B_j\cong0
\qquad
(i\neq j)
]

This is the categorical form of pairwise non-overlap.

When the family is field-disjoint, the induced map:

[
\coprod_i B_i\rightarrow F
]

preserves independent origins.

If this map is monic, the disjoint family embeds faithfully into the field.

If it is also epic, the contributions cover the field.

---

# 24. Field cover

The family of contributions covers (F) when:

[
[\pi_i]:
\coprod_iB_i\rightarrow F
]

is an epimorphism.

It is a **disjoint cover** when it is also monic under the relevant categorical assumptions.

A chart decomposition is therefore a cover by coordinate blocks.

The eight-region construction in the historical material can be interpreted as an eight-object cover whose lower four and upper four were assigned opposing computational orientations.

The categorical theory retains:

* eight indexed charts;
* a two-part orientation;
* a four-by-two decomposition;

but does not retain the old byte names as primitive concepts.

---

# 25. Two-sided field

A **Two-Sided Tangential Field** is an object (F) equipped with:

* subobjects (F^+\hookrightarrow F) and (F^-\hookrightarrow F);
* an involution (\alpha:F\rightarrow F);
* exchange laws:

[
\alpha(F^+)=F^-
]

[
\alpha(F^-)=F^+
]

[
\alpha^2=1_F
]

These sides may later be interpreted as:

* internal and external;
* source and continuation;
* declaration and response;
* incoming and outgoing;
* local and remote.

The categorical standard should use:

```text
positive orientation
negative orientation
```

or:

```text
source-oriented side
target-oriented side
```

until an application assigns domain-specific semantics.

---

# 26. Circular structure

A circular or slide-rule realization is categorically an action of a cyclic group.

Let:

[
C_n
]

be the cyclic group of order (n).

A circular Tangential Block Field carries an action:

[
\rho:C_n\rightarrow\operatorname{Aut}(F)
]

For each (k\in C_n):

[
\rho_k:F\rightarrow F
]

and:

[
\rho_0=1_F
]

[
\rho_{a+b}=\rho_a\circ\rho_b
]

This replaces mechanical-clock language with a standard group action.

A logical step is an automorphism:

[
x\mapsto\rho_1(x)
]

A relative displacement is:

[
\rho_b\circ\rho_a^{-1}
]

No physical time is required.

---

# 27. Tangent position

A **Tangent Position** is not a special numeric character.

It is a selected interface or marked point:

[
t:1\rightarrow F
]

where (1) is a terminal object.

A marked field is therefore:

[
(F,t)
]

Different observer positions may choose different tangent points:

[
t_\omega:1\rightarrow F
]

The historical claim that any element may act as the center depending on viewpoint is best normalized as a family of marked-object structures, not as multiple intrinsic centroids.

A distinguished canonical center, when needed, is one chosen global element:

[
c:1\rightarrow F
]

A viewpoint-relative tangent need not equal the canonical center.

---

# 28. Observer

An observer should not be introduced as an unexplained agent.

Categorically, an observer is a functor:

[
O:\mathcal T\rightarrow\mathcal V
]

from Tangential Blocks to a category of views (\mathcal V).

The observer sends:

* blocks to visible representations;
* morphisms to visible transformations;
* commuting diagrams to consistent visible diagrams.

A faithful observer preserves distinguishability of morphisms.

A non-faithful observer may collapse different structures into the same view.

Thus observer-relative information loss is ordinary functorial non-faithfulness.

---

# 29. View

A **View** is the image of an object under an observer functor:

[
O(B)
]

A field may admit multiple observers:

[
O_1,O_2,\ldots,O_n
]

producing different views of one shared categorical structure.

The theory therefore separates:

[
B
]

from:

[
O(B)
]

just as it separates complete identity from projection.

A graph, grid, matrix, canvas, byte plane, or circular ruler may all be views produced by different functors.

---

# 30. Normalized vocabulary

The canonical vocabulary of the repository should be:

| Canonical term           | Meaning                                       |
| ------------------------ | --------------------------------------------- |
| Tangential Block         | autonomous bounded structured object          |
| Tangential Context Block | block equipped with a projection into a field |
| Tangential Block Field   | shared colimit or projective context          |
| Interface Object         | common structure through which blocks meet    |
| Tangency Span            | (B\leftarrow A\rightarrow C)                  |
| Tangential Gluing        | pushout (B\sqcup_A C)                         |
| Field Contribution       | morphism (B\rightarrow F)                     |
| Field Position           | image under a projection                      |
| Chart                    | bounded coordinate representation             |
| Chart Family             | indexed cover of the field                    |
| Orientation              | automorphism or selected side                 |
| Antipodal Involution     | self-inverse orientation exchange             |
| Overlap                  | pullback over the field                       |
| Compatibility            | commutation on an interface                   |
| Conflict                 | failure of required commutation               |
| Residual Object          | retained projection loss or disagreement      |
| Resolution Policy        | declared categorical construction             |
| Field Cover              | jointly epic family of contributions          |
| Observer                 | functor into a view category                  |
| View                     | observer image of a block or field            |
| Circular Action          | cyclic group action on the field              |

---

# 31. Deprecated foundational language

The following terms should not appear in the pure categorical foundation:

```text
CAR
CDR
CONS
pointer
memory plane
hardware board
bus route
chip selector
ASCII plane
Unicode plane
Lisp cell
garbage collector
register
clock motor
gear
dial
remote node
file type
compiler
```

They may appear only in documents clearly labeled:

```text
implementation profile
historical mapping
computational realization
encoding realization
```

The historical source described wide pointer domains, an intermediate plane, and an eight-selector local/remote partition. The new theory retains the abstract pattern:

[
\text{two source domains}
\rightarrow
\text{bounded mediating field}
\rightarrow
\text{indexed chart decomposition}
]

without importing the legacy machine interpretation.

---

# 32. Normalized foundational tuple

The Tangential Block Field may be summarized by:

[
\boxed{
\mathbf{TBF}
============

(
\mathcal T,
F,
D,
\lambda,
\Pi,
\mathcal R
)
}
]

where:

* (\mathcal T) is the category of Tangential Blocks;
* (F) is the shared field object;
* (D:J\rightarrow\mathcal T) is the active context diagram;
* (\lambda) is the collection of interface spans;
* (\Pi) is the cocone of field projections;
* (\mathcal R) assigns residual objects.

When:

[
F=\operatorname{colim}D
]

the field is the universal compatible composition of the active context diagram.

---

# 33. Canonical laws

## Law 1 — Autonomy

A block exists independently of its projection.

[
B\not\equiv\pi_B(B)
]

in general.

## Law 2 — Explicit context

Context is represented by morphisms, not implicit global state.

## Law 3 — Declared tangency

Blocks meet only through an explicit interface object.

## Law 4 — Universal gluing

Compatible blocks glue through a declared universal construction.

## Law 5 — Projection distinction

Field position does not imply complete identity.

## Law 6 — Compatibility by commutation

Contributions agree when their interface diagrams commute.

## Law 7 — Overlap by pullback

Common projected incidence is computed through a pullback.

## Law 8 — Residual preservation

Information loss and disagreement remain represented by an explicit residual construction.

## Law 9 — Functorial observation

Every valid view preserves identities and composition.

## Law 10 — Orientation coherence

Orientation transformations preserve categorical structure and obey their declared group laws.

---

# 34. Canonical doctrine

```text
A Tangential Block is an autonomous bounded context object.

A Tangential Context Block is a block equipped with
a morphism into a shared field.

Blocks meet through interface objects represented as spans.

Compatible blocks glue through pushouts or other explicitly
declared universal constructions.

The Tangential Block Field is the colimit of the active
diagram of blocks and interfaces.

A field contribution is an object of the slice category
over that field.

Overlap is a pullback.

Agreement is commutation over a shared interface.

Conflict is failure of required commutation.

A residual object preserves disagreement, projection loss,
or unresolved incidence.

A chart is a bounded representation of the field.

An observer is a functor from Tangential Blocks to views.

A circular realization is a cyclic group action on the field.

No computational encoding defines the categorical structure.
Computational systems are functorial realizations of it.
```

---

# 35. Final statement

The categorical identity of the project is:

[
\boxed{
\text{Tangential Block Field}
=============================

\text{a category of autonomous context blocks}
+
\text{declared interface spans}
+
\text{universal gluing}
+
\text{projection into a shared field}
+
\text{explicit residual structure}
}
]

The computational Blackboard Pattern is then obtained through a realization functor:

[
\mathcal C:
\mathbf{TBF}
\rightarrow
\mathbf{Comp}
]

where (\mathbf{Comp}) is a category of computational structures.

Under this functor:

[
\boxed{
\text{Tangential Block}
\mapsto
\text{independent computational contribution}
}
]

[
\boxed{
\text{Field colimit}
\mapsto
\text{shared blackboard}
}
]

[
\boxed{
\text{Tangency span}
\mapsto
\text{declared shared interface}
}
]

[
\boxed{
\text{Pushout}
\mapsto
\text{glued computational result}
}
]

[
\boxed{
\text{Pullback}
\mapsto
\text{overlap or common incidence}
}
]

[
\boxed{
\text{Residual object}
\mapsto
\text{conflict, ambiguity, or projection-loss record}
}
]

Therefore the normalized relation is:

[
\boxed{
\textbf{Blackboard Pattern}
===========================

\textbf{a computational realization of a Tangential Block Field}
}
]

The Tangential Block Field is the theory.

The blackboard is one functorial implementation.
