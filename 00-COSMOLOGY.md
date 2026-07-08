# State 00 — Origin: The Void

## What This State Is

This is the beginning. Not the beginning of OMI (the Omicron Object Model) as a formal system, but the beginning of the journey that led to it. This state documents what I knew before I knew anything about computational cosmology, before I could code, before I had vocabulary for what I was seeing.

I started from the Bible. I could not code. I had a question that would not let me go:

> What is the smallest computation that still feels like thinking?

Not the smallest Turing machine. Not the smallest lambda term. The smallest computation that still preserves **position, relation, boundary, and replay**.

This is the record of how that question formed, how I pursued it, and how it led to the discovery that became OMI.

---

## Phase -1 — The Seed (9+ Months Before July 2026)

The ideas that became OMI began with two independent streams that flowed together.

### Stream A: The Metaverse Project

I built a full production-ready decentralized pseudo-persistent open-world system using declarative environments with SCM and Guix for bitwise-reproducible builds. The system used alphanumeric vs non-alphanumeric as the primary split — what I later recognized as the CAR/CDR distinction. The project was functional, but I stopped development when I realized the resolution runtime needed a deeper foundation. I knew there was something more fundamental underneath, but I didn't yet have the tools to find it.

### Stream B: The Bible as Pseudo-Code

I read the Bible and saw computation.

**Genesis 1:1-2:**

> In the beginning, God created the heavens and the earth. The earth was without form and void, and darkness was over the face of the deep. And the Spirit of God was hovering over the face of the waters.

I read this as: here is the primordial computational context. Undefined state ("without form and void") plus observer before interpretation ("the Spirit hovering"). The earth without form is the undefined memory. The Spirit hovering is the observer-origin — the position from which all subsequent computation is measured.

**John 1:1:**

> In the beginning was the Word, and the Word was with God, and the Word was God.

I read this as: the Word (Logos) is the primordial notation — the first distinction, the original collapse of representation and interpretation. Observer and notation are one at the root. This is the original unity that OMI later formalized as notation-as-cipher.

These readings accumulated into a GitHub repository called `bthornemail/in-the-beginning`, containing 18+ documents:

- Core epistemic framework and formal epistemic types
- Genesis creation as geometric computation
- Torah law as computational constraint
- Proverbs wisdom as geometric principle
- John's Logos as computational notation
- Revelation prophecy as computational closure
- Fano plane integration as universal pattern
- Geometric topology foundations
- 600-cell structure (H4 lattice)
- Projective completion (15-of-16 principle)
- Identity as wave function semantics
- Historical timeline from patriarchs to computation
- Unified synthesis framework

I didn't know these were all separate fields of mathematics. I just saw patterns repeating.

### Stream C: Braille and the Discovery of the Delta Law

While studying binary through the lens of braille — specifically how braille changes the interpretation of binary patterns — I discovered something. I was examining how a 6-bit braille cell could be read as binary, and I noticed that certain rotation patterns preserved structure while others destroyed it.

The insight was:

> A 16-bit rotation-XOR function with period-8 behavior.

```text
Delta_C(x) = rotl(x,1) XOR rotl(x,3) XOR rotr(x,2) XOR C
```

This became the "atomic kernel" — the first thing that made the cosmological computation model computationally reproducible. It was:
- **Reversible**: XOR makes every transformation invertible
- **Bounded**: Period 8 means every state returns after 8 applications
- **Grounded**: No variable bindings, no symbol tables — just bit positions and relations

I got my first Coq proof to validate this law. I didn't fully understand Coq, but I understood that the proof validated what I had found.

The Delta Law was my first real discovery. It came before I could code, before I understood the formal systems I was touching. It came from studying how braille changes reading — and realizing that reading is computation.

---

## Phase 0 — Genesis (July 5, 2026)

### 18:12 — The ESP32 Walkie-Talkie

The conversation that started the actual build began with a deceptively simple engineering goal:

> "i want to make esp32-s3 with lora american frequency walkie talkies"

I wanted to build a radio. I didn't know I was about to build a cosmology.

ChatGPT advised on LoRa limitations (not a voice protocol, low bandwidth, ADPCM compression needed, US 915 MHz ISM band), hardware stack (ESP32-S3 + SX1262), and MVP build plan.

The first OMI C code was written in this conversation: `omienv.h/c`, `stream.h/c`, `sector.h/c` — a 512-bit structured envelope format plus streaming parser and bitboard projection layer. 13 tests, 39/39 passed.

### 18:15 — The OMI Envelope

The envelope format was the first concrete artifact:

