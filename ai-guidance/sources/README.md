# Agentic Polymodality

**Give agents identity. Preserve meaning across contexts.**

Agentic polymodality is a proposed architectural approach for giving agents explicit identities and context-specific representations, with defined relationships and translations between them.

The goal is to help agents represent people, organizations, projects, and services—and collaborate while keeping the meaning, scope, provenance, and authority of their contributions intelligible.

**Start with [The Agentic Polymodality Manifesto](MANIFESTO.md).**

## Why this matters

Consider three agents working on one customer request:

- Sales determines that the customer is qualified.
- Finance approves a credit limit.
- Security authorizes access to a service.

A fulfillment agent needs to understand which decisions permit its next action. The word “approved” alone cannot tell it what was approved, who approved it, or which conditions apply.

Agentic polymodality proposes making those distinctions explicit and preserving them across handoffs. Each agent can contribute its own perspective while collaborators can inspect how that contribution applies to their work.

## What is a dimension?

A dimension is an independently expressible aspect of an agent’s representation or action. The following are starting points for the project, rather than a fixed or exhaustive taxonomy:

| Dimension | Question | Example |
| --- | --- | --- |
| Identity | Who is the agent, and what does it represent? | An agent representing a finance department |
| Semantics | What do its terms and claims mean? | “Approved” means a specified credit limit was accepted |
| Context | Where and under what conditions does that meaning apply? | A particular customer, transaction, and policy version |
| Governance | What responsibilities and decision authority apply? | Delegated authority to approve credit up to a threshold |
| Cybersecurity | What resources and operations are accessible? | Enforced permission to read an account and record a decision |

These dimensions can interact while remaining separately describable. In particular, semantics, governance, and cybersecurity answer different questions. Their connections should be explicit and inspectable.

“Dimensional” describes the architectural approach here. A formal mathematical model would need to define its spaces, mappings, and independence properties.

## A concrete handoff

Instead of exchanging an isolated approval, a finance agent could contribute a structured claim such as:

```json
{
  "claim_id": "claim-1042",
  "agent_id": "agent-finance-01",
  "represents": "department-finance",
  "subject": "customer-123",
  "context": "credit-review-v1",
  "claim_type": "credit_limit_approved",
  "scope": {
    "order_id": "order-456",
    "amount": 5000,
    "currency": "USD"
  },
  "delegation_ref": "delegation-789",
  "policy_ref": "credit-policy-v3",
  "evidence_refs": ["credit-review-321"],
  "issued_at": "2026-10-02T12:00:00Z",
  "expires_at": "2026-10-03T12:00:00Z"
}
```

This is an illustrative message, not an implemented protocol or finalized schema. The identifiers and timestamps are fictional.

A receiving agent would need to resolve the vocabulary, authenticate the source, verify the delegation, evaluate scope and validity, and check any other required approvals. Referencing authority in a message does not establish it; trusted verification and enforcement mechanisms must support the exchange.

The intended result is a handoff that preserves enough meaning to determine the next legitimate action—or identify the decision still needed.

## What the project aims to define

- **Identity and representation:** distinguish an agent from the entity it represents and describe scoped delegation.
- **Contextual semantics:** identify vocabularies, interpretations, assumptions, and versions.
- **Scoped claims:** preserve subject, source, evidence, validity, and intended application.
- **Translation relationships:** map contributions between contexts while exposing assumptions and information loss.
- **Governance connections:** link decisions to responsibilities, authority, and accountability.
- **Security connections:** connect representation and policy to authentication, access controls, and enforcement.

Existing schemas, messaging protocols, identity systems, and policy engines are useful foundations. The project’s proposed contribution is a coherent model for connecting them so meaning and responsibility survive collaboration between agents.

## Status

This initial repository contains the manifesto and project introduction. The architecture is a proposal for public discussion. A reference implementation, validated interoperability specification, and runnable demonstration are future work.

## First demonstration: one customer, three perspectives

The proposed first example will use sales, finance, security, and fulfillment agents working on one order.

It should show that:

1. A finance approval retains its credit-specific meaning when fulfillment receives it.
2. The receiver checks the claim’s source, delegation, scope, and validity.
3. A missing security authorization leads to a request for the appropriate decision.
4. A context or policy revision can be identified and handled explicitly.
5. The record explains which contributions supported the final action.

We intend to compare this with a simpler exchange using role prompts and structured messages. The comparison should document both benefits and added complexity.

## Participate

Open an issue to contribute:

- A concrete use case involving several perspectives on the same entity.
- An agent handoff where meaning, scope, or authority became ambiguous.
- A proposed definition, message schema, or translation rule.
- An integration approach using existing protocols or infrastructure.
- A counterexample or a simpler architecture that addresses the same need.

For each use case, describe what the agents represent, what they exchange, where interpretation becomes difficult, and what successful behavior would look like.

Early contributions can help refine the terminology and shape the first reproducible example.

## Foundational document

[The Agentic Polymodality Manifesto](MANIFESTO.md) sets out the motivation and commitments guiding this project.

**Let identity endure. Let context travel. Let collaboration preserve meaning.**
