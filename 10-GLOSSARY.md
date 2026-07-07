# State 10 — Glossary: The Closure

## What This State Is

This is the final state — the closure of the circle. Every term used in the preceding states is defined here. If a term appears in an earlier state and is not defined there, it is defined here.

The glossary is the last document to read and the first to reference. It closes the circle: the reader who started from 00-ORIGIN.md can end here with all terms defined, and the reader who starts here can navigate forward with confidence.

---

## A

**A-list** — Association list. The canonical form for rule-to-fact state transitions. See `02-DOCTRINE.md` §25.

**Acceptance** — The event of a validated frame having its truth row resolved, a receipt written, and the ring cursor advanced. "Only validation and receipt may accept."

**Address** — A 128-bit instruction frame divided into eight 16-bit segments. The fundamental position in OMI space. See `01-ONTOLOGY.md` §1.

**Agreement** — Not a feeling or vote but a structural event with a rigorous pipeline: reader → resolver → validation → receipt → materializer → projection → inspection. See `02-DOCTRINE.md` §14.

**Anchor** — See **omicron anchor**.

**Antecedent (NN)** — The beginning state in a truth row `(LL, NN, MM)`. The free variable input to the Delta Law resolver. See `01-ONTOLOGY.md` §1.

**Axiom** — An origami-inspired fold operation. Defines how constructed objects may be folded, reflected, complemented, aligned, resolved, and transformed. See `04-FOUNDATIONS.md` §7.

---

## B

**Base36** — The base-36 encoding used for OMI orbit naming and socket references. May respond only after frame validation.

**BiDi** — Bidirectional interpretation. In OMI, the lawful dual reading of the same source forward and backward. Direction is interpretation.

**Binary Quadratic Meta-Mask Lexer** — The formal name for the Q_frame validator that checks envelope membership via the quadratic error function.

**Bitblip** — A small bit-level deviation from an expected mask. The fundamental unit of deviation in OMI — a single-bit transition in the rewrite surface.

**Bitblip policy** — Defines how bit-level deviations are handled: `accept-exact`, `correct-single`, `evict-single`, `correct-up-to-2`, `evict-over-2`, `warn-near-miss`, `drop-packet`, `skip-replay`, `route-preset-1`.

**Bitboard** — A fixed-width mask used to extract or compare rule-bearing fields from an OMI address.

**Boundary signature** — The canonical projection form: `o---o/---/?v=<base64url>;l=<length>;h=<hash>@<base36-ref>@`.

**Bridge equation** — `Q_xy(x,y) = 60x² + 16xy + 4y²`. The quadratic form that projects OMI coordinates to visual geometry.

---

## C

**C (carried closure)** — The constant in the Delta Law that prevents the zero fixed point. Default: C₀ = 0x5A3C.

**Canon** — The recorded cosmology. This repository. The written body of OMI doctrine, ontology, geometry, protocol, and projection.

**Carrier** — The physical surface that carries an OMI frame (IPv6 packet, LoRa radio frame, file, etc.). Carrier is not authority.

**Cayley-Dickson doubling** — The process that lowers `.omi` source to `.imo` bytecode through mirror construction.

**Chiral entry** — The small omicron (ο, U+03BF) anchor that marks the entry boundary of an OMI frame.

**Chirality** — Orientation handedness. Forward orbit = left-handed, reverse orbit = right-handed. Chirality is not disagreement — it is oriented complementarity.

**CIDR** — Classless Inter-Domain Routing. Used in OMI as the address scope operator (`/prefix`).

**Cipher** — In OMI: a declaration of interpretation. "Notation as cipher, cipher as notation." Not secrecy — interpretation.

**Closure** — The projective center of a bounded wheel. The missing state that makes the surface closed rather than linear. See `03-MANIFESTO.md` §9.

**CLOSURES.omi** — The truth gate that seals accepted forms with the CLOSE keyword.

**COMBINATORS.omi** — The truth gate that composes lawful operations with the COMBINE keyword.

**Complement** — The ones-complement anti-surface: `S' = S XOR 0xFFFF` (per segment) or `P' = P XOR all_ones` (per address).

**Conformance** — Faithfully implementing the required acceptance pipeline: anchor check, Q_frame validation, truth row extraction, Delta/Fano resolution, 64-bit receipt, 5040-slot ring, projection boundary.

