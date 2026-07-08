# State 13 — Master Architecture: The Map

Status: Definitive canon doctrine
Layer: Architecture overview / repository map / system boundary

## Purpose

Master Architecture is the map of the OMI canon, not its authority. It describes how the construction spine (00–12), the master map (13), and the constitutional/conceptual spine (14–24) relate. It does not define new doctrine.

## Architecture Statement

OMI is a declarative construction system.

Canonical grammar defines names.
Relational quotation frames candidate relations.
OMI-Lisp declares candidate relations.
The Haskell canvas core resolves typed construction stages.
The C ISA/firmware lowers envelopes onto carriers.
The Coq axioms prove the formal spine.
Hardware, network, memory, Markdown, Canvas, and Lisp are carrier faces, not authorities.

Validation determines.
Omi-Attestation witnesses.
Accepted Omi-State may be recorded.
Projection only displays accepted relation state.

## Corrected Authority Hierarchy

The fundamental pair is OMI↔IMO (citation↔carrier). Around this pair, three named methods provide the operational protocol:

| Method | Role | Register | Description |
|--------|------|----------|-------------|
| **Omnicron** | Horizon resolver | `0x0000`/`0xFFFF` | Portable headless runtime resolver — holds the null/full horizon where resolution occurs |
| **Tetragrammatron** | Validation governor | `0x3C`↔`0x78` | Fold/carry validation method — owns DeltaC/BQF/Polybius/slot5040 logic |
| **Metatron** | Alternating scribe | `0xAA55` | Alternating projection witness — scribe of apparent difference through the Omi-Ring |

These are not independent authorities. The irreducible relation is OMI↔IMO. Tetragrammatron and Metatron are methods/gates applied to that relation. Omnicron is the runtime resolver that hosts the horizon within which the relation operates.

### Symbolic Register Assignments

```
0x0000 / 0xFFFF = Omnicron      — null/full horizon resolver
0xAA55           = Metatron      — alternating witness / boot signature
0x3C (60)        = Tetragrammatron — sexagesimal gate / folded Metatron shadow
0x78 (120)       = Tetragrammatron carried — 0x3C << 1 / shifted carry fold
```

### Omnicron Resolver Envelope

```
FF 00 1C 1D 1E 1F 20 FF
```

This 8-byte pre-header is the canonical carrier horizon. It is not a frame — it is the envelope within which the Omi-Ring relation `omi---imo` is carried. `FF` at both ends seals the tautological boundary.

### Naming Law

`omi-*` prefixes are used for protocol modules, tools, carriers, surfaces, and workbooks (e.g., `omi-vault`, `omi-mcrsgsp`, `omi-canon`, `omi-isa`). `omnicron` (not `omi-omicron`) is the canonical portable headless runtime resolver.

## Repository Relationship

| Repository | Role |
|------------|------|
| **omi-canon** (this repo) | Canonical documentation spine — state transition record |
| **omi-portal** | Reference implementation — browser, compiler, runtime |
| **omi-isa** | ISA implementation + Coq proofs |
| **omi-axioms** | Coq proof stack |
| **omi-canvas** | Pure Haskell kernel — executable specification of the protocol |

## Spine Summary

```
00-12 = Construction spine
13    = Master Architecture (this document)
14-24 = Constitutional and conceptual closure
```

## Canonical Construction Spine (00–12)

The construction spine establishes what must exist for computation to be declared, resolved, and carried:

```
00 — COSMOLOGY               What universe does computation inhabit?
01 — ONTOLOGY                What may exist in that universe?
02 — DOCTRINE                How is truth recognized?
03 — FOUNDATIONS             What cannot be reduced further?
04 — ATOMIC KERNEL           What is the smallest deterministic object?
05 — PURE ALGORITHMS         How do objects move lawfully?
06 — FORMAL PROOFS           What has been verified?
07 — ISA                     How does the law become executable?
08 — PROTOCOL SEMANTICS      How do observers communicate?
09 — OMI-LISP                How are relations declared?
10 — BLACKBOARD              How are declarations resolved?
11 — NOTATION MULTIPLEXING   How are notation streams carried through earned bands?
12 — VERSION CONTROL         How does the canon version itself?
```

## Constitutional and Conceptual Spine (14–24)

The constitutional spine closes the circle with verification, classification, grammar, quotation, projection, carriers, and reference:

```
14 — CANONICAL CONSTITUTION   The verification grid — what the project claims
15 — CLASSIFICATION / TERMINOLOGY  Term roles and document categories
16 — SYMBOLIC GRAMMAR         The Omi-* protocol grammar boundary
17 — RELATIONAL QUOTATION     Cardinality, ordinality, qualification, carry-forward
18 — GAUGE INTERRUPTS         Which orientation is selected?
19 — PROJECTION FACES         How is the surface read?
20 — TRANSFORM CARRIERS       How does nondeterminism enter through port contracts?
21 — SURFACE CLAUSES          What world is rendered from the Delta Law?
22 — PROPAGATION MODEL        How do analog signals, observers, and carriers propagate?
23 — REFERENCE GLOSSARY       What do the terms mean?
24 — OBSERVER CHANGELOG       Observer-facing migration history
```

## Canon as Bounded Packing

The 24-file canon spine forms the bounded n-sphere of OMI construction. Each document is a canonical boundary cell. Derived declarations may circumscribe the canon, but they do not enlarge authority. They must resolve against the tetrahedral Omi-Ring basis and be adjudicated by the Tetragrammatron through deterministic reduction surfaces such as truth gates, decision tables, and Karnaugh maps.
