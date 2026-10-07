# Sources, interpretation, and open decisions

Prepared 2026-10-07. Source hashes are in SOURCE_MANIFEST.json. Copies of the Markdown sources and a text extraction of the Word document are included under sources/ so the pack can travel to another AI. The original DOCX remains the source of record for its formatting and figure; the text extraction does not reproduce visual content or establish platform behavior.

## Source map

| Guidance | Project source |
|---|---|
| Identity distinct from represented entity; delegation lifecycle | MANIFESTO: “Give representation an identity”; README: “What the project aims to define” |
| Context and separate semantic/governance/security dimensions | MANIFESTO: commitments 2–3; README: “What is a dimension?” |
| Explicit translations and continuity | MANIFESTO: commitments 4–5 |
| Reproducible benefit and simpler baseline | MANIFESTO: commitment 6; README: “First demonstration” |
| Modality as semantic frame, not media/model choice | Whitepaper §§1.2, 2 |
| Manifests, bindings, envelopes, bridges, synthesis | Whitepaper §§5, 8, Appendix A |
| Preserve raw outputs and source-domain summaries | Whitepaper §6.4 |
| Uncertainty, conflict, authority, tool isolation | Whitepaper §9 |
| Evaluation dimensions and limits | Whitepaper §§10–11 |
| Incremental technique before product | Whitepaper §§6.5, 12; README status |
| Customer/order exercise and missing security decision | README: concrete handoff and first demonstration |

## Reconciling emphasis

The whitepaper emphasizes semantic synthesis, uses “orthogonal” as an architectural description, and proposes OpenClaw as an implementation substrate. The repository Markdown emphasizes explicit identity, representation, delegation, and a proposal open to public discussion. It explicitly reserves mathematical orthogonality for a future formal model.

This pack combines those commitments. It uses the Markdown's cautious formal-status language, includes the whitepaper's five practical constructs, and treats OpenClaw as an example rather than a required dependency. This is a disclosed synthesis of the sources, not a claim that the owner approved a new precedence rule.

## Proposed conventions introduced here

AP identifiers, file organization, exact template fields, the conformance matrix, the draft 0–2 rubric, the context-loading workflow, and the example bridge/verification states are authoring aids created for this pack. They are not established interoperability requirements. The customer example expands the README with fictional actors and conditions. Review these choices before adopting them as project standards.

## Decisions still owned by the project

- Final terminology and relationship between dimensions and semantic modalities.
- Normative schema, version compatibility, identifier format, and migration rules.
- Identity/delegation verifier, policy source, revocation mechanism, and enforcement integration.
- Who reviews modality definitions and bridge changes; lifecycle of approval.
- Evidence retention, access controls, confidentiality, and provenance storage.
- Runtime/platform versions and deployment details.
- Quantitative acceptance thresholds and baseline experimental design.

An AI may propose options and reversible prototypes. It must not invent owner approval, working controls, or measured benefits. Unresolved implementation details should not block preparing advisory specifications.

## Platform references

The whitepaper cites OpenClaw documentation as checked on September 18, 2026. This pack has not revalidated those API/configuration claims. Verify official documentation for the actual deployed version before producing a runnable OpenClaw integration. The portable guidance itself does not depend on those APIs.
