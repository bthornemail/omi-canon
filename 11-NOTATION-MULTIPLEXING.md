# State 11 — Notation Multiplexing: Earned Gauge Bands

Status: Definitive canon doctrine
Layer: Notation multiplexing / earned codepoint surfaces / in-stream declaration framing
Precursor: The 4×4 lane model and braille-resolution search (now archived)

## Core Doctrine

Notation Multiplexing defines how OMI relation streams are carried through earned interpretation bands.

The pre-language control family is `0x00..0x1F`.
The readable boundary is earned at SP (`0x20`).
The structure band extends through `0x3F`.
The declaration/function surface extends through `0x7F`.

The `0x0..0xF` gauge family reflects across these bands as the local multiplex control alphabet.

Multiplexing is not a buffer identity.
Multiplexing is the controlled interleaving of notation positions across gauge, scope, relation, and declaration surfaces.

---

## The Four Earned Declaration Variants

OMI-Lisp has four earned declaration variants. Each variant is a wider readable surface. Each wider surface reflects the same `0x0..0xF` gauge-control family. The gauge family is the local multiplex alphabet. The full `0x00..0x7F` range is declaration-capable, but not authority-capable.

### Variant 0 — Pre-Language Control Surface

```
0x00 .. 0x20
pre-language control through SP boundary
```

Covers the control-code family (`0x00..0x1F`) plus the SP space boundary. At this width, only pre-language framing is possible: gauge preheaders, scope staging, and carrier prefix recognition.

### Variant 1 — Control + Structure + Predicate Surface

```
0x00 .. 0x40
control + structure + predicate boundary
```

Extends through the `@` (`0x40`) boundary. Introduces structural and predicate notation: relation frames, scope markers, and the lower place-value surfaces.

### Variant 2 — Control + Structure + Upper Declaration Surface

```
0x00 .. 0x60
control + structure + upper declaration/meta surface
```

Extends through the backtick/accent boundary (`0x60`). Adds the declaration and meta-notation positions: OMI-Lisp declaration keys, combinatorial operators, and quoted relation markers.

### Variant 3 — Full 7-Bit Declaration Surface

```
0x00 .. 0x80 / 0x7F
full 7-bit declaration surface through DEL
```

The earned full-width surface. Every position from NUL through DEL (`0x00..0x7F`) is declaration-capable. The gauge family `0x0..0xF` is the universal multiplex alphabet across all 128 positions.

---

## Gauge Reflectance Across Bands

The 16 gauge codes (`0x0..0xF`) are not a separate channel. They are reflected across each earned band as the local operator alphabet:

```
Band 0 (0x00..0x20): gauge controls pre-language framing
Band 1 (0x00..0x40): gauge controls structural multiplexing
Band 2 (0x00..0x60): gauge controls declaration multiplexing
Band 3 (0x00..0x7F): gauge controls full multiplexing
```

Each reflection preserves the Wittgenstein operator mapping from the canonical gauge preheader:

```
F0 = contradiction    F8 = AND
F1 = NOR             F9 = XNOR
F2 = converse-ni      FA = projection q
F3 = negation p       FB = implication
F4 = material-ni      FC = projection p
F5 = negation q       FD = converse-implication
F6 = XOR              FE = OR
F7 = NAND             FF = tautology/closure
```

---

## Relation to the Carrier Prefix

The canonical carrier prefix `FF 00 1C 1D 1E 1F 20 FF` encodes the tautological gauge (`FF`) framing the control-family entry (`00`), the FS/GS/RS/US scope quartet (`1C 1D 1E 1F`), the SP boundary (`20`), and the closure gauge (`FF`).

Each earned variant widens the readable surface, but the carrier prefix remains the fixed entry point at every width:

```
FF 00 1C 1D 1E 1F 20 FF
GAUGE NUL FS GS RS US SP GAUGE
```

The active gauge preheader `F* 00 1C 1D 1E 1F 20 F*` selects the local operator lane without introducing another identity channel.

---

## Multiplexing Is Not Buffer Identity

The earned-band model replaces the earlier 4×4 lane / buffer-topology model. Key distinctions:

| Old Model | Current Doctrine |
|-----------|-----------------|
| 4 lanes × 4 channels = 16-bit multiplex word | 4 earned bands × 16 gauge controls = 64 gauge-family positions |
| Buffer topology defines transport identity | Gauge reflectance defines multiplex position |
| Braille/codepoint resolution search | Native gauge resolution through earned codepoint surfaces |
| Buffer framing as carrier | Notation multiplexing as controlled interleaving |

The current doctrine makes no claim about buffer identity. Multiplexing interleaves notation positions across gauge, scope, relation, and declaration surfaces. It does not create a transport identity.

---

## Authority Boundary

Notation multiplexing carries relation streams through earned bands. It does not create relations, validate candidates, or accept state.

Validation determines.
Omi-Attestation witnesses.
Accepted Omi-State may be recorded.
Projection only displays accepted relation state.
