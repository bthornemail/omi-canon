# State 15 — IMO Ports: External Nondeterminism

## What This State Is

This state is the transition from "how analog signals are classified" to "how the outside world enters the protocol." After the wave surface interpreter classifies physical disturbances into candidate Relations, IMO ports are the declared interfaces through which those candidates are admitted — or rejected.

An IMO port is not a network socket. It is a named boundary between the deterministic OMI protocol and the nondeterministic external world.

---

## The Port Contract

Every IMO port satisfies three obligations:

1. **Bounded interface**: The port accepts only one type of external signal (waveform, packet, file, interrupt). It does not accept general input.
2. **Classification before admission**: Every candidate Relation must pass through the wave surface interpreter (State 14) or an equivalent classification step before reaching the port.
3. **Receipt or rejection**: The port either accepts the candidate Relation with a receipt, or rejects it. There is no partial acceptance.

---

## Port Types

### Sensor Ports

Sensor ports admit classified analog signals:
- Audio (microphone, line-in)
- Electromagnetic (radio, LoRa, WiFi)
- Mechanical (accelerometer, gyroscope)
- Thermal (temperature probe)

Each sensor port is paired with a wave surface interpreter that classifies the sensor's output before presenting it to the port.

### Packet Ports

Packet ports admit structured digital signals:
- UDP / TCP frames
- LoRa packets
- BLE advertisements
- Serial bus messages

Packet ports do not classify — they parse. The structure of the packet determines which Relation fields it populates.

### File Ports

File ports admit persistent storage:
- BLOBs (binary large objects)
- GLOBs (graph large objects)
- Images
- Frame buffers

File ports map files to Relations by address rather than by content.

### Interrupt Ports

Interrupt ports admit temporal signals:
- Timer expiration
- GPIO voltage transition
- DMA completion
- Power state change

Interrupt ports produce Relations with zero payload — they mark that an event occurred at a specific address.

---

## Security Model

IMO ports do not trust their input. Every candidate Relation entering through a port must satisfy:

1. **Address validity**: The candidate's address must fall within a declared scope.
2. **Structural validity**: The candidate's Relation must be well-formed (all fields present, no structural errors).
3. **Gauge conformance**: The candidate's gauge word must select a known orientation.

A candidate that fails any check is rejected. No receipt is issued. The port records the rejection as a null Relation for audit.

---

## Doctrine Sentence

> IMO ports are the only source of nondeterminism in the OMI protocol. Everything else is deterministic replay from the atomic kernel through the surface application. The port is the boundary where the open world is admitted under bounded contract.
