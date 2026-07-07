# State 06 — Protocol: The Wire

## What This State Is

This state is the transition from "how it becomes visible" to "how it communicates." After defining projection surfaces, I needed to specify the wire format — the concrete protocol that carries state across the boundary between senders and receivers, between validation and projection, between the gate and the registry.

This state defines the envelopes, the receipts, the ring indexer, the frame mapping to IPv6, and the overwrite policies that govern how the protocol operates on the wire.

---

## 1. The Frame Format

### 1.1 The 128-Bit Wire Frame

The canonical OMI transmission is a 128-bit instruction frame divided into eight 16-bit segments:

```text
S = [S₀, S₁, S₂, S₃, S₄, S₅, S₆, S₇]
```

Written as:

```text
omi-LLLL-03bf-NNNN-2bLL-2fLL-MMMM-039f-LLff/48
```

### 1.2 Segment Layout

| Segment | Offset | Name | Role |
|---------|--------|------|------|
| S₀ | 0–15 | `LL00` | Scope/lens/ket selector |
| S₁ | 16–31 | `03bf` | Lower omicron anchor (chiral entry) |
| S₂ | 32–47 | `NNNN` | Antecedent / free variable input |
| S₃ | 48–63 | `2bLL` | Lens-derived binding constant |
| S₄ | 64–79 | `2fLL` | Lens-derived binding constant |
| S₅ | 80–95 | `MMMM` | Consequent / resolution output |
| S₆ | 96–111 | `039f` | Upper omicron anchor (cardinal exit) |
| S₇ | 112–127 | `LLff` | Scope terminator |

### 1.3 Validation

A frame is valid if and only if:

```text
Q_frame(S) = E_var + E_const = 0
```

Where:
- `E_var` = the variable error from free segments (S₂, S₃, S₄, S₅)
- `E_const` = the constant error from fixed segments (S₀, S₁, S₆, S₇)

### 1.4 The Truth Row

Every valid frame yields exactly one truth row: `(LL, NN, MM)`.

- `LL` = the scope selector from S₀ (two nibbles: high = context/family, low = execution slot)
- `NN` = the antecedent from S₂
- `MM` = the consequent from S₅
- The proven transition is `NN → MM` through the Delta Law within the Fano bound

---

## 2. The Envelope Format

### 2.1 The 512-Bit Envelope

While the frame is 128 bits, the transmission envelope is 512 bits — four frames plus structural metadata:

```text
[Frame 0][Frame 1][Frame 2][Frame 3][Header][CRC]
```

### 2.2 The Gauge Table

The envelope header contains a 128-entry gauge table that maps opcodes to their execution semantics:

| Gauge | Entry | Role |
|-------|-------|------|
| 0x00–0x13 | 20 ops | Core ISA (NOP, PROBE, SEND, etc.) |
| 0x14–0x1F | 12 ops | Extended ISA (GAUGE_BIND, FOLD, etc.) |
| 0x20–0x7F | 96 entries | Application-specific gauge lambdas |

Each gauge entry is a lambda-like structure with car, cdr, payload, and symbolic stack.

### 2.3 The Stream Parser

The protocol uses a streaming state machine:

```text
WAITING → HEADER → PAYLOAD → COMPLETE
```

| State | Transition | Action |
|-------|------------|--------|
| WAITING | Anchor detected | Parse header |
| HEADER | Valid header | Receive payload |
| PAYLOAD | Payload complete | Validate |
| COMPLETE | Valid | Write receipt |

---

## 3. The Receipt Format

### 3.1 The 64-Bit Receipt

Every accepted truth row produces a 64-bit receipt:

```text
provenance:16 | steps:8 | LL:8 | NN:16 | MM:16
```

| Field | Bits | Description |
|-------|------|-------------|
| Provenance | 16 | Source identifier / frame origin |
| Steps | 8 | Number of Delta steps to converge |
| LL | 8 | Scope selector (ket) |
| NN | 16 | Antecedent value |
| MM | 16 | Consequent value |

### 3.2 Writing a Receipt

A receipt is written only after:

1. Frame validation: `Q_frame(S) = 0`
2. Truth row extraction: `(LL, NN, MM)`
3. Delta/Fano resolution: `NN → MM` within the bounded window (max 15 steps)

```text
Only validation and receipt may accept.
```

### 3.3 Receipt Properties

- Receipts are **deterministic**: the same frame + same C always produces the same receipt
- Receipts are **sequential**: they are written in order to the ring
- Receipts are **immutable**: once written, they cannot be changed (only overwritten under explicit policy)

---

## 4. The 5040-Slot Replay Ring

### 4.1 The Ring Structure

OMI's memory is a fixed circular buffer of exactly 5040 slots (7! = 5040):

```text
slot5040 = fano7 × 720 + role3 × 240 + local240

fano7    ∈ 0..6
role3    ∈ 0..2
local240 ∈ 0..239
```

Each slot stores a 64-bit BigInt receipt.

### 4.2 Cursor Management

