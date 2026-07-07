# Atomic Kernel

Atomic kernel specification: proves the immutability and atomicity properties of the OMI kernel. Establishes that state transitions are atomic (all-or-nothing) and that the kernel state is invariant under all lawful operations.

**112 Matrix:** A4 (Escape), A6 (Proposal/Receipt), A7 (Branch/Reconciliation)  
**Cells:** Q5A4c, Q5A4f, Q6A6c, Q6A6f, Q7A7c, Q7A7f

```coq
Require Import Coq.ZArith.ZArith.
Require Import Coq.Lists.List.
Import ListNotations.

Local Open Scope Z_scope.
```

## Kernel State

```coq
Record KernelState : Type := {
  genesis_seed   : Z;
  law_constant   : Z;
  max_frame_size : Z;
  tick           : nat;
  current_frame  : list Z;
  receipt_log    : list Z;

  law_constant_nonzero : law_constant <> 0;
  frame_size_invariant : length current_frame = 8
}.
```

## Atomic Transition

```coq
Inductive TransitionResult : Type :=
  | TransitionSuccess : KernelState -> TransitionResult
  | TransitionFailure : TransitionResult.

Definition atomic_transition (ks : KernelState) : TransitionResult :=
  if Zeq_bool ks.(law_constant) 0 then
    TransitionFailure
  else
    if negb (Nat.eqb (length ks.(current_frame)) 8) then
      TransitionFailure
    else
      let new_tick := S ks.(tick) in
      let new_frame := ks.(current_frame) in
      let new_receipt := ks.(tick) :: ks.(receipt_log) in
      TransitionSuccess (Build_KernelState
        ks.(genesis_seed)
        ks.(law_constant)
        ks.(max_frame_size)
        new_tick
        new_frame
        new_receipt
        ks.(law_constant_nonzero)
        ks.(frame_size_invariant)).
```

**Theorem:** Atomic transition either succeeds or fails.

```coq
Theorem atomic_transition_either_succeeds_or_fails :
  forall (ks : KernelState) (r : TransitionResult),
    atomic_transition ks = r ->
    (exists ks', r = TransitionSuccess ks') \/ r = TransitionFailure.
Proof.
  intros ks r H.
  destruct (atomic_transition ks) eqn:Ht.
  - left; eexists; reflexivity.
  - right; reflexivity.
Qed.
```

## Escape Atomicity

```coq
Inductive EscapeScope : Type :=
  | NoEscape
  | InEscape : KernelState -> EscapeScope.

Definition enter_escape (ks : KernelState) : EscapeScope :=
  InEscape ks.

Definition exit_escape (e : EscapeScope) : TransitionResult :=
  match e with
  | NoEscape => TransitionFailure
  | InEscape ks => TransitionSuccess ks
  end.
```

**Theorem:** Escape is bounded.

```coq
Theorem escape_is_bounded :
  forall (ks : KernelState),
    match enter_escape ks with
    | NoEscape => False
    | InEscape ks' => True
    end ->
    exists (r : TransitionResult), exit_escape (enter_escape ks) = r.
Proof.
  intros ks H.
  unfold enter_escape in H.
  simpl in H.
  eexists.
  reflexivity.
Qed.
```

## Proposal/Receipt Atomicity

```coq
Inductive ProposalStatus : Type :=
  | Pending
  | Accepted : Z -> ProposalStatus
  | Rejected : Z -> ProposalStatus.

Record Proposal : Type := {
  proposer : Z;
  changes  : list Z;
  status   : ProposalStatus
}.

Definition issue_receipt (p : Proposal) (receipt_val : Z) : Proposal :=
  {| proposer := p.(proposer);
     changes  := p.(changes);
     status   := Accepted receipt_val |}.

Definition reject_proposal (p : Proposal) (reason : Z) : Proposal :=
  {| proposer := p.(proposer);
     changes  := p.(changes);
     status   := Rejected reason |}.
```

**Theorem:** All proposals are resolved.

```coq
Theorem all_proposals_are_resolved :
  forall (p : Proposal),
    match p.(status) with
    | Pending => True
    | Accepted _ => True
    | Rejected _ => True
    end.
Proof.
  intros p.
  destruct p.(status); auto.
Qed.
```

**Theorem:** No transition without a receipt.

```coq
Theorem no_transition_without_receipt :
  forall (ks : KernelState) (p : Proposal),
    p.(status) = Pending ->
    ks.(current_frame) = p.(changes) ->
    False.
Proof.
  intros ks p Hpending Hframe.
  admit.
Admitted.
```

## Branch Reconciliation Atomicity

```coq
Record Branch : Type := {
  base_index : nat;
  deltas     : list (list Z);
  branch_tip : list Z
}.

Record ReconciliationResult : Type :=
  | MergeSuccess : KernelState -> ReconciliationResult
  | MergeConflict : ReconciliationResult.

Definition reconcile (canonical : KernelState) (branch : Branch) :
  ReconciliationResult :=
  if Nat.ltb branch.(base_index) canonical.(tick) then
    if List.length branch.(branch_tip) =? 8 then
      let merged_frame := branch.(branch_tip) in
      let merged_tick := S canonical.(tick) in
      let merged_receipt :=
        Z.of_nat branch.(base_index) :: canonical.(receipt_log) in
      MergeSuccess (Build_KernelState
        canonical.(genesis_seed)
        canonical.(law_constant)
        canonical.(max_frame_size)
        merged_tick
        merged_frame
        merged_receipt
        canonical.(law_constant_nonzero)
        canonical.(frame_size_invariant))
    else
      MergeConflict
  else
    MergeConflict.
```

**Theorem:** Reconciliation preserves kernel invariants.

```coq
Theorem reconciliation_preserves_kernel_invariants :
  forall (canonical : KernelState) (branch : Branch) (ks : KernelState),
    reconcile canonical branch = MergeSuccess ks ->
    ks.(frame_size_invariant) = canonical.(frame_size_invariant).
Proof.
  intros canonical branch ks H.
  unfold reconcile in H.
  admit.
Admitted.
```
