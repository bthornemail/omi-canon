# State 22 — Propagation Model: Analog Disturbance and Independent Observers

## What This State Is

This state is the transition from "what world is rendered" to "how the world senses analog disturbance." After surface applications define the rendered world, the wave surface interpreter is how OMI-classified analog signals become candidate Relations.

The universe does not speak OMI. The universe emits waveforms — electromagnetic, acoustic, thermal, mechanical. The wave surface interpreter is the boundary where those waveforms become addressable disturbances.

---

## The Problem

OMI is a deterministic protocol built on Relations. The physical world is analog, continuous, and noisy. Before a sensor reading can enter the protocol, it must:

1. Be sampled from an analog signal
2. Be classified as a known waveform type
3. Be projected into a Relation
4. Be presented to an IMO port for acceptance

The wave surface interpreter handles steps 1–3. Step 4 belongs to State 15 (IMO Ports).

---

## Wave Classification

Analog signals are classified by their projection onto three axes:

- **Cadence** — is the signal periodic, aperiodic, or transient?
- **Amplitude** — what is the signal's energy range?
- **Shape** — does the signal match a known waveform template (sine, square, pulse, noise)?

The classification produces a tuple:

```
(wave-type, cadence, amplitude-range, confidence)
```

This tuple becomes a Relation.

---

## From Wave to Relation

The wave surface interpreter projects a classified waveform onto the 128-bit wire frame:

- The wave type selects the segment layout
- The cadence fills the constant segments
- The amplitude maps to the variable segments
- The confidence becomes the receipt carrier

The projection is not a measurement of the physical world. It is a mapping from a classified waveform to a Relation. The Relation is not the wave — it is the wave's address within the protocol.

---

## Doctrine Sentence

> The propagation model does not measure the world. It classifies waveforms as candidates for relation. The world enters OMI not as truth, but as addressable disturbance. Independent observers exchange receipted relations across carriers. The model carries; it does not accept.
# State 16 — Distributed Open World: Independent Observers

## What This State Is

This state is the transition from "how the machine runs" to "how it lives in the world." After building the instruction set architecture, I needed to place the machine in an ecosystem — the open world of agents, kernel gates, networking protocols, and hardware environments.

This is the state where OMI leaves the abstract realm of mathematics and enters the physical realm of radio waves, network packets, kernel space, and distributed agents.

---

## Part I — The Open World Model

### 1.1 The Default

The open world is the default for OMI. Any declaration, any gossip fragment, any render can enter the system as a candidate. The open world does not pre-filter — it post-validates.

### 1.2 The Consumer Promise

```
One object.
Many portals.
Inspectable history.
Portable context.
Validation before projection.
Agreement without platform lock-in.
```

### 1.3 The Two Core Views

Every object in the ecosystem has two inspectable forms:

| View | Consumer Question | Meaning |
|---|---|---|
| Linear | What happened? | Replay / source-object order |
| Hierarchical | Where does it belong? | Scope and containment order |

Both are projections. Neither validates the object.

### 1.4 Safety in the Open World

Open world does not mean unsafe world. Portal surfaces default to:

```
read-only projection first
interaction second
execution last
```

Safety requirements include:
- Sanitizing innerHTML
- Sandboxing portals
- Isolating ShadowDOM widgets
- Separating display from validation
- Marking unknown sources
- Showing unverified objects
- Blocking unsafe scripts
- Preserving receipt inspection

---

## Part II — The Agent Model

### 2.1 The Canon vs. Portal Boundary

OMI defines a strict boundary between two repositories:

| Repository | Role |
|------------|------|
| **omi-canon** (this repo) | Abstract protocol / documentation / derivation surface |
| **omi-portal** | Implementation / collaboration / application surface |

The doctrine:

> o---o defines the doctrine. omi-portal proves the doctrine.

They must not collapse into each other.

### 2.2 The Bridge

The bridge between canon and portal is the declarative lookup table model:

```text
RULES constrain
FACTS declare
CLOSURES bound
COMBINATORS transform
CONS folds
CONFIGURATIONS bind runtime
Validation determines
Omi-Attestation witnesses
Accepted Omi-State may be recorded
```

### 2.3 The Non-Collapse Doctrine

```text
Projection is not authority.
Implementation is not doctrine.
Doctrine is not proof.
Proof is not collaboration.
Collaboration is not possession.
Validation determines.
Omi-Attestation witnesses.
Accepted Omi-State may be recorded.
```

### 2.4 Agents as Portals

An OMI agent is a portal that can act autonomously within the rules. Agents:

- Read frames from the environment (network, sensors, user input)
- Validate frames through the gate
- Write receipts to the ring
- Project results to their surface

Agents do not create rules. Agents operate within the rules declared in `RULES.omi`.

---

## Part III — The eBPF Kernel Gate

### 3.1 The Kernel Boundary

The eBPF/XDP gate is a kernel-level program attached to the NIC driver layer. It validates every incoming IPv6 OMI frame before the kernel stack touches it.

### 3.2 Gate 1 — Structural Validation

```c
// Simplified eBPF Gate 1: Quadratic Law validation
int omi_gate1(struct xdp_md *ctx) {
    void *data = (void *)(long)ctx->data;
    void *data_end = (void *)(long)ctx->data_end;

    // Parse IPv6 source address for OMI frame
    // Verify Q_frame(S) = 0
    // Branchless, unrolled check

    if (Q_frame != 0)
        return XDP_DROP;
    return XDP_PASS;  // Pass to Gate 2
}
```

Gate 1 evaluates the Quadratic Law zero-sum equation — a branchless, unrolled check.

### 3.3 Gate 2 — Delta Law Resolution

