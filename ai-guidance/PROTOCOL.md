# Draft collaboration protocol

This operationalizes the sources; it is not a validated wire protocol. Exact storage formats and trust providers remain implementation choices.

## 1. Bind identity and domain

Resolve agent identity and represented entity separately. Select an explicit modality/context version. Record delegation scope and lifecycle independently of the agent prompt. Define allowed resources/actions in the runtime, not merely in the semantic manifest.

## 2. Create a source envelope

Include stable envelope and claim IDs; source identity; represented entity; modality/binding versions; subject and context; observations; claims with qualified meanings; evidence references; assumptions; uncertainty; applicable policy/delegation references; scope and validity; and open questions. Keep recommendations separate from statements of fact.

Evidence references locate support, not proof of its truth. Validity may be temporal, contextual, or policy-dependent. A proposed claim contract is in templates/SEMANTIC_CONTRACTS.json.

## 3. Receive without silently translating

Retain the original envelope. Check completeness, source authenticity, known vocabulary/context versions, shared subject, scope, temporal validity, and evidence availability. When an action depends on authority, verify delegation and revocation with the trusted authority mechanism. Unknown and unavailable are distinct from verified.

A routing agent passes the original envelope intact. If compression is needed, obtain a source-domain summary and record the original reference and lost detail.

Malformed or unresolvable contributions may remain visible as unverified context but cannot support a consequential action. Request clarification from the responsible source rather than filling gaps with guesses.

## 4. Bridge concepts

Name the source and target qualified concepts and versions. State the relationship, its conditions, evidence/justification, uncertainty, and counterexample. Whitepaper starting vocabulary: equivalent_to, related_to, contributes_to, causes, constrains, conflicts_with, transforms_to.

Use equivalent_to only when equivalence is justified within the stated scope; common wording is insufficient. Use causes only with appropriate causal support. New bridges are proposals, not automatically approved catalog entries. Record information loss and preserve the source claim.

## 5. Synthesize

For two or more modalities, emit:

1. Source-domain conclusions, attributed without changing their meaning.
2. Bridges applied and whether their conditions hold.
3. Cross-domain conclusions that follow, with assumptions and uncertainty.
4. Conflicts, missing contributions, and unresolved translations.
5. A trace: conclusion → source claim IDs/envelope versions + bridge IDs/versions + evidence.
6. Decision/action status, separately justified by required approvals and enforced access.

Confidence cannot be upgraded merely because several agents repeat a claim. New supporting evidence and a stated method are required for any stronger confidence assessment.

## 6. Decide and preserve continuity

A correct interpretation is not automatically an authorized action. Confirm all required domain decisions, their compatible scope/validity, verified delegation, and runtime permission before execution. If security authorization is missing, request it from the appropriate decision-maker; do not reinterpret finance approval as security authorization.

On policy/context updates or revocation, retain historical provenance, identify affected claims/bindings/bridges, and revalidate their current use. Do not silently reinterpret an old claim using a new vocabulary. Record the decision, supporting contributions, verifier results, unresolved issues, and actual execution outcome.
