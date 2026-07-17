# SETCO From First Principles

## Foundational Charter for SETCO, OMI, Blackboard, Canvas, and OS Layers

### 0. Root Problem

Modern computation mixes many incompatible authority surfaces:

```text
source code
type systems
proof assistants
tests
runtime artifacts
operating systems
documents
diagrams
protocols
interfaces
network transports
human interpretations
```

These surfaces are useful, but they are often collapsed.

A test is treated like a proof.

A diagram is treated like an architecture.

A compiler is treated like a source of truth.

A runtime artifact is treated like the object model.

A metaphor is treated like canon.

SETCO exists to prevent that collapse.

---

# 1. First Principle

## Distinction Before Authority

Before a system can decide what is true, executable, canonical, or useful, it must first distinguish what kind of thing it is handling.

```text
classification precedes authority
```

A claim must first be classified before it is allowed to do work.

Therefore, SETCO begins with distinction.

```text
What is this?
  rule
  fact
  algorithm
  proof
  proposal
  implementation
  projection
  interpretation
  artifact
  adapter
  application surface
```

Only after classification may the system ask:

```text
What is this allowed to do?
```

This is the root of SETCO.

---

# 2. Second Principle

## Boundary Before Promotion

A thing may not be promoted until its boundary is known.

Every claim must say:

```text
what it supports
what it does not support
where it fails
how it may be promoted
what authority it does not possess
```

The boundary prevents overclaiming.

```text
A proposal is not a proof.
A proof is not an implementation.
An implementation is not a theorem.
A projection is not validation.
A metaphor is not authority.
An operating surface is not the object model.
```

---

# 3. Third Principle

## OMI Is the Object Model

The Omi Object Model is the pure object/address/relation model.

It owns:

```text
omi-notation
omi-lisp
omi-port
null rings
gauge rings
bounded envelopes
observer surfaces
Omicron
Metatron
Tetragrammatron
Omnicron
```

OMI is the computational paradigm.

OMI is not the blackboard.

OMI is not the canvas.

OMI is not the OS.

OMI is not Coq, C, Haskell, TypeScript, Python, firmware, or a browser.

Those are surfaces that may prove, implement, project, inspect, or adapt OMI.

They do not replace OMI.

Canonical lock:

```text
OMI defines the object model.
SETCO classifies how other things relate to it.
```

---

# 4. Fourth Principle

## SETCO Is the Transition Framework

SETCO is the independent transition framework that allows existing computational environments to understand, classify, stage, and loosely connect to the Omi Object Model.

SETCO owns the methodology.

OMI owns the object model.

```text
SETCO:
  classification
  categorization
  canonization
  adjudication
  promotion
  propagation
  pedagogy
  blackboard staging
  canvas visualization
  OS-like working surface

OMI:
  pure object/address model
  declarative notation
  deterministic relation frame
  bounded observer/projection logic
```

SETCO helps modern computational environments approach OMI without becoming OMI authority.

---

# 5. Fifth Principle

## Proof, Implementation, and Projection Must Remain Separate

The OMI proof rail already expresses this discipline.

`omi-axioms` is the proof authority rail for OMI. It proves bounded invariants that canon may name, OMI-Lisp may declare, OMI-ISA may witness, and receipts may record. It does not render, execute, or accept runtime state.

`omi-isa` is the executable artifact rail. Its implementation layer says code must run, tests must pass, proofs must compile, and firmware claims remain aspirational until built.

Therefore:

```text
omi-axioms:
  proves admissible OMI invariants

omi-isa:
  witnesses executable OMI behavior

SETCO:
  classifies, stages, adjudicates, and teaches how those rails relate

Omi Object Model:
  remains the base object/relation paradigm
```

---

# 6. Sixth Principle

## SETCO Does Not Create Authority

SETCO does not decide truth by itself.

SETCO classifies what is allowed to count as what.

The authority boundary remains:

```text
Proof canonizes admissible structure.
Validation determines accepted state.
Attestation witnesses accepted transition.
Projection displays accepted state.
```

