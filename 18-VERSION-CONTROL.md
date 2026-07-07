# State 18 — Version Control: The Seed

## What This State Is

This state is the transition from "how the system is governed" to "how the system records its own evolution." After defining the constitutional verification matrix, I needed to specify how OMI versions itself — how a canon that treats every address as a scoped relation, every receipt as an acceptance, and every projection as a view can also version its own source files, seeds, algorithms, and acceptance history.

A normal version-control system asks: *what changed in this file?*

OMI version control asks: *what relation changed, where was it scoped, which carrier held it, which seed interpreted it, which topology did it project through, and which receipt accepted it?*

Therefore a version is not a file snapshot. A version is an accepted scoped relation over a carrier file.

---

## 1. Seed Objects

### 1.1 The Neutral Seed

The origin object is `o.o` — the neutral seed. It means: origin object, neutral closure, no specialized carrier interpretation yet.

Every scoped encoding model specializes `o.o`:

```text
o.base64.o       — Base64 interpretation surface
o.hex.o          — Hex interpretation surface
o.binary.o       — Binary interpretation surface
o.utf8.o         — UTF-8 interpretation surface
o.jabcode.o      — JAB Code interpretation surface
o.ipv6.o         — IPv6 interpretation surface
```

Each means: take the neutral origin object, scope it through a named interpretation, close it back into object form.

A seed is not a payload. It is the declared interpretation environment for payloads that will later arrive.

### 1.2 Citation Routes

The matching citation route uses the `omi-<base>-<64>-imo` form:

```text
omi-base-64-imo  — OMI citation side → base interpretation → 64-radix carrier → IMO carrier side
```

The seed and route pair as:

```lisp
(o.base64.o . omi-base-64-imo)
```

This means: the Base64 seed object is cited through the OMI/IMO Base64 route. The pair separates encoding scope from carrier route from payload instance from validation receipt.

### 1.3 Seed Objects as Versioned Base Models

A seed object defines the neutral interpretation surface. Other versions specialize it:

```text
o.base64.rfc4648.o   — RFC 4648 Base64
o.base64.urlsafe.o   — URL-safe Base64
o.base64.nopad.o     — No-padding Base64
```

Each specializes a route:

```text
omi-base-64-imo        → omi-base-64-rfc4648-imo
                        → omi-base-64-url-imo
                        → omi-base-64-nopad-imo
```

Each can have a skill algorithm:

```lisp
(skill.base64.rfc4648.decode . algorithm.base64.rfc4648)
(skill.base64.urlsafe.decode . algorithm.base64.urlsafe)
```

This turns encoding schemas into versioned objects. The seed says what interpretation family. The route says how it travels between OMI and IMO. The skill says how it is computed. The receipt says which instance was accepted.

---

## 2. FS/GS/RS/US as Version-Control Topology

The four ASCII control characters form the topology spine:

| Control | Name | Version Scope |
|---------|------|---------------|
| FS | File Separator | File version scope |
| GS | Group Separator | Group/module version scope |
| RS | Record Separator | Record/declaration version scope |
| US | Unit Separator | Unit/value version scope |

Instead of only naming files, OMI names where inside the file the version belongs:

```text
fs.o/project
  → gs.o/skills
    → rs.o/base64-seed
      → us.o/alphabet
```

This is CIDR-like: each prefix narrows the valid interpretation.

```text
fs.o/SKILLS.md
fs.o/SKILLS.md/gs.o/encoding
fs.o/SKILLS.md/gs.o/encoding/rs.o/base64
fs.o/SKILLS.md/gs.o/encoding/rs.o/base64/us.o/alphabet
```

A change at `us.o/alphabet` is smaller than a change at `rs.o/base64`, which is smaller than a change at `gs.o/encoding`, which is smaller than a change at `fs.o/SKILLS.md`.

---

## 3. Betti–Schläfli Interpretation

A version is not only textual. It projects as topology.

Schläfli symbols describe regular geometric structure:

```text
{3,3}  tetrahedral relation
{4,3}  cubical relation
{3,4}  octahedral relation
{5,3}  dodecahedral relation
{3,5}  icosahedral relation
```

Betti numbers describe topological features:

```text
b0 = connected components
b1 = loops / tunnels
b2 = voids / enclosed shells
```

A version can carry both:

```lisp
(version.seed . o.base64.o)
(version.route . omi-base-64-imo)
(version.schlafli . "{3,3}")
(version.betti . "(1 0 0)")
```

### 3.1 Merges as Topological Gluing