**CONS.omi** — The truth gate that reduces structures into executable cons surfaces with the CONS keyword.

**Consequent (MM)** — The final state in a truth row `(LL, NN, MM)`. The output of the Delta Law resolver.

**Cons cell** — `Ο(<car>, <cdr>)`. The minimal OMI object. A bounded relation between entry and exit.

**Control codes** — ASCII range 0x00–0x1F. In OMI, rewrite operators, not non-printing characters.

**Cosmology** — The framework within which OMI makes sense. A first-principles reconstruction of computation from position, relation, boundary, and replay.

---

## D

**Database** — What OMI is not. A database asks "what value is stored here?" OMI asks "what lawful transformation is declared here?"

**Declaration envelope** — The 10! = 3.6M envelope containing ten declaration positions: POSTULATE, AXIOM, RULE, FACT, DECLARATION, TEST, REPLAY, PROJECTION, FAILURE, COMPLEMENT.

**Delta Law** — `Δ_C(x) = rotl(x,1) ⊕ rotl(x,3) ⊕ rotr(x,2) ⊕ C`. The core bitwise transition law. Period: 8. Fano bound: max 15 steps.

**Doctrine** — The invariant laws of OMI. The collapse of representation and interpretation. "The reader may recognize. The resolver may promote. Only validation and receipt may accept."

**DOM projection** — The six DOM handles: `id`, `data-omi`, `data-imo`, `<o>`, `<omi>`, `<imo>`.

---

## E

**Ecosystem** — The open world of agents, hardware, networking, and implementation surfaces surrounding the OMI canon.

**Empty cons** — `()! = ()`. The zero-frame. The place where structure can be addressed, evaluated, and replayed. Both a point and a space.

**Envelope** — The 512-bit transmission unit containing OMI frames plus structural metadata.

**eBPF gate** — A kernel-level XDP program that validates OMI frames before the kernel stack touches them. Gate 1: Q_frame. Gate 2: Delta/Fano.

---

## F

**FACTS.omi** — The truth gate that grounds observed or configured state with the FACT keyword.

**Factorial tower** — The resolution climb from 5! (120) to 12! (479M). Each layer is an interpretive envelope derived from the immutable 128-bit frame.

**Fano bound** — The maximum number of steps for Delta Law convergence: max 15 = 2 × period − 1.

**Fano lottery** — The non-deterministic selection of Fano point during Delta resolution. The point emerges from the walk.

**Fano plane** — The smallest finite projective plane (7 points, 7 lines, 3 points/line). In OMI: 7 replay slots in the 5040 ring, 7 Fano points each carrying a complete S-P-O sweep.

**Five-fold** — The 5! = 120 packet root / 5-cell simplex core. Five semantic cells: subject, predicate, object, context, closure.

**Fold** — A legal transformation over an OMI surface. Reflects, aligns, complements, or resolves. See `04-FOUNDATIONS.md` §7.

**Four-fold** — The 4! = 24 selector surface. Four gauges: FS, GS, RS, US.

**Frame** — A 128-bit instruction frame: 8 segments × 16 bits. The immutable physical surface of OMI computation.

---

## G

**Gate** — The blind validator: parses frame, validates, extracts truth row, resolves Delta, derives slot, writes receipt, emits envelope. Knows nothing of geometry, DOM, or application semantics.

**Gauge** — The four carrier surfaces: `o---o` (FS/object), `/---/` (GS/path), `?---?` (RS/query), `@---@` (US/socket).

**Gauge table** — A 128-entry registry mapping opcodes to execution semantics. Each entry is a lambda-like structure with car, cdr, payload, and symbolic stack.

**Genesis frame** — `0100-03bf-7c00-2b01-2f01-1434-039f-01ff`. The canonical boot frame. Q(S)=0, converges in 1 step, anchors to ring slot 1504.

---

## H

**Hidden five** — Factor 5 appears explicitly only in 5! = 120. Every layer above carries it implicitly inside 240. The digit 5 never appears in the decimal expansion of 1/73.

**Horn clause** — A logical clause used in OMI address path derivation. Each slash segment is a clause selector.

---

## I

