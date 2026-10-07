# Agent specification: <name>

Status: proposed | reviewed | implemented | evaluated (choose one)
Pack version: 0.1.0-draft
Specification version: <version>
Owner/reviewer: <responsible party; do not invent approval>

## Purpose and success

- Use case and shared entity:
- Handoff ambiguity this agent addresses:
- Required outcome and measurable acceptance criteria:
- Non-goals and simpler alternative considered:

## Identity and representation — AP-01, AP-05

- Stable agent ID:
- Represented entity ID and relationship:
- Identity authentication mechanism and verifier:
- Delegating authority, reference, scope, validity, revocation lookup:
- History/version linkage when model, tools, or role changes:

## Modality binding — AP-02, AP-03

- Primary modality ID/version and manifest path:
- Additional permitted modalities and explicit transition rules:
- Binding/context version:
- Overloaded concepts and qualified meaning references:
- Evidence standards, assumptions, and domain boundaries:

## Authority and tools — AP-03, AP-08

- Advisory outputs versus decisions this agent may make:
- Decisions reserved for other agents or humans:
- Trusted authority verifier, required checks, and unavailable-verifier behavior:
- Actual runtime tools/resources/operations and enforcement mechanism:
- Permitted recipients, data handling, and retention responsibilities:
- Unimplemented controls or unverified integration assumptions:

## Input/output and behavior — AP-02, AP-04, AP-07

- Accepted envelope/claim versions and validation rules:
- Required input facts and evidence:
- Output contract and original-source retention:
- Bridges it may propose/use and who reviews them:
- Treatment of uncertainty, conflicts, missing facts, and invalid claims:
- Synthesis responsibility, if any, and trace format:
- Retry/stop/escalation criteria appropriate to this task:

## Agent instructions

<Complete the prompt pattern in GUIDING_AI.md using the explicit bindings above. Do not leave placeholders in a deployed prompt.>

## Evaluation and handoff — AP-06

- Positive case and expected output:
- Ambiguous/missing/revoked/out-of-scope cases and expected outputs:
- Platform-specific verification planned versus completed:
- Baseline comparison, quality metrics, token/latency/maintenance costs:
- Conformance matrix: AP ID | design evidence | test evidence | gap/status
- Open decisions and next responsible owner:
