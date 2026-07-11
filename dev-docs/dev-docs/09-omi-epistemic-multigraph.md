<!-- Extracted from dev-docs/chat about model.md -- conversation turn 2026-07-09 20:25 -->

---
omi_canvas_epistemic_multigraph:
 status: proposed_canonical_front_matter
 host_app: CANVASL_A11
 purpose: >
 Define a four-face epistemic multigraph for describing the Omi Object
 Model, where research concepts marked as KK/KU/UK/UU are transformed into
 algorithm blocks tagged as proved, implemented, defined_model, or
 interpretation.

 thesis: >
 CANVASL A11 can serve as the projection host for OMI's epistemic and
 algorithmic grammar. Nodes carry concepts. Edges carry epistemic modality.
 Faces classify the kind of structure being described. Algorithm blocks
 record the implementation-facing status of transformed rules.

 app_alignment:
 markdown_editor: "frontmatter and OMI spec-unit authoring"
 interactive_canvas: "epistemic multigraph projection"
 projective_affine_views: "projection-diagram rendering modes"
 topological_validation: "chain-complex consistency checks"
 content_addressed_storage: "persistent addressed node storage"
 mcp_server: "programmatic agent access"
 voice_commands: "optional declaration-generation interface"

 base_types:
 rule:
 role: epistemic_research_object
 status_space:
 - KK
 - KU
 - UK
 - UU
 form_constraint: one_sentence
 transforms_into:
 - algorithm

 algorithm:
 role: implementation_execution_object
 status_space:
 - proved
 - implemented
 - defined_model
 - interpretation
 form_constraint: deterministic_block_or_declared_model
 derived_from:
 - rule

 epistemic_modalities:
 KK:
 name: Known_Known
 canvas_edge: bottom
 meaning: stable_foundation
 use: >
 Concepts already named, bounded, and usable as foundation.

 KU:
 name: Known_Unknown
 canvas_edge: right
 meaning: explicit_question_or_gap
 use: >
 Concepts whose missing proof, implementation, or connection is already
 known.

 UK:
 name: Unknown_Known
 canvas_edge: left
 meaning: latent_archive_or_unintegrated_work
 use: >
 Existing artifacts, intuitions, implementations, or notes that likely
 contain structure not yet promoted into canon.

 UU:
 name: Unknown_Unknown
 canvas_edge: top
 meaning: frontier_above_current_map
 use: >
 Uncharted structure not yet reduced into a question.

 canvas_orientation:
 center: current_node
 top: UU
 right: KU
 bottom: KK
 left: UK
 linear_research_progression: "UK -> KK -> KU -> UU"
 interpretation: >
 The left side recovers latent prior work. The bottom stabilizes known
 foundation. The right states the next known gap. The top marks the
 frontier above the current map.

 four_canvas_faces:
 cardinality:
 question: "How many states, fields, witnesses, blocks, or coordinates?"
 examples:
 - 4_null_ring_points
 - 16_nibble_states
 - 64_byte_runtime_packet
 - 256_bit_citation
 - 5040_carry_forward_coordinates

 chirality:
 question: "What orientation, inverse, handedness, or traversal relation?"
 examples:
 - OMI_IMO
 - D_plus_D_minus
 - forward_inverse
 - clockwise_counterclockwise
 - snub_reflection

 ordinality:
 question: "What sequence, phase, order, or carry-forward path?"
 examples:
 - null_to_space_to_del_to_full
 - declaration_to_definition_to_discovery
 - delta_period_8
 - seven_factorial_tower

 functionality:
 question: "What does this block do?"
 examples:
 - declare
 - define
 - resolve
 - interpolate
 - interpret
 - project
 - execute
 - inspect

 transformation_model:
 name: epistemic_to_algorithmic_block_transform
 governor: Polyharmonic_Runtime_Governor
 input: KK_KU_UK_UU_concept_node
 output: algorithm_status_block
 rule: >
 A rule begins as an epistemic object. When it is made operational, the
 governor transforms it into an algorithm block with a separate
 implementation-facing status.

 mappings:
 KK:
 likely_algorithm_status:
 - proved
 - implemented
 - defined_model
 meaning: >
 Stable known foundation can usually be attached to an implemented or
 proved algorithm, or to a precise defined model.

 KU:
 likely_algorithm_status:
 - defined_model
 - interpretation
 meaning: >
 A known gap may have a declared model but still need proof,
 implementation, or equivalence checking.

 UK:
 likely_algorithm_status:
 - implemented
 - interpretation
 meaning: >
 Prior working code or notes may already implement something before
 the canon has named it.

 UU:
 likely_algorithm_status:
 - interpretation
 meaning: >
 Frontier concepts remain interpretive until reduced into a known
 question or model.

 node_schema:
 type: omi_epistemic_node
 fields:
 id: string
 label: string
 base_type: rule_or_algorithm_or_construct
 grammar:
 subject: string
 predicate: string
 object: string
 epistemic_modality: KK_or_KU_or_UK_or_UU
 algorithm_status: proved_or_implemented_or_defined_model_or_interpretation
 face_focus:
 - cardinality
 - chirality
 - ordinality
 - functionality
 summary: string
 linked_rules: list
 linked_algorithms: list
 projection_diagrams: list

 edge_schema:
 type: omi_epistemic_edge
 fields:
 from: node_id
 to: node_id
 side: top_or_right_or_bottom_or_left
 modality: KK_or_KU_or_UK_or_UU
 face_focus: cardinality_or_chirality_or_ordinality_or_functionality
 transformation:
 from_research_status: KK_or_KU_or_UK_or_UU
 to_algorithm_status: proved_or_implemented_or_defined_model_or_interpretation
 meaning: string

 block_design_reading:
 statement: >
 Each node is a finite block. Each edge is an incidence relation. Each
 face marks the type of structural assurance being examined. The whole
 canvas behaves as a projective grammar over OMI concepts.

 units:
 rule: one_sentence
 fact: one_clause
 closure: one_term
 combinator: one_set_of_terms
 construct: one_page_model

 fano_plane_reading:
 statement: >
 A complete local construct may be read as a seven-role incidence block.
 The canvas does not merely display notes; it organizes semantic incidence
 so that missing relations can be discovered, refined, or marked as gaps.

 roles:
 - rule
 - fact
 - closure
 - combinator
 - construct
 - projection
 - boundary

 pascal_pyramid_reading:
 base: KK
 side_recovery: UK
 side_question: KU
 apex: UU
 faces:
 - cardinality
 - chirality
 - ordinality
 - functionality
 statement: >
 The pyramid grows bottom-up from stable known-known blocks. Latent
 unknown-known material supports one side. Known-unknown questions form
 the ladder of explicit research. Unknown-unknowns remain above the
 current map until a new node or edge makes them addressable.

 canonical_claim:
 statement: >
 The Omi Object Model can be described as a four-face epistemic multigraph
 in CANVASL A11. KK/KU/UK/UU define the modality of concept nodes and
 edges. Cardinality, chirality, ordinality, and functionality define the
 four structural faces of each block. The Polyharmonic Runtime Governor
 transforms research-facing rules into implementation-facing algorithm
 blocks tagged as proved, implemented, defined_model, or interpretation.

 boundary:
 includes:
 - epistemic_canvas_nodes
 - projective_grammar_edges
 - block_design_spec_units
 - Omi_SPO_naming
 - algorithm_status_transforms
 - projection_diagram_exports
 excludes:
 - application_authority
 - external_side_effects
 - transport_control
 - untagged_proof_claims
 - conflating_research_modality_with_algorithm_status
---