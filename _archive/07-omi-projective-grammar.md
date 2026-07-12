<!-- Extracted from dev-docs/chat about model.md -- conversation turn 2026-07-09 19:01 -->

# Omi Projective Grammar: Block-Design Spec Convention

## 1. Purpose

The Omi Object Model specification should be written as a projective grammar over bounded semantic blocks.

The goal is to make every spec unit:

```text id="0egk3y"
small enough to inspect
structured enough to compose
stable enough to cite
bounded enough to compile
clear enough for a coding agent to navigate
```

The model borrows from block designs and the Fano plane: small finite sets of terms are arranged so that each relation has a constrained place, and each larger construct is built from complete sets of smaller objects.

This is not just documentation style. It is an OMI-compatible way of writing specifications.

---

## 2. Core Spec Units

OMI spec units have five levels.

```text id="jfwjux"
rules
facts
closures
combinators
constructs
```

Each level has a fixed writing constraint.

| Unit | Form | Function |
|---|---|---|
| Rule | one sentence | Declares a bounded operation or law |
| Fact | one clause | States a stable condition or observation |
| Closure | one term | Names a completed invariant boundary |
| Combinator | one set of terms | Groups compatible terms into a reusable composition |
| Construct | one page model | Explains how a complete set of terms relates or interoperates |

---

## 3. Rules

A **rule** is one sentence.

It declares an operation, law, or boundary.

A rule should be short enough to cite directly and strong enough to constrain implementation.

Example:

```text id="e3v43o"
Address is identity.
```

Example:

```text id="75krk6"
A Projection Diagram may inform discovery but must not command application behavior.
```

Example:

```text id="lfuwz3"
Any two coordinates in a Latin resolver triple determine the third inside the bounded frame.
```

Rule shape:

```yaml id="e9v0ft"
rule:
 id: omi.rule.address_identity
 sentence: "Address is identity."
 cardinality: one_sentence
 modality: canonical
```

A rule should not explain itself inside the sentence. Explanation belongs to facts and constructs.

---

## 4. Facts

A **fact** is one clause.

It states a stable condition, observation, or finite result.

Facts support rules without expanding into full argument.

Example:

```text id="pqm9pt"
512 bits equals 64 bytes.
```

Example:

```text id="fr96yu"
The Polybius full nibble wheel sums to 0x78.
```

Example:

```text id="8ezvmt"
The Omicron NULL Byte Ring closes to zero under XOR.
```

Fact shape:

```yaml id="kgkqtm"
fact:
 id: omi.fact.runtime_packet_width
 clause: "512 bits equals 64 bytes"
 supports:
 - omi.rule.runtime_packet_is_fixed_width
 status: proved_or_defined
```

Facts should be tagged by status:

```text id="le8ci0"
proved
implemented
defined_model
interpretation
```

Your proof book already uses this style of status distinction: **Proved**, **Implemented**, **Defined model**, and **Interpretation**. filecite turn39file0

---

## 5. Closures

A **closure** is one term.

It names a completed invariant boundary.

Closures are not explanations. They are compact names for finished reduction points.

Examples:

```text id="5ku9mv"
Null-Ring-Closure
Polybius-Diagonal-Closure
Projection-Only-Boundary
Address-Identity-Closure
Omicron-Envelope-Closure
```

Closure shape:

```yaml id="h16byv"
closure:
 id: omi.closure.null_ring
 term: Null-Ring-Closure
 invariant: "complete XOR witness reduces to zero"
 status: proved
```

A closure is the term your coding agent can search for when it needs the completed boundary.

---

## 6. Combinators

A **combinator** is one set of terms.

It groups closures, rules, or facts into a reusable composition.

A combinator says:

```text id="9y3bd0"
these terms are allowed to work together
```

Example:

```yaml id="d1oxcb"
combinator:
 id: omi.combinator.runtime_frame
 terms:
 - Omicron-Envelope-Closure
 - Null-Ring-Closure
 - Polybius-Diagonal-Closure
 - Projection-Only-Boundary
 role: "construct bounded runtime frame"
```

Example:

```yaml id="9se5co"
combinator:
 id: omi.combinator.latin_discovery
 terms:
 - Attestation
 - Attribution
 - Discovered-Point
 law: "any two determine the third"
 role: "recover missing citation coordinate"
```

Combinators are where the block-design logic becomes useful.

