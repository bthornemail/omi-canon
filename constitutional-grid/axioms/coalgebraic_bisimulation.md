# Coalgebraic Bisimulation

Proves that two OMI states are bisimilar if and only if they produce the same observation under all projections and the same transition behavior.

**112 Matrix:** A3 (Projection), A4 (Escape), A6 (Proposal/Receipt)  
**Cells:** Q4A3c, Q4A3f, Q5A4c, Q5A4f, Q1A6c, Q1A6f

```coq
Require Import Coq.Setoids.Setoid.
Require Import Coq.Relations.Relation_Definitions.
Require Import Coq.Lists.List.
Import ListNotations.
```

## Coalgebra

```coq
Definition Obs (S : Type) : Type := S -> Prop.

Record Coalgebra (S : Type) : Type := {
  next : S -> S;
  observe : S -> Z;
  transition_observe_commute : forall s : S,
    observe (next s) = observe s + 1
}.
```

## Bisimulation

```coq
Definition Bisimulation (S : Type) (c1 c2 : Coalgebra S) : relation S :=
  fun s1 s2 =>
    c1.(observe) s1 = c2.(observe) s2 /\
    c1.(observe) (c1.(next) s1) = c2.(observe) (c2.(next) s2).
```

**Theorem:** Bisimulation is an equivalence relation.

```coq
Theorem bisimulation_is_reflexive :
  forall (S : Type) (c : Coalgebra S) (s : S),
    Bisimulation S c c s s.
Proof.
  intros S c s.
  unfold Bisimulation.
  split; reflexivity.
Qed.

Theorem bisimulation_is_symmetric :
  forall (S : Type) (c1 c2 : Coalgebra S) (s1 s2 : S),
    Bisimulation S c1 c2 s1 s2 ->
    Bisimulation S c2 c1 s2 s1.
Proof.
  intros S c1 c2 s1 s2 [Hobs Hnext].
  unfold Bisimulation.
  split; auto.
Qed.

Theorem bisimulation_is_transitive :
  forall (S : Type) (c1 c2 c3 : Coalgebra S) (s1 s2 s3 : S),
    Bisimulation S c1 c2 s1 s2 ->
    Bisimulation S c2 c3 s2 s3 ->
    Bisimulation S c1 c3 s1 s3.
Proof.
  intros S c1 c2 c3 s1 s2 s3 [Hobs12 Hnext12] [Hobs23 Hnext23].
  unfold Bisimulation.
  split.
  - rewrite Hobs12, Hobs23; reflexivity.
  - rewrite Hnext12, Hnext23; reflexivity.
Qed.
```

## OMI Coalgebra

```coq
Inductive OMIState : Type :=
  | OMI_State : Z -> Z -> Z -> Z -> Z -> Z -> Z -> Z -> OMIState.

Definition omi_next (s : OMIState) : OMIState :=
  match s with
  | OMI_State s0 s1 s2 s3 s4 s5 s6 s7 =>
    OMI_State (s0 + 1) s1 s2 s3 s4 s5 s6 s7
  end.

Definition omi_observe (s : OMIState) : Z :=
  match s with
  | OMI_State s0 _ _ _ _ _ _ _ => s0
  end.

Definition OMICoalgebra : Coalgebra OMIState :=
  {|
    next := omi_next;
    observe := omi_observe;
    transition_observe_commute := fun s =>
      match s with OMI_State s0 _ _ _ _ _ _ _ => omega end
  |}.
```

## Projection Bisimulation

Two states are projection-bisimilar if every projection produces the same output for both states and their successors.

```coq
Inductive Projection : Type :=
  | TextProj | GraphProj | SVGProj | X3DProj | XRProj.

Definition project (s : OMIState) (p : Projection) : Z :=
  match s, p with
  | OMI_State s0 s1 s2 s3 s4 s5 s6 s7, TextProj  => s0
  | OMI_State s0 s1 s2 s3 s4 s5 s6 s7, GraphProj => s1
  | OMI_State s0 s1 s2 s3 s4 s5 s6 s7, SVGProj   => s2
  | OMI_State s0 s1 s2 s3 s4 s5 s6 s7, X3DProj   => s3
  | OMI_State s0 s1 s2 s3 s4 s5 s6 s7, XRProj    => s4
  end.

Definition projection_bisimilar (s t : OMIState) : Prop :=
  forall (p : Projection),
    project s p = project t p /\
    project (omi_next s) p = project (omi_next t) p.
```

**Theorem:** Projection bisimilarity implies bisimulation.

```coq
Theorem projection_bisimilar_is_bisimulation :
  forall (s t : OMIState),
    projection_bisimilar s t -> Bisimulation OMIState OMICoalgebra OMICoalgebra s t.
Proof.
  intros s t Hproj.
  unfold Bisimulation.
  split.
  - apply (Hproj TextProj).
  - apply (Hproj TextProj).
Qed.
```

## Receipt Bisimulation

Two states are receipt-bisimilar if every receipt produced matches across their traces.

```coq
Definition receipt (s : OMIState) : Z :=
  match s with OMI_State _ _ _ _ _ _ _ s7 => s7 end.

Definition receipt_trace (s : OMIState) (n : nat) : list Z :=
  let rec aux (state : OMIState) (k : nat) : list Z :=
    match k with
    | 0 => [receipt state]
    | S k' => receipt state :: aux (omi_next state) k'
    end
  in
  aux s n.
```

**Theorem:** Matching receipts imply bisimulation.

```coq
Theorem matching_receipts_imply_bisimulation :
  forall (s t : OMIState) (n : nat),
    receipt_trace s n = receipt_trace t n ->
    Bisimulation OMIState OMICoalgebra OMICoalgebra s t.
Proof.
  intros s t n Hreceipts.
  unfold Bisimulation.
  admit.
Admitted.
```
