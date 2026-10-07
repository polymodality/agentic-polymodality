# Vision and design commitments

## Purpose

Give agents identities that distinguish them from what they represent. Preserve meaning across contexts so collaborators can tell what a claim means, where it applies, who contributed it, and which legitimate action it can support. When domains interact, derive useful relationships while preserving their differences.

## Vocabulary

- **Agent:** an actor with identity, responsibilities, memory/tool context, and a lifecycle.
- **Represented entity:** the person, organization, department, project, or service whose perspective the agent expresses. Representation alone conveys no authority.
- **Dimension:** an independently expressible aspect of representation or action. Identity, semantics, context, governance, and cybersecurity are starting dimensions, not an exhaustive taxonomy.
- **Modality:** the whitepaper's domain-specific semantic frame: concepts, assumptions, evidence standards, and interpretation rules. It does not mean image/audio/text or model selection.
- **Binding:** an explicit, versioned association between an agent and one or more modalities. Agent and modality are separate concepts.
- **Envelope:** a contribution carrying claims and the context needed to interpret and verify them.
- **Bridge:** a conditional relationship between concepts in different modalities, with assumptions and limits.
- **Synthesis:** a justified conclusion derived across domains, with a trace through source claims and bridges. A summary or concatenation alone is not synthesis.

## Commitments to preserve

| ID | Commitment | Consequence for agent design |
|---|---|---|
| AP-01 | Distinguish actor and represented entity | Record both identities and a delegation source, scope, validity, and revocation mechanism. |
| AP-02 | Meaning travels with context | Qualify overloaded terms by vocabulary/version; retain subject, scope, evidence, assumptions, and conditions. |
| AP-03 | Keep dimensions independently expressible | Describe semantic meaning, governance authority, and enforced access separately; make links inspectable. |
| AP-04 | Translation is explicit | Preserve source envelopes, name bridges, disclose information loss, conditions, and counterexamples. |
| AP-05 | Continuity survives change | Version modality/context/binding/policy records; retain historical provenance when tools, models, or authority change. |
| AP-06 | Benefits must be observable | Compare to simpler role prompts plus structured messages; measure both quality and complexity. |
| AP-07 | Preserve uncertainty and disagreement | Distinguish observations, interpretations, recommendations, and conflicts; do not manufacture consensus or unsupported confidence. |
| AP-08 | Authority requires verification and enforcement | A delegation reference or approval statement is not a permission grant. Verify trusted authority and independently enforce resource access. |

AP-01–06 summarize the manifesto's six commitments. AP-07 operationalizes whitepaper §§5, 8–10. AP-08 connects README's handoff verification with manifesto §§1, 3 and whitepaper §9.

## Boundaries

Do not claim mathematical orthogonality without a defined formal model. Do not claim interoperability, formal proof, security isolation, or runtime compliance based only on prompts and JSON. Do not create a universal ontology before demonstrating a small useful bridge. Do not present the initial repository as a working platform.

The initial exercise is one customer/order with sales, finance, security, and fulfillment perspectives. The separate synthesis responsibility may be a role in that workflow; an additional process is not automatically required. The whitepaper's document-agent release scenario is a second useful exercise, not a replacement for the repository's proposed first demonstration.