A block design arranges elements into constrained subsets. In OMI, a combinator is a constrained subset of terms that may compose.

---

## 7. Constructs

A **construct** is one page model.

It explains how a complete set of terms relates or interoperates.

A construct should include:

```text id="v63s0d"
summary
purpose
required terms
rules
facts
closures
combinators
cardinality
chirality
ordinality
modality
boundaries
non-claims
```

Construct shape:

```yaml id="b2s2yo"
construct:
 id: omi.construct.projection_diagram
 title: Omi-Projection Diagram
 summary: >
 A Projection Diagram is an OMI-Lisp declared finite-state
 relation view that may render on Omi-Canvas but does not
 command application behavior.
 required_terms:
 - Address
 - State
 - Transition
 - Projection
 - Closure
 rules:
 - omi.rule.projection_does_not_command_application
 facts:
 - omi.fact.polybius_wheel_sum_78
 closures:
 - Projection-Only-Boundary
 combinators:
 - omi.combinator.latin_discovery
 axes:
 cardinality: "finite declared state set"
 chirality: "forward/inverse traversal"
 ordinality: "declared transition order"
 modality: "impotent or innocuous projection"
```

Constructs are the spec pages.

They are where the project becomes readable.

---

## 8. Projective Grammar

The OMI spec should use a projective grammar.

That means every term can be read as part of a finite relation structure.

The naming convention is:

```text id="83orxq"
Omi-<Predicate_or_Modality> <Object_or_Type>
```

Example:

```text id="28k20u"
Omi-Projection Diagram
```

Parsed as:

```text id="a3sl73"
Subject:
 Omi canonical declaration space

Predicate:
 Projection

Object:
 Diagram
```

This forms a semantic triplet:

```text id="ju9gap"
(Omi, Projection, Diagram)
```

The name is a checkpoint.

It tells the reader:

```text id="gglb79"
what field the term belongs to
what relation or modality constrains it
what kind of object is being named
```

This is why the `Omi-` prefix is not decorative. It declares the subject field.

---

## 9. Fano / Block-Design Reading

The Fano-plane idea gives a model for bounded incidence.

Each spec construct can be treated as a small incidence block.

For example, a construct may require seven canonical roles:

```text id="wdjqgb"
rule
fact
closure
combinator
construct
projection
boundary
```

Or a resolver triple:

```text id="0p0ikm"
attestation
attribution
discovered-point
```

The block-design rule is:

```text id="nk05qq"
terms should not float freely;
terms should appear inside bounded relation blocks.
```

That makes the spec navigable.

A coding agent can ask:

```text id="x1cbk6"
What block does this term belong to?
What other terms must appear with it?
What closure completes it?
What modality limits it?
```

---

## 10. Four Required Axes

Every categorical group delineation should identify four axes.

```text id="37xd7y"
cardinality
chirality
ordinality
modality
```

### Cardinality

Question:

```text id="3pvkoz"
How many positions, states, fields, terms, or witnesses?
```

Examples:

```text id="ntqw8m"
4 byte-ring points
16 nibble values
32 axes in a 64-bit word
240-state bridge
5040 carry-forward coordinates
512-bit initialization packet
```

### Chirality

Question:

```text id="zxrav4"
What is the orientation, inverse, handedness, or traversal direction?
```

Examples:

```text id="hl5qq6"
OMI / IMO
D+ / D-
forward / inverse
left / right
snub / reflected
```

### Ordinality

Question:

```text id="b0tr83"
What is the sequence, order, phase, or carry-forward path?
```

Examples:

```text id="sd735x"
declaration before definition
definition before discovery
delta period-8 sequence
7! carry-forward ring
null → space → DEL → full → null
```

### Modality

Question:

```text id="yxkfh0"
What mode of force, interpretation, or use does the object carry?
```

Examples:

```text id="jq1n2l"
executable
runtime-operator
declarative
definitional
interpretive
interpolative
impotent
innocuous
projection-only
```

These axes should appear in every construct page.

---

## 11. Proposed Folder / Page Convention

The spec can be organized as:

```text id="oreodo"
00-front-matter/
01-rules/
02-facts/
03-closures/
04-combinators/
05-constructs/
06-projection-diagrams/
07-runtime/
08-implementation/
09-proof-status/
```

Each page should contain only one primary object.

Examples:

```text id="vl564a"
01-rules/address-is-identity.md
02-facts/runtime-packet-is-512-bits.md
03-closures/null-ring-closure.md
04-combinators/runtime-frame-combinator.md
05-constructs/omi-projection-diagram.md
06-projection-diagrams/polybius-gauge.diagram.md
```

---

## 12. YAML Shape for a Spec Unit

```yaml id="im62q3"
omi_spec_unit:
 id: omi.construct.example
 kind: construct
 name: Omi-Example Construct

 grammar:
 subject: Omi
 predicate: Example
 object: Construct

 form_constraint:
 rules: one_sentence
 facts: one_clause
 closures: one_term
 combinators: one_set_of_terms
 constructs: one_page_model

 axes:
 cardinality: null
 chirality: null
 ordinality: null
 modality: null

 content:
 summary: null
 rules: []
 facts: []
 closures: []
 combinators: []
 related_constructs: []

 boundary:
 includes: []
 excludes: []
 application_authority: false

 status:
 claim_status: defined_model
 proof_status: unclassified
 implementation_status: unclassified
```

---

## 13. Example: Omi-Projection Diagram

```yaml id="xctakl"
omi_spec_unit:
 id: omi.construct.projection_diagram
 kind: construct
 name: Omi-Projection Diagram

 grammar:
 subject: Omi
 predicate: Projection
 object: Diagram

 summary: >
 An Omi-Projection Diagram is an OMI-Lisp declaration of a
 bounded finite-state relation view. It may render on Omi-Canvas,
 but it does not decide application behavior.

 rules:
 - id: omi.rule.projection_only
 sentence: "A Projection Diagram may expose a bounded relation but must not command application behavior."

 facts:
 - id: omi.fact.diagram_is_finite
 clause: "A Projection Diagram has a finite declared state set"

 closures:
 - Projection-Only-Boundary

 combinators:
 - id: omi.combinator.diagram_runtime
 terms:
 - Declaration
 - Definition
 - Discovery
 - Projection

 axes:
 cardinality: "finite declared states and transitions"
 chirality: "forward/inverse traversal may be represented"
 ordinality: "transition order is declared"
 modality: "impotent or innocuous projection"

 boundary:
 includes:
 - finite states
 - transitions
 - witnesses
 - projection strength
 excludes:
 - application command
 - external side effect
 - user acceptance
 application_authority: false

 status:
 claim_status: defined_model
```

---

## 14. Example: Omi-Latin Resolver

```yaml id="zrhu0v"
omi_spec_unit:
 id: omi.construct.latin_resolver
 kind: construct
 name: Omi-Latin Resolver

 grammar:
 subject: Omi
 predicate: Latin
 object: Resolver

 summary: >
 An Omi-Latin Resolver uses Latin-square/quasigroup structure
 as a finite reversible discovery table for citation coordinates.

 rules:
 - id: omi.rule.any_two_determine_third
 sentence: "Any two coordinates in a Latin resolver triple determine the third inside the bounded frame."

 facts:
 - id: omi.fact.latin_quasigroup_equivalence
 clause: "Finite quasigroups and Latin squares are equivalent table structures"

 closures:
 - Resolver-Uniqueness-Closure

 combinators:
 - id: omi.combinator.attestation_attribution_discovery
 terms:
 - Attestation
 - Attribution
 - Discovered-Point

 axes:
 cardinality: "order n table with n symbols"
 chirality: "left and right recovery operations"
 ordinality: "row-column-symbol relation order"
 modality: "discovery resolver"

 boundary:
 includes:
 - reversible coordinate recovery
 - bounded table consistency
 excludes:
 - global associativity
 - application networking
 - transport behavior
 application_authority: false

 status:
 claim_status: defined_model
```

---

## 15. Canon Statement

The OMI specification should be written as a projective grammar of bounded block-design units.

Rules are one sentence.

Facts are one clause.

Closures are one term.

Combinators are one set of terms.

Constructs are one page models explaining how complete sets of terms relate or interoperate.

Every construct should identify its cardinality, chirality, ordinality, and modality.

The `Omi-` naming convention forms subject-predicate-object semantic checkpoints, allowing the spec to function as a navigable mental graph and a machine-oriented declaration surface.

This makes the OMI spec readable, bounded, composable, and suitable for meta-compilation into Omi-Canvas / Obsidian Markdown exports.