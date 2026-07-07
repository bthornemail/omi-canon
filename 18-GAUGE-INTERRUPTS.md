# State 18 — Gauge Interrupts: The Selection Surface

## What This State Is

This state is the transition from "what names can be read" to "which interpretation is selected." After defining the vocabulary of projection faces, the gauge is what chooses *which orientation* to read on an already-resolved blackboard surface.

The gauge is not a structure. It is a selection — the hairline on a slide rule, the plinth line between two powers.

---

## The Gauge as Selection

The fundamental algebraic analogy:

```
a³ − b³ = (a − b)(a² + ab + b²)

difference    gauge line    plinth surface
of cubes      (selection)   (reference face)
```

The gauge does not create the cubes. It selects the line by which their difference becomes readable. The plinth surface `(a² + ab + b²)` exists independently of the gauge — it is the reference face between two volumes.

The gauge is to the blackboard what the cursor is to a slide rule: the scale exists already; the gauge picks which line to read.

---

## Gauge Word vs. Gauge Table

There are two distinct concepts that share the name "gauge":

### The Gauge Table

The gauge table is the canonical set of possible alignments. It belongs to documentation, not to the runtime. The gauge table explains:

- Which orientations are available
- Which plinth surfaces correspond to which differences
- Which sexagesimal weightings produce bijective readings

The gauge table is static. It is defined once and referenced thereafter.

### The Gauge Word

The gauge word is an in-stream selection. It appears as a field within a Relation — typically as a Word16 or Word32 that selects one entry from the gauge table.

The gauge word is the runtime manifestation of the gauge. It is what turns an addressed blackboard surface into a specifically oriented projection.

---

## The Pleth

The plinth between two cubic volumes — `(a² + ab + b²)` — has a specific name in OMI: the **pleth** (from πλῆθος, "fullness / surface of extension").

The pleth is the reference surface that the gauge selects against. It is the "Always Positive" term in the SOAP structure:

```
Same    Opposite    Always Positive
(a + b)(a² − ab + b²)   ← sum of cubes
(a − b)(a² + ab + b²)   ← difference of cubes
       ^         ^
       sign      middle term is always positive
       flips     (the plinth is orientation-independent)
```

The "Always Positive" property is what makes the gauge bijective: regardless of which cube is larger, the plinth face is always readable.

---

## Sexagesimal Weighting

A sexagesimal bridge of the form:

```
60x² + 16xy + 4y²
```

is a weighted gauge surface. The coefficients weight the plinth so that the selected difference `(x − y)` maps to a unique position in a numeration frame.

```
weighted pleth × gauge line = traversed volume at resolution R
```

This is how gauge interrupts work at the algorithmic level: the gauge word selects a weighting, and the weighted plinth produces a uniquely positioned reading.

---

## The Four Gauges

The canonical gauge set follows the four operational axes:

- **FS** (o---o) — object carrier boundary. Selects orientation on the carrier span.
- **GS** (/---/) — path navigation. Selects orientation on the address path.
- **RS** (?---?) — query / record. Selects orientation for record comparison.
- **US** (@---@) — socket / point. Selects orientation at a specific address.

Each gauge is a Word16 within the Relation's field structure. Together they define the four-dimensional orientation of the projected blackboard surface.

---

## When the Gauge Interrupts

A gauge interrupt occurs when the runtime encounters a gauge word that selects a different orientation than the current projection:

```
Current projection:   FS gauge = 0x01  (object carrier)
Incoming gauge:       FS gauge = 0x03  (different alignment)
Runtime action:       interrupt current projection
                      re-read blackboard at new orientation
```

The interrupt does not modify the blackboard. It modifies the reading. This is why the gauge is not part of the kernel — the kernel has no readings, only Relations.

---

## Doctrine Sentence

> The gauge does not create the scale. The gauge selects the line. The gauge word is an in-stream interrupt that changes which face of the blackboard is read.