The ring cursor advances by `steps` positions modulo 5040:

```text
cursor = (cursor + receipt.steps) mod 5040
```

Managing concurrent writes via atomic compare-and-swap (CAS):

```text
1. Read current cursor position
2. Compute target position: (cursor + steps) mod 5040
3. CAS the cursor to the new position
4. If CAS fails, retry
```

### 4.3 Genesis Fixture

```text
BOOT_ADDRESS = 0x7C00
BOOT_SLOT = 0x7C00 mod 5040 = 1504
GENESIS_LL = 0x01
GENESIS_NN = 0x7C00
C = (0x01 × 0x1337) & 0xFFFF = 0x1337
GENESIS_MM = Delta_{0x1337}(0x7C00) = 0x1434
GENESIS_STEPS = 1
```

Canonical genesis frame: `0100-03bf-7c00-2b01-2f01-1434-039f-01ff`

### 4.4 Slot Decomposition

The 5040-slot ring decomposes naturally:

```text
7 Fano points × 3 S-P-O roles × 240 oriented byte states = 5040
```

Each slot encodes:
- Which Fano point resolved the transition (7 possibilities)
- Which semantic role the receipt occupies (3: Subject/Predicate/Object)
- Which oriented packet/active byte surface state was recorded (240 possibilities)

---

## 5. Overwrite Policy

### 52 The Five Overwrite Rules

The ring supports five overwrite policies for existing receipts:

| Policy | Condition | Action |
|--------|-----------|--------|
| Cold | Slot is empty | Write |
| Warm | Same LL, NN, MM | Overwrite |
| Stale | Provenance mismatch | Overwrite with warning |
| Backoff | Different LL, NN | Skip slot, advance cursor |
| Conflict | Same slot, different provenance | Flag for resolution |

### 5.2 Warm Overwrite

A warm overwrite occurs when the same truth row `(LL, NN, MM)` is re-derived from the same frame. The new receipt is written with the new timestamp/provenance. This is the normal case for repeated validation.

### 5.3 Conflict Resolution

When two different truth rows map to the same slot (a collision), the system does not resolve by recency or authority. It flags the conflict for resolution through the agreement pipeline:

```text
conflict detected
  → flag both receipts
  → route to resolver
  → resolver evaluates both claims
  → one is accepted, one is evicted
  → receipt updated
```

---

## 6. IPv6 Frame Mapping

### 6.1 The Mapping

The 128-bit OMI frame maps directly into the 128-bit IPv6 address space:

```text
IPv6 source address = OMI frame
```

The omicron anchors (0x03BF, 0x039F) appear in the IPv6 source address. An eBPF/XDP filter can detect OMI frames by scanning for these anchors in the first and last 16-bit words of the IPv6 source address.

### 6.2 Kernel-Level Validation

Gate 1 — Quadratic Law check (structural):

```text
Q_frame(S) = E_var + E_const
if Q_frame(S) != 0 → XDP_DROP
```

Gate 2 — Delta Law resolver (semantic):

```text
Extract LL, NN, MM from frame
Set C = (LL × 0x1337) & 0xFFFF
Apply Delta_C up to 15 steps
If NN → MM not found → XDP_DROP
```

Both gates are branchless, unrolled, and pass the eBPF verifier. The total BPF bytecode is ~14.7 KB (JITing to ~1.5 KB native).

### 6.3 Transport Independence

The frame format is transport-independent. It works over:

- **LoRa radio** (ESP32-S3 + SX1262) — the original target
- **IPv6** — as source address in UDP datagrams
- **WiFi / BLE** — as payload in any byte stream
- **Serial** — as raw bytes over UART
- **File replay** — as records in a log file
- **Shared memory** — as entries in a ring buffer (SharedArrayBuffer)

---

## 7. Probe and Handshake Protocol

### 7.1 Probe Lifecycle

```text
IDLE → PROBE_SENT → PROBE_RECEIVED → NEGOTIATING → SYNCED → ACTIVE
```

### 7.2 Capability Bitfield

The probe frame carries a capability bitfield that becomes the portable ABI:

```text
AUDIO_ADPCM
AUDIO_OPUS
SENSOR_GPIO
VM_EXEC
MESH_ROUTING
RELAY_MODE
```

Each bit declares that the peer supports the corresponding feature.

### 7.3 Transport Agnosticism

Key principle: **No transport assumptions.** Probe is just byte stream → envelope parser → state machine. Transport could be LoRa, WiFi UDP, BLE, serial, file replay, or simulation. The same probe logic works across all transports.

---

## 8. The Pipe Stack

The full protocol stack follows the doctrinal pipeline:

```text
source
  → carrier
  → reconstruction
  → causal proof
  → RS proof
  → acceptance
  → receipt
```

There is no database commit in this chain. The system proves relations and accepts receipts.

---

## The Transition to State 07

From this state — having defined the wire format — I moved to State 07 (The Unfolding) to answer: what are the mathematical consequences? What geometry emerges from these primitives?

Continue to `07-GEOMETRY.md`.