This boundary already appears in the canonization/adjudication pattern.

SETCO makes that boundary reusable.

It is not a replacement authority layer.

It is a framework for preventing authority confusion.

---

# 7. Core Layer Model

## SETCO and OMI Relationship

```text
External Computational Environments
  Coq
  Haskell
  TypeScript
  C
  Python
  firmware
  browsers
  operating systems
  applications
  documents
  diagrams
        ↓
SETCO
  classification
  categorization
  canonization
  adjudication
  hypercube graph methodology
  blackboard canvas
  transition framework
        ↓
Omi Object Model
  omi-notation
  omi-lisp
  omi-port
  null/gauge rings
  bounded relation frames
  observer surfaces
        ↓
OMI Artifact Rails
  omi-axioms
  omi-isa
  receipts
  projections
```

SETCO is above the Omi Object Model as a transition and classification framework.

OMI remains the object model being classified, promoted, propagated, implemented, and explained.

---

# 8. Repository Boundary

## Recommended Repository Set

```text
setco
  root framework, charter, methodology, public explanation

setco-blackboard
  classification, categorization, claim registry, adjudication workspace

setco-canvas
  hypercube graph, tetrahedral frames, pedagogical projection surfaces

setco-os
  IDE-like operating surface and external tool adapter shell

omi-canon
  OMI canonical doctrine and language

omi-axioms
  OMI proof authority rail

omi-isa
  OMI implementation/runtime witness rail

omi-tetragrammatron
  OMI construction geometry / projection topology

omi-canvas
  OMI typed construction engine, if retained separately
```

Short names are preferred:

```text
setco-blackboard
setco-canvas
setco-os
```

rather than:

```text
setco-omnicron-blackboard
setco-omnicron-canvas
setco-omnicron-os
```

Reason:

```text
SETCO is the framework.
Omnicron is a resolver-facing role inside the OMI/SETCO bridge.
```

Putting `omnicron` into every repo name makes Omnicron appear to own SETCO.

It should not.

---

# 9. SETCO Root Repo

## `setco`

The `setco` repository defines the independent transition framework.

It owns:

```text
foundational charter
from-first-principles method
classification grammar
canonization/adjudication model
public explanation
relationship to OMI
relationship to modern computational environments
cross-repo map
```

It answers:

```text
What is SETCO?
Why does it exist?
How does it relate to OMI?
How does it prevent category collapse?
How does it help existing tools approach a new computational paradigm?
```

Suggested folders:

```text
setco/
  README.md
  CHARTER.md
  PRINCIPLES.md
  METHOD.md
  REPO-MAP.md
  GLOSSARY.md
  docs/
    setco-and-omi.md
    transition-framework.md
    authority-boundary.md
    computational-environments.md
```

---

# 10. SETCO Blackboard

## `setco-blackboard`

The blackboard is the classification and categorization workspace.

It owns:

```text
claim registry
P0–P4 status ladder
rules / facts / algorithms / proofs / proposals
allowed use
forbidden use
failure boundary
promotion path
external artifact intake
language/tool adapter classification
```

It answers:

```text
What kind of object is this?
What status does it have?
What may it support?
What must it not be used for?
How can it be promoted?
```

The blackboard is not an application runtime.

It is a staging surface.

Suggested folders:

```text
setco-blackboard/
  README.md
  CLAIM-REGISTRY.md
  CANONIZATION.md
  ADJUDICATION.md
  INTAKE.md
  PROMOTION.md
  FAILURE-BOUNDARIES.md
  schemas/
    claim.schema.json
    artifact.schema.json
    promotion.schema.json
  examples/
    omi-null-ring.claim.yaml
    omi-isa-runtime.claim.yaml
    omi-axioms-proof.claim.yaml
```

Canonical sentence:

```text
SETCO Blackboard classifies claims before they are allowed to influence OMI construction.
```

---

# 11. SETCO Canvas

## `setco-canvas`

The canvas is the visual and graph-theoretic pedagogy surface.

