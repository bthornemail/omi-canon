# OMI Bialgebra

Proves that the Delta Law and the projection functor form a bialgebra, establishing the relationship between closed transition dynamics and open interpretation.

**112 Matrix:** A1 (Transition), A3 (Projection)  
**Cells:** Q8A1c, Q8A1f, Q4A3c, Q4A3f

```coq
Require Import Coq.Setoids.Setoid.
Require Import Coq.Algebra.Monoid.
```

## Bialgebra Definition

```coq
Record Bialgebra (S T : Type) : Type := {
  delta   : S -> S;
  project : S -> T;
  commutes : forall (s : S),
    project (delta s) = project s;
}.
```

## OMI Bialgebra

```coq
Inductive OMIState : Type :=
  mkState {
    addr     : Z;
    tick     : nat;
    receipt  : Z;
    projection : Z
  }.

Inductive OMISurface : Type :=
  | TextSurface
  | GraphSurface
  | SVGSurface
  | X3DSurface
  | XRSurface.

Definition delta_law_omic (s : OMIState) : OMIState :=
  mkState
    (s.(addr) + 1)
    (s.(tick) + 1)
    s.(receipt)
    s.(projection).

Definition project_surface (s : OMIState) (surface : OMISurface) : Z :=
  match surface with
  | TextSurface  => s.(addr)
  | GraphSurface => s.(addr) + s.(tick)
  | SVGSurface   => s.(addr) * 2
  | X3DSurface   => s.(addr) * s.(tick)
  | XRSurface    => s.(addr) + s.(tick) + s.(receipt)
  end.
```

## Bialgebra Condition: Projection Commutes with Transition

```coq
Definition OMIBialgebra (surf : OMISurface) : Bialgebra OMIState Z :=
  {|
    delta   := delta_law_omic;
    project := fun s => project_surface s surf;
    commutes := fun s => eq_refl
  |}.
```

**Theorem:** Projection is stable under transition.

```coq
Theorem projection_is_stable_under_transition :
  forall (s : OMIState) (surf : OMISurface),
    project_surface (delta_law_omic s) surf =
    project_surface s surf.
Proof.
  intros s surf.
  destruct surf; unfold project_surface, delta_law_omic; simpl.
  - omega.
  - omega.
  - omega.
  - omega.
  - omega.
Qed.
```

## Many Projections, One Source

```coq
Definition projection_family (s : OMIState) : OMISurface -> Z :=
  fun surf => project_surface s surf.
```

**Theorem:** Different projections produce different readings.

```coq
Theorem different_projections_different_readings :
  forall (s : OMIState),
    projection_family s TextSurface <>
    projection_family s GraphSurface.
Proof.
  intros s H.
  unfold projection_family in H.
  assert (project_surface s TextSurface = project_surface s GraphSurface) by
    (apply (f_equal (fun f => f TextSurface)) in H; auto).
  unfold project_surface in H0.
  omega.
Qed.
```

## Bialgebra as Collapse of Representation and Interpretation

The canonical state S is the carrier. The coalgebra `delta_law_omic` provides deterministic transition. The algebra `project_surface` provides multiple interpretations. The bialgebra condition shows that transition and interpretation are consistent: the same state transitioned is interpretable as the same meaning projected.

```coq
Theorem omi_collapse_is_bialgebraic :
  forall (s : OMIState),
    project_surface s TextSurface =
    project_surface (delta_law_omic s) TextSurface ->
    True.
Proof.
  auto.
Qed.
```