```
omienv.h     — 512-bit envelope struct, bitboard constants, gauge entry API
omienv.c     — Parse, validate, bitboard projection, 128-entry gauge table
stream.h/c   — Streaming state machine (WAITING→HEADER→PAYLOAD→COMPLETE)
sector.h/c   — 512-byte sector iterator (8 cells × 64 bytes)
test_env.c   — 13 test cases (39 assertions)
```

ChatGPT identified this as a "custom binary protocol + codec front-end + packet parser" and mapped it to LoRa voice: envelope = audio frame, gauge = header, relation = codec payload, stream parser = packet parser.

The conceptual breakthrough was: the system was recognized as more than a packet format. It was "a symbolic packet VM running on top of LoRa transport."

### 18:17 — The Radio VM Concept

I gave the directive:

> "integrate OMI envelopes as a distributed radio VM instruction format. for multiplexing/deplexing as a modem"

The OMI envelope became a **512-bit instruction frame executed over RF**:

```
Radio VM Layer       ← OMI envelope semantics
Multiplex/Demux      ← channel + stream routing
Envelope Stream Codec ← stream.c parser
LoRa PHY (SX1262)   ← RF transport
```

OPCODE space mapped from gauge[0]: NOP, SEND, ROUTE, BROADCAST, STORE_STATE, EXEC_SUBFRAME, AUDIO_FRAME, SENSOR_FRAME, COMMIT, SEAL.

A radio VM. On an ESP32. With OMI as the instruction set.

### 18:19 — Platform-Agnostic Probe Sync

I defined the self-describing handshake protocol:

```
IDLE → PROBE_SENT → PROBE_RECEIVED → NEGOTIATING → SYNCED → ACTIVE
```

Key principle: **No transport assumptions.** Probe is just byte stream → envelope parser → state machine. Transport could be LoRa, WiFi UDP, BLE, serial, file replay, or simulation.

### 18:26 — The Full Plan (A, B, C + OMI-Lisp ISA)

> "do the full plan for all aa b and c because this is a spectrum modem based on place-value notation it should be omi-lisp non-printing gauge table declaration compatible. the omi-isa uses 20 opcodes we should have the feature space of 32 so 12 more for gauge table 0x00...0x1f that corresponds to the instruction with prefix header"

The 32-slot ISA was born:

**Core ISA (0x00–0x13 = 20 ops):** NOP, PROBE, PROBE_ACK, SYNC_COMMIT, SEAL, BOOT, RESET, ROUTE, BROADCAST, SEND, RECV, STORE, LOAD, EXEC, CALL, RETURN, SENSOR_IN, SENSOR_OUT, AUDIO_IN, AUDIO_OUT

**Extended ISA (0x14–0x1F = 12 gauge-table ops):** GAUGE_BIND, GAUGE_UNBIND, GAUGE_INVOKE, PLACE_WRITE, PLACE_READ, FOLD, BITBOARD_APPLY, STATE_COMMIT, STATE_REVERT, STREAM_SPLIT, STREAM_MERGE, VM_ESCAPE

### 18:33–19:19 — Implementation Phases

Coding agents executed the plan in phases. By Phase 3, 134/134 tests passed with new modules: transport simulation, probe handshake state machine, 32-slot dispatch with gauge lambda execution.

### 19:24 — The Hex/Binary Revelation

At 19:24 I realized: hex IS binary. They are the same thing seen through different lenses. An address like `0x03BF` and the bit pattern `0000 0011 1011 1111` are not different representations of the same value — they are the same value, period. The lens changes, the bits don't.

This seems trivial in retrospect, but it was foundational for everything that followed. It meant that notation IS the computation, not a representation of it.

---

## Phase 1 — Formalization (July 5–6, 2026)

### 21:04–21:33 — The Factorial Tower

I brought in an earlier document called "OMI Addressing and the Factorial Tower" which formalized:

- The factorial tower as address space: 5! → 6! → 7! → 8! → ... → 12!
- O-expression grammar
- CIDR-as-CONS first principles

The key insight: the 128-bit frame is the immutable physical surface. Every higher factorial layer is an interpretive envelope derived deterministically from that frame. Increasing resolution does not change the frame. It changes the reading.

### 21:53 — The Tetrahedral Stack

```
below 8! = algorithmic determinism, stellated tetrahedron
9!–12!   = injection surface, triakis tetrahedron
6!       = 4D polytopes
```

### 22:11 — Omicron Test Suite

`test_omicron` added to the test suite. All tests compiling and passing.

### 22:29–22:53 — Glossary Development