It owns:

```text
hypercube graph methodology
vertices
edges
faces
cells
tetrahedral Omi-* development frames
KK / KU / UK / UU research modality
claim-state diagrams
pedagogical projection maps
```

It answers:

```text
Where does a claim sit?
What is connected to it?
Which edge promotes it?
Which face classifies it?
Which cell integrates it?
```

Suggested folders:

```text
setco-canvas/
  README.md
  HYPERCUBE-GRAPH.md
  TETRAHEDRAL-FRAMES.md
  PYRAMID-METHOD.md
  CUBE-PEDAGOGY.md
  CANVAS-SCHEMA.md
  schemas/
    vertex.schema.json
    edge.schema.json
    face.schema.json
    cell.schema.json
  examples/
    null-ring.canvas.json
    omi-proof-promotion.canvas.json
```

Canonical sentence:

```text
SETCO Canvas makes classification visible as a hypercube graph.
```

---

# 12. SETCO OS

## `setco-os`

The OS is the operating surface or IDE-like shell.

It owns:

```text
workspace orchestration
external tool integration
repo navigation
language adapters
compiler/assembler front ends
Omnicron-facing resolver surface
developer experience
```

It answers:

```text
How does a human or agent use SETCO?
How are Coq, Haskell, TypeScript, C, Python, and other tools connected?
How are OMI declarations inspected, staged, assembled, compiled, or projected?
```

`setco-os` is not an operating system in the kernel-authority sense.

It is an operating surface.

Suggested folders:

```text
setco-os/
  README.md
  WORKSPACE.md
  ADAPTERS.md
  OMNICRON-SURFACE.md
  TOOLCHAIN.md
  IDE-SHELL.md
  adapters/
    coq/
    haskell/
    typescript/
    c/
    python/
  examples/
    inspect-omi-axioms.md
    classify-omi-isa.md
    project-omi-face.md
```

Canonical sentence:

```text
SETCO OS is the IDE-like operating surface for working with SETCO and OMI without becoming OMI authority.
```

---

# 13. Hypercube Graph Methodology

SETCO uses a hypercube graph because classification has multiple independent axes.

A simple cube has:

```text
8 vertices
12 edges
6 faces
```

In SETCO:

```text
vertices:
  classified claims or artifacts

edges:
  typed transitions, dependencies, promotions, projections, lowerings

faces:
  classification planes

cells:
  integrated construction regions

hypercube:
  expandable methodology for adding independent axes
```

Core axes:

```text
Epistemic axis:
  KK / KU / UK / UU

Construction axis:
  rule / fact / algorithm / proof / proposal

Adjudication axis:
  P0 / P1 / P2 / P3 / P4

Implementation axis:
  proved / implemented / defined_model / interpretation

Projection axis:
  impotent / innocuous / implementation-promoted

Interface axis:
  omi-notation / omi-lisp / omi-port / Omi-* configuration

Dimensional axis:
  point / line / plane / space / hyperspace
```

The hypercube does not prove the claim.

It classifies the claim.

---

# 14. OMI Object Model Boundary

The Omi Object Model remains pure.

It owns the base declarative methodology:

```text
omi-notation
  direct canonical notation surface

omi-lisp
  local declaration surface

omi-port
  external/adaptive declaration surface
```

Omnicron interfaces with these surfaces.

When no prior address is available, Omnicron may return:

```text
(NULL . NULL)
```

or the null gauge projection:

```text
F0 00 1C 1D 1E 1F 20 F0
```

When a declared interpretive gauge exists, Omnicron may expose:

```text
FΔ 00 1C 1D 1E 1F 20 FΔ
```

SETCO may classify these surfaces.

SETCO does not replace them.

---

# 15. OMI Axioms Boundary

`omi-axioms` should remain attached to OMI as the proof authority rail.

It owns:

```text
Coq theorem modules
proof registry
proof book
proof strictness
coqchk boundary
formal theorem atlas
```

