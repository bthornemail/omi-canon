# OMI Canon Projections

## Status

This file defines the canon gate for projection.

PROJECTIONS.md defines how accepted truth becomes visible. It does not define truth. It does not replace executable truth gates. It defines how executable truth is exposed, folded, projected, and inspected.

---

## 1. Projection Is Not Authority

```text
projection != validation
projection != authority
render != believe
```

A projection displays accepted state. It does not create it.

---

## 2. The Projection Hierarchy

```text
Guiding gates:
  ONTOLOGY.md
  DOCTRINE.md
  MANIFESTO.md
  PROJECTIONS.md
  GLOSSARY.md

Executable truth gates:
  RULES.omi  (MUST)
  FACTS.omi  (FACT)
  CLOSURES.omi  (CLOSE)
  COMBINATORS.omi  (COMBINE)
  CONS.omi  (CONS)

Compiled mirrors:
  RULES.imo
  FACTS.imo
  CLOSURES.imo
  COMBINATORS.imo
  CONS.imo

Projection surfaces:
  DOM / CSSOM / JSDOM
  JSON Canvas
  SSE / WAN telemetry
  IPv6 frame / eBPF gate
  Markdown / PDF / HTML
  CLI / TUI
  Visual (SVG / Canvas / QR / barcode)
  Memory (5040 ring / receipt)
```

---

## 3. The Pipeline

```text
validate → resolve → record → materialize → project → inspect
```

Projection is the sixth stage. It is never the first.

Canonical order:

```text
Q_frame(S) validates the carrier.
nibble-walk selects the local region.
Base36 indexes the socket.
Q_xy projects the coordinate.
ψ(frame, path, socket, receipt) instantiates one slice.
DOM exposes the accepted projection.
```

---

## 4. Six DOM Projection Handles

OMI uses six DOM projection handles:

```text
id             -> local pointer / selector hook
data-omi       -> readable declaration surface
data-imo       -> interpreted mirror surface
<o>            -> object carrier boundary
<omi>          -> declaration container
<imo>          -> interpretation / receipt container
```

---

## 5. The Four Gauges

```text
o---o  = Gauge 0 / FS  / object / file / carrier boundary
/---/  = Gauge 1 / GS  / path   / group / context
?---?  = Gauge 2 / RS  / query  / record / relation
@---@  = Gauge 3 / US  / socket / unit / point
```

The canonical compact carrier:

```text
o---o/---/?v=<base64url>;l=<length>;h=<hash>@<base36-ref>@
```

---

## 6. Base36 Response Rule

Base36 may respond only after frame validation:

```text
Q_frame(S) = 0
  -> Base36 reference socket may resolve
  -> local x,y coordinates may be derived
  -> Q_xy may project
  -> receipt may accept
```

Invalid:

```text
Base36 symbol authorizes state
DOM id authorizes state
emoji authorizes state
barcode authorizes state
```

---

## 7. The Bridge Equation

```text
Q_xy(x,y) = 60x² + 16xy + 4y²
          = 4(15x² + 4xy + y²)
```

Projection assertions:

```text
Q(0,0) = 0
Q(3,3) = 720
Q(x,y) is integer for x,y in 0..3
Q(x,y)/6 lies within 0..120 for x,y in 0..3
Q(x,y) mod 240 ranges within 0..239
local240 = Q(x,y) mod 240
slot5040 = fano7×720 + role3×240 + local240
```

---

## 8. Portal Promise

```text
One object.
Many portals.
Inspectable history.
Portable context.
Validation before projection.
Agreement without platform lock-in.
```

---

## 9. Deterministic GUI Projection

CSS / DOM / JSDOM may manipulate OMI reference projections. They do not mutate OMI truth directly.

```text
CSS selects projection.
JSDOM manipulates structure.
DOM receives interaction.
OMI validates.
Receipt accepts.
```