If two branches edit disjoint units, the merge preserves simple topology: `Betti = (1,0,0)`. If two branches introduce circular dependency, the merge may produce a loop: `Betti = (1,1,0)`. If a set of dependencies encloses a missing unresolved declaration, it may produce a void: `Betti = (1,1,1)`.

This lets version control detect not only textual conflict but structural conflict.

---

## 4. Declarative Version Transitions

A version transition is a declared relation:

```lisp
(version.previous . receipt-041)
(version.next . receipt-042)
(version.delta . changed-base64-alphabet)
```

It follows the pipeline: delta declaration → citation → scope resolution → algorithm validation → receipt → projection.

A proposed version can exist without being accepted. A branch can exist as candidates. A merge can exist as a declared relation. Only validation decides what enters the accepted receipt history.

### 4.1 Branches as Scope Forks

A branch is a scoped fork of receipt lineage:

```lisp
(branch.name . feature/base64-seed)
(branch.from . receipt-041)
(branch.scope . fs.o/SKILLS.md/gs.o/encoding/rs.o/base64)
```

A merge becomes:

```lisp
(merge.left . receipt-043a)
(merge.right . receipt-044b)
(merge.scope . fs.o/SKILLS.md/gs.o/encoding)
```

Validation checks whether the merged relation is consistent. If accepted, the merge gets a receipt.

---

## 5. Version IDs as Receipts

A version ID is a receipt handle:

```text
receipt:5040/2820
omi-version:fs.o/SKILLS.md/gs.o/encoding/rs.o/base64@receipt-2820
```

This identifies scope, carrier, relation, and receipt. A peer can resolve: which file, which group, which record, which unit, which accepted receipt.

---

## 6. AGENTS.md and SKILLS.md in Version Control

`AGENTS.md` versions the allowed behavior. `SKILLS.md` versions the algorithms. `.imo` files carry normalized declarations. Receipts accept exact versions.

```lisp
(agent.allowed-skill . skill.base64.decode)
(agent.version-scope . fs.o/AGENTS.md/gs.o/permissions)

(skill.base64.decode.seed . o.base64.o)
(skill.base64.decode.route . omi-base-64-imo)
(skill.base64.decode.effect . pure)
(skill.base64.decode.version . v1)
```

A change to AGENTS.md may affect whether a skill is allowed. A change to SKILLS.md may affect how the skill computes. A change to `.imo` may affect the normalized carrier. A receipt identifies which exact combination was accepted.

---

## 7. Minimal Version-Declaration Format

A minimal OMI version declaration:

```lisp
(version . receipt-2820)
(version.parent . receipt-2819)
(version.scope . fs.o/SKILLS.md/gs.o/encoding/rs.o/base64/us.o/schema)
(version.seed . o.base64.o)
(version.route . omi-base-64-imo)
(version.carrier . SKILLS.md)
(version.algorithm . skill.base64.zero-polynomial)
(version.schlafli . "{3,3}")
(version.betti . "(1 0 0)")
(version.effect . pure)
(version.result . accepted)
```

A proposed delta:

```lisp
(delta.intent . update-base64-schema)
(delta.parent . receipt-2819)
(delta.scope . fs.o/SKILLS.md/gs.o/encoding/rs.o/base64/us.o/schema)
(delta.seed . o.base64.o)
(delta.route . omi-base-64-imo)
(delta.effect . pure)
(delta.status . candidate)
```

Accepted:

```lisp
(receipt.delta . receipt-2820)
(receipt.parent . receipt-2819)
(receipt.accepts . delta.intent)
(receipt.result . accepted)
```

---

## 8. Canon Statement

OMI version control treats every version as a scoped, validated relation. `o.o` is the neutral origin object. Objects such as `o.base64.o` are scoped seed models that define neutral encoding interpretation surfaces. Routes such as `omi-base-64-imo` declare how the seed moves between citation and carrier. FS/GS/RS/US provide the place-value scope hierarchy. SKILLS.md defines the exact algorithms that make the relation reproducible. AGENTS.md defines which version transitions are allowed. Betti numbers describe the topology of the accepted relation. Schläfli symbols describe the projected geometric class. Receipts accept version transitions.

Therefore a version is not merely a file snapshot. A version is an accepted scoped relation over a carrier file, interpreted through a seed object, validated by deterministic skills, and projected through topology.

---

## Transition to the Mirrors

The state files define the doctrine. The seed objects define interpretation surfaces. The citation routes define how seeds travel between OMI and IMO. The FS/GS/RS/US scopes define where in a file a version lives. The receipts accept the version.

The mirrors (`truth-gates/*.imo`) carry the normalized compiled form. Versioning the mirrors means versioning the compiled canon itself.