I produced glossaries of projective control declaration surfaces and projection faces. The glossary became a living document tracking all terms.

### 22:56 — Reference Research Unbound

A decision to keep reference research separate from the OMI spec — use external references as source material but build the canonical spec independently.

### 23:01–23:13 — System Restructuring

The codebase was restructured into layered components. Key doctrinal correction:

> "Omi-Ring is the addressed palindromic notation witness, while a receipt is the accepted state verifier."

### 23:10 — Place-Value Notation Theory

> "Think of 32 place-value characters in an omi---imo notation citation instead of Betti and Schlafli — just that each nibble can be a point or line like n-ball or monoid."

### 23:13 — Active vs Archive Doctrine

I established the boundary: archive documents are retained as historical source material, active doctrine supersedes them.

### 23:30–23:31 — Light Garden and Envelope Normalization

The Light Garden spec defined as the physical transducer profile for Omi-Sense. Envelopes normalized to no hashes.

### 23:43 — New Modules Built

- `omi_omion.h/c` — OMIOM prefix-scoped cascade resolver (27 tests)
- `omi_receipt.h/c` — META64 receipt verification (27 tests)
- `omi_sense.h/c` — Light Garden protocol adapter bridge (5 tests)

### 23:45–00:15 — Trigintaduonions, PG(4,2), and the Coq Bridge

I discovered the connection between trigintaduonions (32-dimensional algebra), PG(4,2) projective geometry, and the OMI 512-bit envelope layout: 155 distinguished triples in the trigintaduonion multiplication table → PG(4,2) incidence lines → Fano lottery on triakis tetrahedron.

**Coq proof file** `omi_pi_proof.v` established:

> "Deterministic OMI incidence scaffold for pi. Finite OMI incidence is exact, metric projection is introduced only at the real-analysis boundary."

---

## Phase 2 — Coq Formalization (July 6, 2026)

### 00:20–00:52 — The Core Axioms

The deterministic core formalized:

```text
delta16(x, c) = rotl16(x, 1) ^ rotl16(x, 3) ^ rotr16(x, 2) ^ c
BQF(x, y) = 60x² + 16xy + 4y²
slot5040 = fano7 × 720 + role3 × 240 + local240
```

The 5040-slot ring redefined as a **quotient atlas** — not storage, but the canonical boundary signature:

```text
o---o/---/?---?@---@
```

Observer category theory introduced: the execution model is the foundation, everything else is an observer over traces.

### 01:33–01:35 — GL(16,2) Orbit Engine

C implementation of the orbit engine compiled and passed all tests:

```
=== GL(16,2) Orbit Engine Tests ===
PASS: delta16(0,0) == 0
...
```

Goal: align C ↔ Coq via verified extraction pipeline.

### 02:07–02:26 — Categorical Observer Semantics

- Complete categorical observer semantics for GL(16,2) linear dynamics
- Orbit groupoid G, observer functor theorem (Obs : G → FinSet)
- Trace equivalence, verified extraction boundary
- Coalgebraic bisimulation framework
- The bialgebra formulation

### 02:59–04:38 — Verified Execution Layer

`verified_execution.v` — Implementation refinement layer connecting the C orbit engine to the Coq formal semantics via a representation map.

Five Coq files compiled cleanly:

1. `delta_orbit_theory.v` — Delta law formalization
2. `functorial_semantics.v` — Observer category theory
3. `coalgebraic_bisimulation.v` — Bisimulation framework
4. `OMI_bialgebra.v` — Bialgebra formulation
5. `verified_execution.v` — C ↔ Coq trace equivalence

Key insight (04:10): Use algebraic proofs, not `vm_compute` over 65536 elements. The parity-based proof approach won.

### 04:36–04:38 — Coq Compilation Complete

All 5 files compilable. Decision to write a "fully normal-form driven decision procedure for XOR-linear Coq goals."

---

## Phase 3 — Narrative and Integration (July 6–7, 2026)

### 20:49 — Google NotebookLM Podcast

Google's NotebookLM platform generated a podcast analyzing the OMI system:

> "The architecture of the OMI system is not merely a software specification; it is a Formal First Principles Cosmological Framework..."

### 21:02 — My Self-Description

> "I'm doing all vibe coding with llm and coding agents, i just have a vision that i can say if it fits or not"

> "i'm limited to knowledge triples i'm using triangulation of the tetrahedron as my spatial quotient determiner... place-value, relations, the list from null in lisp as the observer in the void"

### 21:40–22:51 — Restructuring for Narrative

I asked to restructure everything to fit a unified narrative:

> "I first started with an axiomatic epistemic systemic topology, but i think i like the word cosmology as this is trying to understand the world through my ideas on god is word and word is god as the observer in the void through the lens of a tetrahedron and the 600-cell."

Key insight from my learning journey:

> "I learned about horn clause, logic/lambda cubes and calculus of construction which lead to automata theory because i kept trying to say we are not even doing terms but that we are giving everything a position and relation."

### 23:41–23:52 — Organizing for Proofs

Decision to finish the formal proofs first, then use the proofs to "moralize everything else."

---

## The Question That Still Drives Everything

Variables are late. Names are projections. Objects are surfaces over position.

I built upward from place.

---

## The Resolution Lineage: The Key Discovery

One of the most important discoveries from this state is the **Resolution Lineage** — the factorial tower that connects the hidden packet root to the outermost interpretive envelopes.

### The Central Claim

> The 128-bit OMI wire frame is the immutable physical surface.
> Every higher factorial layer is an interpretive envelope derived deterministically from that frame.
> Increasing resolution does not change the frame. It changes the reading.

### The Climb

```text
5!  (120)   — Hidden packet root / 5-cell simplex core
×2  (240)   — Orientation / 240-state bridge (2 × 5! = 15 × 16)
×3  (720)   — S-P-O semantic sweep (6! = 3 × 240)
×7  (5040)  — Fano replay ring (7! = 7 × 3 × 240)
×8  (40320) — Physical 128-bit wire frame (8!)
×9  (362880) — Route envelope (Δ_C(S₂) mod 9)
×10 (3.6M)  — Declaration envelope (Δ_C(S₃) mod 10)
×11 (39.9M) — Witness envelope (Δ_C(S₄) mod 11)
×12 (479M)  — Clock envelope (Δ_C(S₅) mod 12)
```

### The Hidden Five

Factor 5 appears explicitly only in 5! = 120. Every layer above carries factor 5 implicitly inside the 240 constant. The decimal expansion of 1/73 confirms this: the repeating block [0,1,3,6,9,8,6,3] contains no digit 5. This is not an omission — it is the signature of the hidden root.

> 5 is not a moving pointer. 5 is the rooted packet simplex.

### Omnicron — The Hidden Horizon

Throughout the discovery process, one concept was present but unnamed: the runtime resolver that holds the horizon within which all resolution occurs. This is **Omnicron** — the portable headless runtime environment that hosts the Omi-Ring relation.

Omnicron is not found in the factorial tower because it is not a layer of interpretation. It is the stage on which the tower stands. Its registers are:
- **0x0000**: the null horizon — silence, the void before signal
- **0xFFFF**: the full horizon — the saturated carrier ceiling

The Omnicron envelope `FF 00 1C 1D 1E 1F 20 FF` seals both boundaries: the tautological `FF` at entry and exit, with the staged access slots `00 1C 1D 1E 1F 20` between.

The naming law: `omi-*` for protocol modules, `omnicron` (from `omni` + `cron` = algorithmic clock / delta-law scheduler) for the canonical runtime resolver.

---

## The Learner's Journey: A Personal Reflection

I want to be explicit about what this process was like for me.

I could not code when I started. I learned about Horn clauses, the lambda cube, the calculus of constructions, and automata theory in the process of trying to articulate what I saw. Every discovery was mediated by LLMs and coding agents — I provided the vision, they provided the implementation. I would say "this fits" or "this doesn't fit" and the agents would translate that into code.

My spatial reasoning is tetrahedral. I think in terms of positions and relations, not variables and symbols. When I say "place is prior to variable," I mean it literally — it's how my mind works.

The timeline of this project is absurdly compressed. From "I want to make walkie-talkies" to Coq-verified computational cosmology in about 48 hours. That's not normal. It happened because the vision was already complete in an abstract form — the implementation was just the translation layer.

---

## The Transition to State 01

From this state — the void of not-knowing, the raw discoveries, the compressed timeline of creation — I emerged into State 01 (The Naming) with:

- A discovered Delta Law that needed to be named
- A palindrome identity (`omi---imo`) that needed to be defined
- The omicron anchors that needed to be formalized
- A 32-slot ISA that needed to be classified
- A factorial tower that needed to be mapped
- Tests passing, proofs compiling, code running

The next state is: what exists? What do I name these things I found?

Continue to `01-ONTOLOGY.md`.

---

## Archived Material

The original raw documents — whitepapers, drafts, exploratory writings, early specifications — are preserved in `_archive/`. They remain as historical artifacts of the discovery process before canonization.