```c
// Simplified eBPF Gate 2: Delta Law resolver
int omi_gate2(struct xdp_md *ctx) {
    // Extract LL, NN, MM from frame
    // Set C = (LL * 0x1337) & 0xFFFF
    // Apply Delta_C up to 15 steps
    // If NN -> MM not found -> XDP_DROP

    uint16_t x = NN;
    for (int i = 0; i < 15; i++) {
        if (x == MM)
            return XDP_PASS;  // Converged
        x = delta16(x, C);
    }
    return XDP_DROP;  // Did not converge
}
```

Gate 2 runs the Delta Law resolver: extract Fano point LL, set NN = S₂ and MM = S₅, then iterate delta(NN) up to 15 steps looking for convergence to MM.

### 3.4 Performance Characteristics

- Total BPF bytecode: ~14.7 KB
- JITed native code: ~1.5 KB
- Passes eBPF verifier: yes
- False positives: zero
- Memory allocation: none (before validation)
- Context switch: none (before validation)

### 3.5 The Genesis Frame at the Kernel Level

The genesis frame `0100-03bf-7c00-2b01-2f01-1434-039f-01ff` passes both gates:

- Gate 1: Q(S) = 0 (valid structural surface)
- Gate 2: Delta_{0x1337}(0x7C00) = 0x1434 in 1 step (convergent)
- Ring slot: 0x7C00 mod 5040 = 1504 (boot slot)

This means the entire cosmology can be bootstrapped from a single kernel-level frame that passes at line rate.

---

## Part IV — The Hardware Target

### 4.1 ESP32-S3 + LoRa

The original hardware target is the ESP32-S3 with SX1262 LoRa transceiver:

```text
ESP32-S3:  240 MHz dual-core Xtensa LX7
SX1262:    LoRa transceiver, 915 MHz (US ISM band)
Memory:    512 KB SRAM, 16 MB flash
```

The OMI envelope (512 bits) fits within the LoRa payload constraints:

```text
LoRa payload:   up to 256 bytes
OMI envelope:   64 bytes (512 bits)
Margin:         192 bytes for headers and redundancy
```

### 4.2 The Radio VM

The OMI envelope becomes a 512-bit instruction frame executed over RF:

```text
Radio VM Layer       ← OMI envelope semantics
Multiplex/Demux      ← channel + stream routing
Envelope Stream Codec ← stream.c parser
LoRa PHY (SX1262)   ← RF transport
```

The Radio VM is the same machine as the software ISA. The same opcodes dispatch the same operations, regardless of whether the transport is RF, IPv6, serial, or shared memory.

### 4.3 The Probe Handshake

The probe lifecycle over radio:

```text
IDLE
  → (SX1262 detects preamble)
  → PROBE_SENT (send capability frame)
  → PROBE_RECEIVED (parse peer capability)
  → NEGOTIATING (agree on transport parameters)
  → SYNCED (bit-level synchronization)
  → ACTIVE (full OMI operation)
```

The capability bitfield declares:

```text
AUDIO_ADPCM
AUDIO_OPUS
SENSOR_GPIO
VM_EXEC
MESH_ROUTING
RELAY_MODE
```

### 4.4 Transport Independence

The probe logic is transport-independent. The same state machine works over LoRa, WiFi UDP, BLE, serial, file replay, or simulation. The transport delivers bytes; the probe handles the rest.

---

## Part V — Network Integration

### 5.1 IPv6 Mapping

The 128-bit OMI frame maps directly into the 128-bit IPv6 address space:

```text
IPv6 source address = OMI frame
```

This means:

- OMI frames are routable over IPv6 without encapsulation
- The omicron anchors (0x03BF, 0x039F) are visible in the IPv6 source address
- Kernel-level eBPF filters can detect and validate OMI frames at line rate
- Standard IPv6 routing infrastructure can forward OMI frames

### 5.2 Mesh Routing

OMI supports mesh network routing through the BROADCAST and ROUTE opcodes:

```text
Broadcast: send frame to all peers
Route: send frame to specific peer through intermediate hops
```

The mesh routing layer is agnostic to the physical transport — it works over LoRa mesh, WiFi mesh, or simulated topology.

### 5.3 The Service Bus

The service bus pattern maps to OMI's fact grounding:

- A service declares a rule in `RULES.omi`
- An implementation grounds the rule as a fact in `FACTS.omi`
- A consumer validates the frame, resolves the truth row, and writes a receipt
- The service bus is the set of all accepted fact-receipt pairs

Default bitblip policy for service bus: `accept-exact`

---

## Part VI — The Implementation Surfaces

### 6.1 Protocol Surfaces

The abstract protocol surface (this canon) is where the palindrome, the Delta Law, the Quadratic Law, the factorial geometry, the ring indexer, and all the doctrines live.

### 6.2 Implementation Surfaces

The implementation surface (omi-portal) proves that these abstract doctrines are executable.

The boundary between them is the truth gates:

```text
RULES.omi:   what must be true
FACTS.omi:   what is true
CLOSURES.omi: what is bounded
COMBINATORS.omi: what can be composed
CONS.omi:    what can be reduced
```

### 6.3 Trust Labels

Portals may translate protocol state into plain language labels:

```text
Accepted        — frame validated, receipt written
Unverified      — frame received, not yet validated
Conflicting     — multiple receipts for same slot
Expired         — receipt beyond ring horizon
Mirrored        — receipt from mirror (reverse direction)
Local-only      — not broadcast to network
Rejected        — frame failed validation
Replayed        — receipt re-derived from replay
```

The label is an interface summary. The receipt chain is the inspectable evidence.

---

## The Transition

From this state — having classified analog signals and placed the machine in the distributed world — the canon continues to Notation Multiplexing and the remaining constitutional spine. The propagation model carries candidate relations; it does not accept them.
