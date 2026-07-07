# A3 — Projection Algorithm

## Definition

The projection algorithm derives text, graph, SVG, 3D, and XR views from canonical state. Every projection is a pure function of the canonical state — it does not modify state, and it does not hold authority.

## Specification

```text
Input: canonical_state :: 128-bit frame
       surface_selector :: enum { text, graph, svg, x3d, xr }

Output: artifact :: projection artifact (format depends on selector)

Invariant:
  projection(S, selector) = artifact
  projection_is_authority(S, selector) = false  // always

Projection types:
  text    — Human-readable OMI notation with indentation
  graph   — Graphviz DOT rendering of frame topology
  svg     — Vector graphic showing segment geometry
  x3d     — 3D scene graph (X3D/VRML format)
  xr      — Mixed reality overlay (WebXR)

Rewrite surfaces: Each projection uses a rewrite table defined by
  the surface selector and the canonical frame segments.

Forbidden: A projection may never validate or accept state.
  Only validation and receipt may accept (see A6).
```

## Proof Obligations

| # | Question | Constructive | Falsification |
|---|----------|-------------|---------------|
| Q1 | Source of truth | Views generated from canonical state; projections rebuildable | Cached artifact as authority causes divergence from recomputed output |
| Q2 | System movement | Visual motion rendered from evolving canonical index | Projection-driven state movement without event/log is invalid |
| Q3 | Control vs payload | Renderer consumes decoded state, not raw stream control | Renderer guessing control boundaries creates non-canonical views |
| Q4 | Meaning across projections | All views generated from same source state | Projection-specific ontology unmappable to source is invalid |
| Q5 | Intervention and replay | Local pause is projection-only, non-authoritative | UI dwell time defining canonical scope is invalid by law |
| Q6 | Collaboration without authority | Collaborators read snapshots, not hidden renderer internals | Projection-only scraped state cannot act as canonical authority |
| Q7 | Branch and return | Return to canonical reference available from any branch view | Projection-only branch identity without canonical anchor is invalid |
| Q8 | Open meaning closed law | Many projections map to one canonical source | Any view elevated to source-of-truth is invalid |

## Implementation Reference

See `05-PROJECTIONS.md` for the full projection specification including the 6 DOM handles (address, receipt, error, frame, graph, rewrite), the bridge equation, and the meta-circular compiler. See `08-ISA.md` for the FOLD (0x19) and BITBOARD_APPLY (0x1A) opcodes used in projection.

## Dependencies

- `05-PROJECTIONS.md` — Full projection specification
- `08-ISA.md` — Fold and bitboard operations
- `02-DOCTRINE.md` — Rule 0x0B (projection-is-not-authority)
