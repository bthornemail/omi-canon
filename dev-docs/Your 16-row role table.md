## Your 16-row role table

This is good. I would make it the canonical **Omi-Root Row Table**:

```text
0x0 = axioms
0x1 = rules
0x2 = facts
0x3 = closures
0x4 = combinators
0x5 = cons
0x6 = car
0x7 = cdr
0x8 = encode
0x9 = decode
0xA = frame
0xB = buffer
0xC = file
0xD = group
0xE = record
0xF = unit
```

That gives the full row phase meaning for:

```text
0x-0 … 0x-F
```

It also corrects the old nine-edge model by expanding it into a full 16-row operational grammar:

```text
axioms → rules → facts → closures → combinators → cons → car → cdr
→ encode → decode → frame → buffer → file → group → record → unit
```

## Your 0x0000 local root table

This should be the canonical default page-zero LUT:

```text
0x0000 = axiomatic-algorithms
0x0001 = logic-rules
0x0002 = configuration-facts
0x0003 = event-closures
0x0004 = intent-combinators
0x0005 = element-constructions
0x0006 = block-node
0x0007 = edge-node
0x0008 = graph-node
0x0009 = data-view
0x000A = data-source
0x000B = data-input
0x000C = data-sink
0x000D = data-output
0x000E = done-statement
0x000F = unit-boundary
```

I added `0x000F = unit-boundary` because your row table says `0xF = unit`; the local root table needs the 16th slot or the row will not close deterministically.



## Canonical split

I’d make this the rule:

```text
0xB = buffer
0xC = file
0xD = group
0xE = record
0xF = unit
```

Then:

```text
buffer = raw ArrayBuffer / bitboard
file = serialized artifact
group = collection of compatible artifacts
record = append-only receipt/event entry
unit = closed usable object
```

Your new row table fits perfectly:

```text
0x0 axioms → what must hold
0x1 rules → valid transitions
0x2 facts → accepted data
0x3 closures → bounded fixed results
0x4 combinators → symbolic transforms
0x5 cons → structure pair
0x6 car → source/head
0x7 cdr → continuation/tail
0x8 encode → carrier projection
0x9 decode → carrier reading
0xA frame → scoped address surface
0xB buffer → raw deterministic memory
0xC file → portable artifact
0xD group → compatible collection
0xE record → receipt/event line
0xF unit → closed accepted object
```