# State 14 — Wave Surface Interpreter: Analog Disturbance

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

> The wave surface interpreter does not measure the world. It classifies waveforms as candidates for relation. The world enters OMI not as truth, but as addressable disturbance.
