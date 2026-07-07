# State 17 — Buffer Framing: Transport Carriers

## What This State Is

This state is the transition from "how external signals are admitted" to "how Relations are carried across boundaries." After IMO ports admit external candidates, buffer framing is how Relations are packaged for transport — across files, packets, images, memory buses, and hardware interfaces.

Buffer framing does not create Relations. It carries them. A framed Relation is the same Relation it was before framing — the frame is a transport envelope, not an interpretation.

---

## The Framing Principle

A buffer frame is a Relation plus a transport header:

```
BufferFrame = (CarrierType, Length, Relation)
```

The carrier type identifies the transport medium:
- FILE — byte stream on persistent storage
- PACKET — network datagram
- IMAGE — pixel buffer
- FRAME — hardware frame buffer
- BLOB — binary large object
- GLOB — graph large object
- STREAM — ordered sequence of Relations

The length is the number of bytes in the framed Relation. The Relation itself is byte-aligned and self-describing.

---

## Representation Neutrality

A buffer frame does not care what the payload is.

Whether the bytes represent OMI Relations, HTML markup, JSON data, JabCode barcodes, audio samples, or pixel values — the frame only guarantees that bytes enter and bytes leave in the same order.

```text
BufferFrame

does not inspect

the payload

It only transports

bytes → bytes
```

This is the **representation neutrality** principle: a buffer frame is a pipe, not an interpreter. Interpretation is the responsibility of the receiver's gauge (State 12) and projection faces (State 11). The frame carries; it does not read.

Separation from Projection:
- **Projection** (State 11) determines *how a Relation appears* to an observer
- **Buffer framing** (State 17) determines *how a Relation moves* between observers

A buffer frame is not a projection surface. It does not render, display, or interpret. It delivers a byte sequence from one location to another. The same buffer frame may carry an OMI envelope, a JPEG image, or an audio stream — the frame treats all payloads identically.

---

## Carrier Types

### BLOB — Binary Large Object

A BLOB is an opaque byte sequence. BLOBs carry Relations whose internal structure is not inspected during transport. The framing layer transports the bytes; interpretation belongs to the receiver.

BLOBs are the simplest carrier: write bytes, read bytes, no transformation.

### GLOB — Graph Large Object

A GLOB is a structured Relation sequence. Unlike BLOBs, GLOBs preserve the relational structure — each Relation in a GLOB is independently addressable.

GLOBs are used for batch transport of multiple Relations that share a common address prefix.

### Image Carriers

Relations may be projected onto pixel buffers for transport through image-capable media (displays, cameras, barcode scanners). The image carrier:

1. Projects the Relation onto a bitmap (via State 11 projection faces)
2. Encodes the bitmap as a pixel buffer
3. Transports the pixel buffer
4. Decodes the bitmap back to a Relation on receipt

Image carriers are lossy — the projection may not be reversible if the image resolution is insufficient.

### Frame Buffers

Frame buffers are hardware-level carriers for display hardware (HDMI, DisplayPort, LVDS). They transport Relations as rendered pixels at refresh rate.

Frame buffers are the only carrier type that is consumed by the transport — once the frame is displayed, the buffer is overwritten. Frame buffer transport does not guarantee reliable delivery.

---

## Transport Invariants

Buffer framing preserves three invariants:

1. **Relation identity**: A framed Relation, when unframed, produces the same Relation that was framed. (Image carriers excepted.)
2. **Address scope**: The Relation's address does not change during framing. Transport does not rewrite addresses.
3. **Receipt binding**: If the Relation carries a receipt, the receipt is transported with it. Transport does not strip receipts.

---

## Doctrine Sentence

> Buffer framing carries Relations across boundaries without interpreting them. Carriers move frames. Buffers hold frames. Validation determines state. Omi-Attestation witnesses. The frame is never the authority.
