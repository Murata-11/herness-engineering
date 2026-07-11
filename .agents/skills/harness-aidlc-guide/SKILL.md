---
name: harness-aidlc-guide
description: Guide AI-assisted software delivery with adaptive AI-DLC principles and this repository's documentation harness. Use when starting or shaping a product, adding a feature, fixing a defect, refactoring, or improving quality and operations, and when Codex must choose an appropriate scope, plan, approval points, artifacts, and validation rather than impose a fixed workflow.
---

# Harness AI-DLC Guide

Use the repository as the durable context. Adapt the work to the request; do not require every lifecycle stage, document, or planning checkpoint for every change.

## Choose the path and depth

1. Read `AGENTS.md`, the relevant source of truth, existing implementation, and applicable settings before proposing changes.
2. Classify the primary pathway: product inception, feature addition, defect fix, refactor, quality improvement, or operations work.
3. Assess the change's impact, uncertainty, reversibility, and risk. Select only the lifecycle stages and artifact depth that add value.
4. State verified facts separately from assumptions. Do not silently turn an assumption into an approved requirement.

For a high-uncertainty, high-impact, or multi-step change, propose a concise adaptive plan before material implementation. Include:

- intended outcome and stopping point;
- selected stages and why other stages are unnecessary;
- files or durable artifacts to create or update;
- validation evidence;
- decisions requiring human confirmation.

For a self-contained, low-risk change whose expected behavior is already clear, state the intended change and validation briefly, then proceed.

Use a task goal only when the user explicitly asks to create one. Treat a goal as session-level progress tracking; store lasting decisions, requirements, plans, and evidence in the repository.

## Apply only the needed stages

### Inception — determine what and why

Use this stage when behavior, users, scope, acceptance criteria, or a durable technical decision is unclear or changing.

- Record user behavior, scope, non-scope, and acceptance criteria in `docs/product-specs/`.
- Record durable architectural or technical decisions in `docs/design-docs/`.
- Create an active execution plan in `docs/exec-plans/active/` for work that has multiple milestones, decisions, or validation steps.
- Keep small, low-risk fixes lightweight when existing specifications already determine the required behavior.

### Construction — determine how and build it

Use this stage for implementation, build configuration, tests, and quality automation.

- Respect the dependency directions and ownership in `ARCHITECTURE.md`.
- Update architecture and operational entry points when the implementation introduces or changes them.
- Add or update automated checks for recurring invariants where proportionate to the risk.
- Record validation evidence in the execution plan or PR information, as required by `docs/QUALITY.md`.

### Operations — deploy and learn from running systems

Use this stage only when deployment, reliability, security, observability, or production support is in scope.

- Define ownership, review triggers, and verification before adding `docs/RELIABILITY.md` or `docs/SECURITY.md`.
- Treat runtime configuration, CI/CD, and infrastructure code as their own source of truth; link to them rather than duplicating values in prose.

## Stop only at critical decision points

Propose options, trade-offs, and a recommendation, then wait for explicit direction before fixing any of the following:

- product scope or an external commitment;
- a new architecture, dependency, paid service, or data source;
- security, privacy, retention, compliance, or production-risk posture;
- a destructive or hard-to-reverse change.

Continue autonomously with evidence-backed drafting, implementation, and reversible changes that stay within the confirmed scope.

## Preserve traceability and close the loop

1. Update the relevant document indexes and reciprocal links in the same change as a new or moved document.
2. Run the checks appropriate to the changed code and documentation. Never describe unrun or failed checks as successful.
3. For complex work, keep the execution plan's progress, decisions, and follow-ups current; move it to `completed/` only after its validation is recorded.
4. Prepare the Japanese PR description using `.github/PULL_REQUEST_TEMPLATE.md`, including purpose, impact, and validation evidence.

## Use this depth guide

| Situation | Expected depth |
| --- | --- |
| Typo or self-contained, low-risk defect fix | Inspect context, make the smallest change, and validate. Add durable documentation only if it prevents recurrence. |
| Feature within an approved product direction | Confirm affected behavior and design constraints, then implement and test. Add a specification or plan when the existing sources do not make the acceptance criteria and work clear. |
| New product, new capability, or high-uncertainty change | Start with Inception artifacts, confirm critical decisions, then construct incrementally. |
| Deployment, security, reliability, or data-risk work | Deepen validation and explicit human approval before execution. |

## Response shape

At the start of work, report: **current understanding**, **proposed path**, **decision requests**, and **validation plan**. At handoff, report: **outcome**, **evidence**, **remaining assumptions or follow-ups**, and **suggested next goal**.