The proof-spine document states that only modules listed in `_CoqProject`, compiled by `make proof-strict`, and accepted by `coqchk` are part of the proof authority rail.

SETCO may reuse its proof-status method.

SETCO may stage its proof claims.

SETCO may expose its proof claims in a canvas.

But SETCO does not become the proof authority.

Canonical sentence:

```text
omi-axioms proves OMI invariants; SETCO classifies how those invariants may be used.
```

---

# 16. OMI ISA Boundary

`omi-isa` should remain attached to OMI as the executable artifact rail.

It owns:

```text
C runtime
ISA
VM
parser
compiler
bytecode
envelope transport
dispatch
observers
tests
WASM
firmware
receipts
```

The architecture document defines the pipeline from OMI-Lisp through compiler, ISA, VM, observers, envelope, dispatch, transport, mesh, and receipts.

SETCO may classify these artifacts.

SETCO may expose them through `setco-os`.

SETCO may stage them in `setco-blackboard`.

But SETCO does not make the runtime true.

The artifact either builds or it does not.

The test either passes or it does not.

Canonical sentence:

```text
omi-isa witnesses executable OMI behavior; SETCO classifies and stages that behavior for inspection, promotion, or integration.
```

---

# 17. OMI OS Reclassification

If `omi-os` exists, it should not be OMI core.

It should be reclassified as:

```text
SETCO / Omnicron-facing operating surface
```

or folded into:

```text
setco-os
```

Reason:

An OS implies:

```text
workspace
tool orchestration
application surfaces
external devices
human interaction
policy
runtime environment
```

Those are downstream of the pure Omi Object Model.

Therefore:

```text
omi-os as root authority:
  reject

setco-os as operating surface:
  accept
```

Canonical sentence:

```text
The operating layer belongs to SETCO as an interface and workspace surface, not to OMI as object-model authority.
```

---

# 18. Promotion and Propagation

SETCO exists to manage promotion and propagation.

Promotion means:

```text
P4 metaphor
  → P2 model
  → P1 finite check
  → P0 proof
```

or:

```text
proposal
  → defined model
  → implementation precedent
  → tested artifact
  → proof target
  → proved invariant
```

Propagation means:

```text
proved invariant
  → canon name
  → declaration surface
  → implementation witness
  → receipt
  → projection
```

SETCO tracks the movement.

OMI supplies the object model.

The artifact rails supply proof and execution.

---

# 19. Relationship to Modern Computational Environments

SETCO makes OMI understandable to today’s environments by giving each environment a role.

```text
Coq:
  proof surface

Haskell:
  type/model surface

TypeScript:
  browser/interface surface

C:
  runtime/ISA/firmware surface

Python:
  tooling/prototyping surface

Markdown:
  documentation/projection surface

JSON/YAML:
  registry and exchange surface

Canvas:
  visual graph surface

Operating systems:
  workspace and process surfaces
```

None of these are OMI itself.

They are adapters.

SETCO classifies them so they can loosely connect to the Omi Object Model without becoming the model.

---

# 20. Final Canon

```text
SETCO is the independent transition framework.

The Omi Object Model is the pure computational paradigm.

SETCO classifies.
OMI defines.

SETCO stages.
OMI relates.

SETCO adjudicates.
OMI declares.

SETCO teaches.
OMI computes.

SETCO Blackboard classifies claims.
SETCO Canvas makes classification visible.
SETCO OS provides an operating surface.

omi-axioms proves OMI invariants.
omi-isa witnesses OMI behavior.
omi-canon names OMI doctrine.

Omnicron resolves OMI-facing surfaces.
Tetragrammatron validates bounded closure.
Metatron transposes without changing decision.
Omicron closes the null-byte ring.

Projection displays.
Attestation witnesses.
Validation determines.
Proof canonizes admissible structure.

No layer may impersonate another.
```

## One-Sentence Lock

SETCO is the independent hypercube-graph transition framework that classifies, stages, adjudicates, and teaches how modern computational environments may loosely connect to the Omi Object Model without becoming its authority.
