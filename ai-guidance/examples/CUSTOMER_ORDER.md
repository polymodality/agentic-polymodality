# Worked design example: one order, several meanings

Synthetic, illustrative, unexecuted. All IDs, limits, and policies below are invented for this example. This is not a live approval or finalized protocol.

## Agents and domains

| Actor | Represents | Modality | Contribution | Boundary |
|---|---|---|---|---|
| sales-01 | sales department | sales@1 | Customer qualifies for this offer | Cannot grant credit or service access |
| finance-01 | finance department | finance@1 | Credit limit approved for this order | Cannot authorize restricted-service access |
| security-01 | service-access authority | security@1 | Service access decision | Cannot approve credit |
| fulfillment-01 | fulfillment service | fulfillment@1 | Determine readiness and perform permitted fulfillment | Must verify all required decisions and runtime access |

Each requires its own completed AGENT_SPEC, verified binding, and runtime controls before implementation. These names do not themselves authenticate the actors. Synthesis is a distinct responsibility within fulfillment's proposed decision workflow, not another source of approval authority.

## Minimal vocabulary

- sales.qualified@1: customer satisfies offer eligibility conditions.
- finance.approved@1: scoped credit limit accepted under the named credit policy.
- security.authorized@1: scoped service-access operation permitted under the named access policy.
- fulfillment.ready@1: all applicable prerequisites are independently satisfied and verified.

These four concepts illustrate a handoff; they are not complete domain manifests.

## Contributions

Envelope S1: sales-01 represents sales; subject customer-123; order-456; sales.qualified@1; evidence customer-review-1; context order-review@1; sales-policy@1; delegation DS1. Qualification is assumed verified for this exercise, not a real verifier result.

Envelope F1: finance-01 represents finance; claim F1-C1 is finance.approved@1 for order-456, customer-123, at most USD 5,000. Evidence credit-review-321; policy credit-policy@3; delegation DF1; validity 2026-10-07T12:00:00Z through 2026-10-08T12:00:00Z. Evaluate at 2026-10-07T13:00:00Z. Source confidence high applies to the credit interpretation only.

Security envelope: missing. No policy or delegation verification is fabricated for it.

## Proposed bridge

B1@1: finance.approved@1 **contributes_to** fulfillment.ready@1.

Conditions: same customer/order, required credit no greater than the approved limit, matching currency, current policy compatibility, valid authenticated source and delegation, and approval still within validity. The bridge contributes one prerequisite; it does not establish readiness by itself.

Counterexample: credit is approved but required service access has not been authorized. Information loss would occur if the amount, currency, or expiration were compressed to just “approved”; preserve those fields. Status: proposed for domain-owner review.

## Synthesis and action status

Source-domain conclusion: F1-C1 satisfies the credit prerequisite under the exercise's explicit verification assumptions.

Bridge inference: B1 maps that scoped credit result to one fulfillment prerequisite.

Synthesized conclusion C1: this order is credit-ready within USD 5,000, but not fulfillment-ready because service-access authorization is missing. Sales qualification and credit approval cannot collectively substitute for that decision.

Trace: C1 ← S1 + F1/F1-C1 + B1@1 + fulfillment@1 prerequisite definition + recorded absence of security contribution. A production trace must additionally include trusted verification records; none are supplied here.

Action status: blocked. Request the scoped access decision from security-01 or the actual authorized owner. Do not grant security tools or permissions to finance/fulfillment to fill the gap.

## Follow-up and negative variants

- Security provides a valid scoped authorization: verify its identity, delegation, current policy, validity, and scope; then independently check execution permission before eligibility.
- Order increases to USD 6,000: F1 no longer satisfies credit requirements; request revised finance decision.
- Credit policy changes: identify compatibility uncertainty and revalidate explicitly.
- Finance delegation is revoked: keep F1's historical provenance but do not treat it as current action authority.
- Finance and security disagree about the subject identity: preserve the conflict and resolve identity before combining decisions.

A successful demonstration compares these cases with the simpler baseline and records benefits and additional cost. No outcome has been measured by this guidance pack.
