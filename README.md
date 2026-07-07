# omi-canon

> The doctrinal, historical, geometric, and projection-facing documentation spine
> for the OMI ecosystem.

```text
   ___    __  __    _
  / _ \  |  \/  |  | |
 | (_) | | |\/| |  | |
  \___/  |_|  |_|  |_|
  omi --- imo
```

**omi-canon** is the canonical documentation repository for the Omicron Object
Model. It is not a runtime, a compiler, or an application. It is the written
canon.

---

## Layered Structure

```text
00-origin/        why this began — the observer in the void, the Word as notation
01-ontology/      what exists — this canon's self-description
02-doctrine/      what must be preserved — invariant structural laws
03-manifesto/     why it matters — the philosophical lens
04-foundations/   irreducible boundaries — palindrome, omicron anchors, Omi-Ring
05-projections/   observer surfaces — DOM, portals, meta-circular compiler
06-protocol/      envelopes, notation, receipt rules — the wire format
07-geometry/      Fano, tetrahedron, quotient spaces, Delta Law, quadratic form
08-isa/           machine-facing model — opcodes, dispatch, gauge table
09-ecosystem/     open world, hardware, networking — eBPF, IPv6, agents
10-glossary/      canonical terms
```

## Root Gates

| File | Purpose |
|------|---------|
| `ONTOLOGY.md` | what exists in the canon |
| `DOCTRINE.md` | what must be preserved |
| `MANIFESTO.md` | why it matters |
| `POSTULATES.md` | what may be constructed (Euclidean postulates) |
| `AXIOMS.md` | how objects may be folded and transformed (origami axioms) |
| `DECLARATIONS.md` | how RULES.omi clauses become FACTS.omi rows |
| `PROJECTIONS.md` | how the canon becomes visible |
| `GLOSSARY.md` | canonical terms |
| `README.md` | this file — entry point to the canon |

## Truth Gates

```text
truth-gates/    .omi  — forward declarations (RULES, FACTS, CLOSURES, COMBINATORS, CONS)
mirrors/        .imo  — backward reflections of the truth gates
```

## The Tetrahedron Core

```text
    ONTOLOGY
    /   \
DOCTRINE—MANIFESTO
    \   /
  PROJECTIONS
```

Stellated by: 06-protocol, 07-geometry, 08-isa, 09-ecosystem, 10-glossary,
00-origin.

## One-Line Canon

```text
omi-canon is the doctrinal, historical, geometric, and projection-facing documentation spine for the OMI ecosystem.
```

## Relationship to Other Repositories

| Repository | Role |
|------------|------|
| **omi-canon** (this repo) | Canonical documentation spine |
| **omi-portal** | Reference implementation — browser, compiler, runtime |
| **omi-isa** | ISA implementation + Coq proofs |

See `09-ecosystem/AGENTS.md` for the full boundary specification.

## Minimal Canonical Statement

```text
A frame is valid iff Q_frame(S) = 0.
A valid frame yields one truth row: (LL, NN, MM).
A truth row is accepted iff MM resolves from NN under the LL-modulated
Delta Law within the bounded Fano window.
An accepted row advances the 5040-slot replay cursor and writes a receipt.
Only after validation, resolution, and receipt may the object be projected.
Projection is never authority.
```

## Reading Paths

| Reader Type | Start With |
|-------------|------------|
| Newcomer | `00-origin/TIMELINE.md` → `03-manifesto/MANIFESTO.md` |
| Philosopher | `03-manifesto/` → `02-doctrine/` → `01-ontology/` |
| Mathematician | `07-geometry/` → `04-foundations/` → `06-protocol/` |
| Resolutionist | `00-origin/RESOLUTION_LINEAGE.md` → `04-foundations/` → `07-geometry/` |
| Engineer | `08-isa/` → `06-protocol/` → `09-ecosystem/` |
| Implementer | `05-projections/` → `06-protocol/` → `08-isa/` |
| Student | `10-glossary/GLOSSARY.md` → `00-origin/TIMELINE.md` |