**.imo** — The compiled mirror format (`.imo`). The result of lowering `.omi` source through Cayley-Dickson doubling. Wrapped with ο/Ο delimiters.

**ISA** — The 32-slot instruction set architecture. 20 core ops + 12 extended ops. Four semantic lenses (LOCAL VM, REMOTE VM, USER LAYER, HW BRIDGE).

**Interpretation** — The active reading of a binary source. In OMI, interpretation IS computation. The source remains; the reading changes.

---

## J

**JSDOM** — JavaScript DOM emulation. In OMI, a projection surface that can manipulate structure without mutating OMI truth.

---

## K

**Kernel gate** — See **eBPF gate**.

**Ket selector (LL)** — The scope/lens selector from S₀. High nibble = context/family, low nibble = execution slot.

---

## L

**LL** — See **ket selector**.

**Light Garden** — The physical transducer profile for Omi-Sense. Defines how light signals are interpreted as OMI frames.

**LoRa** — Long Range radio. The original physical transport target for OMI (ESP32-S3 + SX1262, 915 MHz ISM band).

**Logos** — "The Word" in John 1:1. Read by OMI as primordial notation — the original collapse of representation and interpretation.

---

## M

**MANIFESTO.md** — The philosophical lens of OMI. "Notation as cipher. Cipher as notation."

**Materializer** — Applies an accepted rule address to affect object structure, document projection, DOM/CSSOM/JSDOM state.

**Meta-circular compiler** — A compiler that can compile its own source code. Proves OMI is self-describing.

**Mirror** — The `.imo` compiled form of a truth gate. The backward reflection.

**MM** — See **consequent**.

---

## N

**NN** — See **antecedent**.

**Nomogram** — The runtime scale selector (Omi-Nomogram). 16 scales mapping 0x30–0x3F.

**Notation as cipher** — The central OMI claim: notation declares interpretation. Cipher is not secrecy — it is interpretation.

---

## O

**o---o** — The object carrier boundary (FS gauge). Also used as the abstract protocol surface (this repository).

**Observer in the void** — The primordial computational context from Genesis 1:2. Undefined state plus observer before interpretation.

**Omi-Nomogram** — See **Nomogram**.

**Omi-Ring** — The atomic waveform enclosure of `omi---imo`. The addressed palindromic notation witness. Distinguished from a receipt.

**omi---imo** — The universal palindromic mnemonic notation. `omi` (entry) mirrored across three hyphens into `imo` (exit). The fundamental identity.

**.omi** — The forward declaration format (`.omi`). Source form for truth gates.

**Omicron** — The observer-origin marker. Distinguished from zero. Small omicron (ο, U+03BF) = chiral entry. Capital omicron (Ο, U+039F) = cardinal exit.

**Omicron anchor** — `0x03BF` and `0x039F`. The structural frame boundaries that enable constant-time frame detection.

**Ontology** — What exists in the OMI cosmology. The address, the truth gates, the mirrors, the resolution lineage.

**Open world** — The default assumption: any declaration, any gossip, any render can enter the system as a candidate. The system post-validates rather than pre-filters.

---

## P

**Palindrome** — `omi---imo`. The identity surface. Read the same forward and backward.

**PG(4,2)** — 5-dimensional projective space over GF(2). 31 points, 155 lines. Connected to trigintaduonion multiplication table.

**Portal** — A projection surface that displays accepted OMI objects without being the authority. "One object. Many portals."

**Postulate** — A permitted construction in OMI. Euclid-inspired: defines what may be drawn, extended, connected, projected, derived, or grounded.

**Probe** — The self-describing handshake protocol: IDLE → PROBE_SENT → PROBE_RECEIVED → NEGOTIATING → SYNCED → ACTIVE.

**Projection** — The visible surface of accepted truth. Projection is not authority. Projection is always downstream of validation and receipt.

**Projective closure** — The principle that every bounded wheel has a closure state (projective center) in addition to its active states.

**Protocol** — The wire format: 128-bit frame, 512-bit envelope, 64-bit receipt, 5040-slot ring, eBPF gates, probe handshake.

**Provider contract** — "No address without a rule. No rule without a test. No test without a replay path. No replay path without visible state."

---

## Q

