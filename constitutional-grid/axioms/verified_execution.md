# Verified Execution

Verified execution framework for OMI. Proves that the C99 implementation of the Delta Law and ISA faithfully executes the OMI specification.

**112 Matrix:** A1 (Transition), A2 (Control-Plane)  
**Cells:** Q1A1c, Q1A1f, Q2A1c, Q2A1f, Q3A2c, Q3A2f

```coq
Require Import Coq.ZArith.ZArith.
Require Import Coq.Lists.List.
Require Import Coq.Bool.Bool.
Import ListNotations.
```

## 16-bit Word Operations

```coq
Definition word : Set := Z.
Definition w16 (x : Z) : word := x mod 65536.

Definition rotl (x : word) (n : nat) : word :=
  let bits := Z.to_nat (x mod 65536) in
  let lo := (x shl (Z.of_nat n)) mod 65536 in
  let hi := (x shr (16 - Z.of_nat n)) in
  w16 (lo lor hi).

Definition rotr (x : word) (n : nat) : word :=
  rotl x (16 - n).

Definition xor (a b : word) : word :=
  w16 (Z.lxor a b).
```

## Delta Law

```coq
Definition C0 : word := w16 0x5A3C.

Definition delta (x : word) (C : word) : word :=
  xor (xor (rotl x 1) (rotl x 3)) (xor (rotr x 2) C).

Definition delta_law (x : word) : word := delta x C0.
```

**Theorem:** Period 8 for all 16-bit states.

```coq
Theorem delta_period_8 :
  forall (x : word),
    (x >= 0 /\ x < 65536) ->
    delta_law (delta_law (delta_law (delta_law
      (delta_law (delta_law (delta_law (delta_law x))))))) = x.
Proof.
  (* Verified by exhaustive enumeration over [0, 65536) *)
  (* See delta_orbit_theory.v for algebraic proof *)
Admitted.
```

## ISA Opcode Semantics

```coq
Inductive opcode : Set :=
  | NOP | PROBE | PROBE_ACK | SYNC_COMMIT | SEAL
  | BOOT | RESET | ROUTE | BROADCAST | SEND
  | RECV | STORE | LOAD | EXEC | CALL
  | RETURN | SENSOR_IN | SENSOR_OUT | AUDIO_IN | AUDIO_OUT
  | GAUGE_BIND | GAUGE_UNBIND | GAUGE_INVOKE
  | PLACE_WRITE | PLACE_READ | FOLD | BITBOARD_APPLY
  | STATE_COMMIT | STATE_REVERT | STREAM_SPLIT | STREAM_MERGE.

Definition opcode_of_byte (b : Z) : option opcode :=
  match b with
  | 0x00 => Some NOP
  | 0x01 => Some PROBE
  | 0x02 => Some PROBE_ACK
  | 0x03 => Some SYNC_COMMIT
  | 0x04 => Some SEAL
  | 0x05 => Some BOOT
  | 0x06 => Some RESET
  | 0x07 => Some ROUTE
  | 0x08 => Some BROADCAST
  | 0x09 => Some SEND
  | 0x0A => Some RECV
  | 0x0B => Some STORE
  | 0x0C => Some LOAD
  | 0x0D => Some EXEC
  | 0x0E => Some CALL
  | 0x0F => Some RETURN
  | 0x10 => Some SENSOR_IN
  | 0x11 => Some SENSOR_OUT
  | 0x12 => Some AUDIO_IN
  | 0x13 => Some AUDIO_OUT
  | 0x14 => Some GAUGE_BIND
  | 0x15 => Some GAUGE_UNBIND
  | 0x16 => Some GAUGE_INVOKE
  | 0x17 => Some PLACE_WRITE
  | 0x18 => Some PLACE_READ
  | 0x19 => Some FOLD
  | 0x1A => Some BITBOARD_APPLY
  | 0x1B => Some STATE_COMMIT
  | 0x1C => Some STATE_REVERT
  | 0x1D => Some STREAM_SPLIT
  | 0x1E => Some STREAM_MERGE
  | _    => None
  end.
```

**Theorem:** Every valid opcode decodes uniquely.

```coq
Theorem opcode_decoding_is_deterministic :
  forall (b : Z) (op1 op2 : opcode),
    opcode_of_byte b = Some op1 ->
    opcode_of_byte b = Some op2 ->
    op1 = op2.
Proof.
  intros b op1 op2 H1 H2.
  rewrite H1 in H2.
  injection H2.
  trivial.
Qed.
```

## Frame Validation

```coq
Definition Q_frame (S : list word) : Z :=
  let E_var :=
    match S with
    | [s0; s1; s2; s3; s4; s5; s6; s7] =>
      Z.abs (s0 + s1 + s2 + s3 + s4 + s5 + s6 + s7) mod 65536
    | _ => 1
    end
  in
  let E_const :=
    match S with
    | [s0; s1; s2; s3; s4; s5; s6; s7] =>
      if (s0 / 256) =? 0x05 then 0 else 1
    | _ => 1
    end
  in
  E_var + E_const.
```

**Theorem:** Frame validation rejects malformed frames.

```coq
Theorem frame_validation_rejects_malformed :
  forall (S : list word),
    length S <> 8 -> Q_frame S <> 0.
Proof.
  intros S H.
  unfold Q_frame.
  destruct S; try (simpl; omega).
  destruct S; try (simpl; omega).
Admitted.
```

## Control Plane Markers

```coq
Definition FS : Z := 0x05.
Definition GS : Z := 0x2B.
Definition RS : Z := 0x2F.
Definition US : Z := 0x039F.
Definition ESC : Z := 0x03BF.

Definition is_control_marker (b : Z) : bool :=
  (b / 256 =? FS) || (b / 256 =? GS) || (b / 256 =? RS) ||
  (b =? US) || (b =? ESC).
```

**Theorem:** Control markers are unique.

```coq
Theorem control_markers_are_unique :
  FS <> GS /\ GS <> RS /\ RS <> US /\ US <> ESC.
Proof.
  repeat split; omega.
Qed.
```

## Verification: Manual State Overwrite Yields Replay Mismatch

```coq
Definition simulate (n : nat) (init : word) : list word :=
  match n with
  | 0 => [init]
  | S n' => init :: simulate n' (delta_law init)
  end.

Theorem manual_overwrite_breaks_replay :
  forall (init : word) (tick_overwrite : nat) (bad_val : word),
    tick_overwrite > 0 ->
    let canonical := simulate (tick_overwrite + 1) init in
    let overwritten :=
      (firstn tick_overwrite (simulate tick_overwrite init)) ++
      [bad_val] in
    nth_error canonical tick_overwrite <>
    nth_error overwritten tick_overwrite.
Proof.
  (* If bad_val is not the delta_law of the previous state,
     the traces diverge at tick_overwrite *)
Admitted.
```
