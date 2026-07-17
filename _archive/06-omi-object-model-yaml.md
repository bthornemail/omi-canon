<!-- Extracted from dev-docs/chat about model.md -- conversation turn 2026-07-09 18:46 -->

---
omi_object_model:
 status: proposed_complete_model
 scope: canonical_object_model_front_matter
 purpose: >
 Define the Omi Object Model as a platform-agnostic,
 deterministic, address-as-identity model for declaring,
 defining, resolving, discovering, and projecting bounded
 semantic citation structures.

 completion_claim:
 claim: >
 The Omi Object Model is complete at the model-boundary level:
 it defines its substrate, runtime origin, declaration layer,
 definition layer, discovery/projection layer, and application
 exclusion boundary.
 excludes:
 - full implementation of every adapter
 - proof of every historical interpretation
 - ownership of general algorithmic execution logic
 - application behavior
 - transport-layer authority
 includes:
 - canonical naming grammar
 - bounded address identity
 - Omi-Lisp declarations
 - inverse/definition expressions
 - Omicron Null Byte Ring runtime origin
 - Polyharmonic Runtime Governor
 - Projection Diagrams
 - Omi-Canvas export surface
 - Haskell pure type model compatibility
 - a-list expression generation

 primary_axiom:
 statement: >
 Address is identity.
 consequences:
 - objects are addressed identities
 - updates construct new addressed identities
 - provenance is preserved by carry-forward
 - interpretation and interpolation operate over addresses
 - projection does not become application authority

 model_sequence:
 "-1_algorithmic_substrate":
 role: compiled_bounded_law
 description: >
 The algorithmic substrate sits below expression.
 It contains deterministic compiled bytecode or executable
 law surfaces used by the runtime.
 examples:
 - compiled_o_bytecode
 - delta_law
 - xor_closure
 - rotation_laws
 - finite_incidence_resolvers
 cardinality:
 type: fixed_or_bounded
 examples:
 - 16_bit_delta_frames
 - 64_bit_bitboards
 - 256_bit_citations
 - 512_bit_runtime_packet
 chirality:
 role: inverse_traversal_possible
 examples:
 - omi_imo_pairing
 - forward_inverse_witness
 ordinality:
 role: execution_order
 examples:
 - deterministic_replay
 - delta_step_sequence
 modality:
 mode: executable_substrate
 authority: computational_not_declarative

 "0_omicron_null_byte_ring":
 role: runtime_origin_operator
 description: >
 The Omicron Null Byte Ring is the runtime zero-point.
 It supplies closure, origin, readable boundary, seal,
 saturation, and inert projection capability.
 canonical_ring:
 - [0x00, 0x20]
 - [0x20, 0x7F]
 - [0x7F, 0xFF]
 - [0xFF, 0x00]
 closure_witnesses:
 - 0x20
 - 0x5F
 - 0x80
 - 0xFF
 closure_reduction: "0x20 XOR 0x5F XOR 0x80 XOR 0xFF = 0x00"
 projection_strength: impotent
 cardinality:
 byte_ring_points: 4
 byte_domain: 256
 chirality:
 role: closed_forward_inverse_cycle
 ordinality:
 role: null_to_space_to_del_to_full_to_null
 modality:
 mode: runtime_operator
 projection: inert_inspection_only

 "1_declaration":
 role: omi_lisp_declaration
 description: >
 Omi-Lisp declarations are embeddable environment references.
 They are dotfile-like only in the sense of hidden/native
 environmental presence, not literal file-extension authority.
 declares:
 - notation
 - names
 - rules
 - facts
 - closures
 - combinators
 - cons_like_constructs
 - projection_diagrams
 environment_behavior:
 attached: true
 native_reference: true
 application_authority: false
 cardinality:
 role: declared_frame_size
 examples:
 - 8_segment_frame
 - 16_pleth_citation
 - 32_axis_64_bit_word
 chirality:
 role: declaration_can_have_inverse_face
 ordinality:
 role: declaration_precedes_definition
 modality:
 mode: human_readable_declaration
 authority: declaration_only

 "2_definition":
 role: imo_inverse_definition
 description: >
 Definition binds declaration into attribution and attestation.
 The citation is defined as a bounded address identity, not as
 mutable application data.
 citation_model:
 total_width: 256_bits
 form: hexadecimal_note
 halves:
 attestation_by_declaration: 128_bits
 attribution_by_definition: 128_bits
 interpretation:
 declaration_answers: "who or what asserts the position"
 definition_answers: "what the position resolves as"
 cardinality:
 total: 256_bits
 pleths: "16 x 16-bit"
 halves: "2 x 128-bit"
 chirality:
 role: omi_forward_and_imo_inverse_definition
 ordinality:
 role: definition_after_declaration
 modality:
 mode: inverse_attribution
 authority: bounded_definition

 "3_discovery_projection":
 role: projection_diagram_discovery
 description: >
 Discovery occurs through interpolation and interpretation.
 The output is a Projection Diagram, not application behavior.
 mechanisms:
 - interpolation
 - interpretation
 - latin_square_resolver
 - quasigroup_like_recovery
 - steiner_triplet_checkpoint
 - polybius_gauge
 - blackboard_pattern_behavior
 projection_diagram:
 role: omi_lisp_declared_finite_state_relation_view
 may_render_to: omi_canvas
 may_generate:
 - a_list_expressions
 - bitboard_attachments
 - addressed_bit_blits
 - innocuous_projection
 - impotent_projection
 blackboard_pattern:
 status: behavioral_analogy
 architecture_claim: false
 meaning: >
 Independent resolvers may contribute partial annotations
 to a bounded shared context. This does not require OMI to
 be implemented as a Blackboard Architecture.
 cardinality:
 role: discovered_relation_space
 examples:
 - 7_factorial_5040_coordinate_ring
 - 15_active_states_plus_closure
 - 240_state_bridge
 chirality:
 role: traversal_orientation_and_inverse_projection
 ordinality:
 role: ordered_discovery_over_declared_frames
 modality:
 mode: projection_only
 allowed_strengths:
 - impotent
 - innocuous
 application_authority: false

 runtime_initialization_packet:
 width: 512_bits
 bytes: 64
 role: platform_agnostic_bootstrap_frame
 layout:
 gauge: 8_bytes
 orientation: 8_bytes
 recovery: 8_bytes
 target: 8_bytes
 relation: 32_bytes
 total: "8 + 8 + 8 + 8 + 32 = 64 bytes = 512 bits"
 purpose: >
 Bootstrap an Omi Object Model environmental runtime without
 binding the runtime to a specific platform, application, or
 transport.
 canonical_envelope:
 bytes:
 - 0xFF
 - 0x00
 - 0x1C
 - 0x1D
 - 0x1E
 - 0x1F
 - 0x20
 - 0xFF
 role: omnicron_resolver_envelope

 polyharmonic_runtime_governor:
 role: runtime_resolver
 description: >
 The Polyharmonic Runtime Governor adjudicates embeddable
 Omi-Lisp environment references against the current Omicron
 runtime frame.
 governs:
 - environment_embeddings
 - projection_diagrams
 - gauge_readiness
 - closure_witnesses
 - latin_square_or_quasigroup_resolver_fragments
 - polybius_diagonal_closure
 - null_ring_closure
 does_not_govern:
 - application_behavior
 - user_intent
 - external_network_policy
 - physical_transport
 relation_to_tetragrammatron:
 polyharmonic_tetragrammatron: "DSL + ABI boundary"
 governor: "runtime resolver and adjudicator"

 naming_grammar:
 convention: "Omi-<Predicate_or_Modality> <Object_or_Type>"
 interpretation:
 subject: "Omi canonical declaration space"
 predicate: "relation, constraint, modality, or behavioral pattern"
 object: "bounded semantic type or checkpoint"
 examples:
 - name: Omi-Blackboard Pattern
 subject: Omi
 predicate: Blackboard
 object: Pattern
 meaning: >
 Blackboard-like discovery behavior reduced into the OMI
 declaration space; not a full blackboard architecture.
 - name: Omi-Projection Diagram
 subject: Omi
 predicate: Projection
 object: Diagram
 meaning: >
 Declared finite-state relation view that may render through
 Omi-Canvas but does not become application authority.
 - name: Omi-Gnomic Gauge
 subject: Omi
 predicate: Gnomic
 object: Gauge
 meaning: >
 Identity-bearing gauge surface for innocuous projection.
 steiner_triplet_role:
 description: >
 Canonical names act as semantic checkpoints using
 subject-predicate-object structure.
 use:
 - boundary_mapping
 - constraint_mapping
 - connotation_control
 - mental_graph_navigation
 - coding_agent_orientation

 algebraic_resolvers:
 latin_square:
 role: reversible_finite_discovery_table
 law: "any two coordinates determine the third"
 omi_mapping:
 row: attestation
 column: attribution
 symbol: discovered_point
 quasigroup:
 role: algebraic_reading_of_latin_square_resolver
 requirement: reversible_lookup
 non_requirement: global_associativity
 steiner_triplet:
 role: semantic_checkpoint_and_incidence_completion
 use: "two known points may determine a third within a bounded incidence frame"
 moufang_loop_like_governor:
 role: lawful_reassociation_without_global_associativity
 mapped_to: Polyharmonic_Tetragrammatron_Governor

 polybius_gauge:
 role: local_4x4_projection_diagram
 nibble_field:
 rows:
 - [0x0, 0x1, 0x2, 0x3]
 - [0x4, 0x5, 0x6, 0x7]
 - [0x8, 0x9, 0xA, 0xB]
 - [0xC, 0xD, 0xE, 0xF]
 diagonals:
 d_plus: [0x0, 0x5, 0xA, 0xF]
 d_minus: [0x3, 0x6, 0x9, 0xC]
 witnesses:
 xor_d_plus: 0x00
 xor_d_minus: 0x00
 sum_d_plus: 0x1E
 sum_d_minus: 0x1E
 combined_diagonal_sum: 0x3C
 full_wheel_sum: 0x78
 active_byte_bridge: "15 * 16 = 240"

 projection_diagrams:
 role: omi_lisp_declared_views
 replaces_overstrong_terms:
 - surface_projection_as_primary
 - canvas_projection_as_canon_primary
 - blackboard_architecture
 may_render_on:
 - Omi-Canvas
 - DOM
 - SVG
 - terminal
 - bitboard_viewer
 - firmware_inspector
 strengths:
 impotent:
 meaning: inert_inspection_only
 application_force: none
 innocuous:
 meaning: informative_but_harmless
 application_force: none

 omi_canvas:
 status: implementation_export_surface
 current_model: Haskell_pure_type_model
 produces:
 - omi_lisp_a_list_expressions
 - projection_diagram_exports
 - meta_compiled_canvas_markdown
 role: >
 Omi-Canvas is an implementation/render/export surface for
 Projection Diagrams. It is not the authority layer.

 osi_layer_adaptations:
 model: declarative_extension
 governor: Polyharmonic_Runtime_Governor
 claim: >
 OMI can declare OSI-layer adaptations without replacing the
 OSI model or becoming a transport/application protocol.
 layers:
 7_application:
 omi_role: declare_adapter_not_application_behavior
 6_presentation:
 omi_role: notation_encoding_projection_diagrams
 5_session:
 omi_role: runtime_context_and_frame_continuity
 4_transport:
 omi_role: bounded_packet_framing
 3_network:
 omi_role: address_projection_and_identity_mapping
 2_data_link:
 omi_role: bitboard_attachments_and_frame_witnesses
 1_physical:
 omi_role: carrier_specific_encoding_outside_omi_authority

 categorical_group_delineation:
 required_axes:
 cardinality:
 question: "How many positions, states, fields, or witnesses?"
 examples:
 - 4_byte_ring_points
 - 16_nibble_values
 - 32_64_bit_axes
 - 240_state_bridge
 - 5040_carry_forward_coordinates
 - 512_bit_runtime_packet
 chirality:
 question: "What is the orientation, inverse, handedness, or traversal direction?"
 examples:
 - omi_imo
 - d_plus_d_minus
 - forward_inverse_pairing
 - snub_or_twisted_projection
 ordinality:
 question: "What is the sequence, order, phase, or carry-forward path?"
 examples:
 - delta_period_8
 - null_to_space_to_del_to_full
 - declaration_before_definition_before_discovery
 - seven_factorial_tower
 modality:
 question: "What mode of force or interpretation does this object carry?"
 examples:
 - executable
 - runtime_operator
 - declarative
 - definitional
 - interpretive
 - interpolative
 - impotent_projection
 - innocuous_projection

 application_boundary:
 statement: >
 Application is downstream from OMI.
 omi_stops_at:
 - declaration
 - definition
 - governed_discovery
 - projection_diagram
 - environment_reference
 omi_does_not_decide:
 - application_action
 - user_acceptance
 - external_side_effect
 - network_policy
 - physical_transport_behavior

 concise_canon:
 statement: >
 OMI is a deterministic address-as-identity object model.
 It begins below expression with compiled bounded algorithms,
 enters expression through the Omicron Null Byte Ring,
 declares with Omi-Lisp, defines through inverse/attribution
 references, discovers through governed interpolation and
 interpretation, and projects through OMI-Lisp Projection
 Diagrams that may render on Omi-Canvas.
 Cardinality, chirality, ordinality, and modality classify each
 categorical group. Application remains outside OMI.
---