**Q_frame(S)** — The quadratic error function that validates frame membership: `Q_frame(S) = E_var + E_const`. Must equal 0.

**Q_xy(x,y)** — The bridge equation: `60x² + 16xy + 4y²`. Projects OMI coordinates to visual geometry.

**Quadratic Law** — The family of quadratic forms (Q_frame, Q_xy) that govern frame validity and spatial projection.

---

## R

**Radio VM** — The OMI instruction set executed over radio frequency (LoRa). Same ISA, different transport.

**Receipt** — A 64-bit record of acceptance: `provenance:16 | steps:8 | LL:8 | NN:16 | MM:16`. Written only after validation and resolution.

**Registry** — The component that owns meaning: reads the accepted envelope, looks up the rule slot, applies the implementation, projects and explains the result.

**Replay ring** — The 7! = 5040 slot circular buffer that stores receipts. Decomposes as `fano7 × 720 + role3 × 240 + local240`.

**Resolution lineage** — The factorial tower from 5! to 12!. The claim: the 128-bit frame is immutable; higher layers are interpretive envelopes derived from it.

**Rewrite register** — What OMI is. A system that asks "what lawful transformation is declared here?" rather than "what value is stored here?"

**Rewrite surface** — A binary source viewed through an active notation. The same source, different readings.

**Ring cursor** — The current position in the 5040-slot replay ring. Advances by `steps` modulo 5040.

**Rotation** — OMI does not shift; OMI rotates. A shift loses information. A rotation preserves it. The Delta Law is a rotation.

**RULES.omi** — The truth gate that declares obligations and invariants with the MUST keyword.

---

## S

**S₀–S₇** — The eight 16-bit segments of an OMI frame.

**Sexagesimal** — Base-60. The runtime cadence of OMI. Steps 0–59. Derived from Hellenistic Greek astronomical notation.

**Slash path** — `/---/`. The interpretation routing path appended to the palindrome identity. Not storage — declaration.

**Slot 5040** — `fano7 × 720 + role3 × 240 + local240`. The canonical slot formula for the replay ring.

**Snub** — The primary geometric operation. Snub rotates faces (vs. truncation which cuts corners). Produces chiral pairs.

**State** — A numbered phase in the OMI journey. 00 (The Void) through 10 (The Closure). Each state is a directory in this repository.

---

## T

**Third Collapse** — OMI's position alongside Lisp (program/object) and POSIX (storage/communication) as the collapse of representation/interpretation.

**Truth gate** — One of five declarative files: `RULES.omi`, `FACTS.omi`, `CLOSURES.omi`, `COMBINATORS.omi`, `CONS.omi`.

**Truth row** — The triple `(LL, NN, MM)` extracted from every valid frame. LL = scope selector, NN = antecedent, MM = consequent.

**240 bridge** — The identity `2 × 5! = 15 × 16 = 240`. Where the five-fold packet root meets the four-fold selector surface.

---

## U

**Upper Bidi** — The projection layer (CSSOM, DOM, SVG, direction, `unicode-bidi`). Lower Omicron validates, Upper Bidi reads.

---

## V

**Validation** — The check `Q_frame(S) = 0`. The sole structural admission predicate.

**Void** — State 00. The beginning. The observer in the void before interpretation.

---

## W

**Witness envelope** — The 11! = 39.9M envelope. Carries the proof trail through the protocol stack.

**Wormhole portal** — A projection surface that connects two OMI addresses across different contexts without merging them.

---

## Z

**Zero** — Arithmetic additive identity. Distinguished from omicron.

**Zero-frame** — `()! = ()`. The empty cons. Not nothing — the observer-origin.

**0xE_ manifold** — The 0xE0–0xEF band. The single accepted execution manifold. Inner materializers (0xE0–0xEB) and outer controller vertices (0xEC–0xEF).

---

## Final Note

This glossary closes the circle. Every term used in the canon is defined here. Terms that appear in the canon but are not defined here are either:

1. Standard mathematical terms (used in their conventional sense)
2. Terms defined inline in their respective state documents
3. Terms from external references (which are noted as such)

The canon begins at 00-ORIGIN.md and ends here at 10-GLOSSARY.md. The reader who follows the numbered progression will encounter every term in its natural context before reaching its formal definition here.

---

**End of the Canon.**
