# How to give this guidance to a new AI

## 1. Provide files, not just a link or filename

Give the AI readable access to this folder or upload its files. A folder path works only when that AI has filesystem access. For a chat without file access, attach the Markdown/JSON files or paste their content in labeled sections. If using a ZIP, confirm the AI can extract and read it. If an AI cannot open Word documents, use sources/WHITEPAPER_EXTRACT.txt.

Start with START_HERE.md, VISION.md, and GUIDING_AI.md. Supply PROTOCOL.md and templates before requesting agent designs, plus EVALUATION.md before asking for a review. SOURCES_AND_DECISIONS and the source snapshots provide grounding when meanings are disputed. Keep domain-specific context limited to what the task needs.

Some coding environments auto-load specific instruction filenames. This pack deliberately does not assume that behavior. Explicitly ask the AI to read these files. If you later add a project instruction file, use a short pointer to START_HERE rather than duplicating the whole pack.

## 2. Copy/paste kickoff prompt

```text
Use the attached Agentic Polymodality guidance pack, version 0.1.0-draft.
Read START_HERE.md, VISION.md, GUIDING_AI.md, PROTOCOL.md, the templates,
and EVALUATION.md. Use SOURCES_AND_DECISIONS.md to distinguish original
project commitments from proposed implementation conventions.

My task: [describe the agents/workflow to design].
Shared entity or decision: [what all perspectives concern].
Platform and actual available tools: [known details, or “unspecified”].
Authority and data boundaries: [known owners/limits, or “unresolved”].
Desired deliverable: [design files, prototype, or review].
Success criteria: [observable results].

First list the files you successfully read and explain, briefly, the
identity/representation distinction, semantic modality, explicit bridges,
and separation of meaning, decision authority, and enforced access.
Identify missing context; do not invent it. Then perform the task using
GUIDING_AI.md. Preserve source-domain meaning and uncertainty. Label
proposals and unverified assumptions. Finish with the AP-01–08 conformance
matrix, evaluation status, open decisions, and a continuation handoff.
Do not claim this pack grants runtime permissions or proves compliance.
```

The first response is a comprehension check, not a request to ask permission for every step. Correct misunderstandings before investing in implementation.

## 3. Add a task brief

A stable base does not replace the particulars. Provide the real entities, source data/evidence, local vocabulary, desired outputs, available tools, reviewers, authority boundaries, costs, and deployment constraints. Use synthetic data for initial demonstrations. Do not upload confidential sources to an AI service without authorization.

Example: “Design sales, finance, security, and fulfillment agents for one order. No production tools are available. Deliver advisory specifications and two handoff traces, including missing security authorization. Compare against role prompts plus structured messages.”

## 4. Use the base guidance through the work

- **Design:** complete one AGENT_SPEC per actor and reuse modality manifests across actors where appropriate.
- **Review:** ask an AI or human reviewer to evaluate AP-01–08 using actual artifacts and traces, not statements of intent.
- **Implementation:** add a platform-specific layer only after verifying its real APIs and controls. Preserve portable contracts underneath it.
- **Evaluation:** run the same cases under a simpler baseline and the polymodal design. Record correctness, traceability, cost, and complexity.
- **Continuation:** reload the base and the current handoff in a fresh session. Do not assume prior chat memory or previous uploads are still present.

Benefits to look for are consistent terminology across newly created agents, less repeated explanation, explicit authority boundaries, reusable reviews, and detectable drift. These are intended benefits; use EVALUATION.md to determine whether they occur.

## 5. Handoff template

```text
Pack version and source revision/hashes:
Task and intended outcome:
Files created/changed and where they can be read:
Agent/modality/binding/bridge versions:
Owner-approved decisions (with references):
Proposals and unverified assumptions:
Evidence and original envelope references:
Tests run and observed results:
Tests unrun and remaining gaps:
Authority/enforcement state:
Conflicts and questions for the owner:
Next concrete action:
```

## 6. Keep the guidance current

Treat the project repository as the maintained copy. Change the source vision deliberately, then update affected guidance, examples, and tests together. Record why the change was made, who approved project-level decisions, and which agents/contracts need revalidation. Increment the pack version and refresh SOURCE_MANIFEST.json and snapshots when the sources change.

Do not silently edit source snapshots to make the pack appear consistent. Preserve older versions when they explain past decisions. At each new session, compare the pack's source hashes to the current project sources. If stale, reconcile before relying on it for a new design. An exported ZIP is a dated snapshot and should be regenerated after changes.

The guidance reduces repeated setup; it does not retrain a model, guarantee obedience, establish authority, or replace external enforcement and domain review.
