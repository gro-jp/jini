# Org-Wide, Model-Agnostic Software Factory

**Document type:** Product Requirements Document (discovery draft)  
**Version:** 0.1  
**Date:** 2026-07-26  
**Status:** Not approved; intended for brainstorming and interview  
**Scope of this document:** Product definition and requirements only. It deliberately does not select a final technology stack or provide an implementation plan.

---

## 1. Executive summary

The proposed product is an **open, model-agnostic software factory** that converts approved business intent into evidence-backed software changes through durable, observable, resumable workflows.

The factory is not an unstructured swarm of autonomous LLMs. Its core is a **deterministic control plane** that owns queueing, workflow state, retries, permissions, budgets, checkpoints, evidence, and policy enforcement. LLMs are interchangeable reasoning workers used only where probabilistic intelligence is valuable: clarification, specification, architecture, decomposition, implementation, critique, and qualitative evaluation.

The factory should preserve complete provenance for every run; maintain a portable, curated body of organizational knowledge; support multiple model providers and open-source models; enforce specification-driven and test-driven development; expose real-time progress to humans; and continuously improve through controlled analysis of historical traces and outcomes.

The central product promise is:

> **Approved intent in; reproducible, evidence-backed software change out; humans retain governance.**

---

## 2. Problem statement

Modern coding agents can produce code quickly, but org-wide autonomous software delivery remains unreliable because the surrounding system is missing or fragmented:

1. Requests arrive through inconsistent channels and contain ambiguity.
2. Product intent, architecture decisions, codebase conventions, incidents, and business context are scattered.
3. Agent sessions are often single-user, ephemeral, opaque, and difficult to resume.
4. “Done” is frequently judged by an agent’s confidence rather than executable evidence.
5. Different models and coding harnesses have incompatible interfaces and state models.
6. Parallel agents can duplicate work, conflict, or diverge architecturally.
7. Prompts, corrections, failures, and review feedback are rarely converted into durable organizational learning.
8. Human attention becomes the bottleneck when people must supervise many long-running agent sessions.
9. Existing platforms tend to create vendor, model, cloud, or workflow lock-in.

The factory must solve these surrounding-system problems rather than merely wrapping another coding agent.

---

## 3. Product vision

Build an organization-wide software delivery operating system in which:

- Any approved source can submit work.
- Ambiguous requests are clarified before expensive implementation begins.
- A versioned specification becomes the contract for the change.
- Acceptance criteria are translated into executable or otherwise auditable evaluation oracles.
- Work is decomposed into small, independently verifiable units with explicit dependencies.
- Specialized agents can use Claude, Gemini, OpenAI/Codex, open-source models, or future models through adapters.
- Every run is durable, resumable, replayable, and inspectable.
- Every prompt, response, tool call, decision, artifact, test, diff, approval, and outcome has provenance.
- Humans can observe and steer work in real time without micromanaging each session.
- Production authority is governed by risk policy, not by model confidence.
- Historical execution data compounds into better context, tests, skills, routing, and workflows.

---

## 4. Product goals

### G-01 — Model and harness independence

The control plane must not depend on one provider’s session format, tool protocol, prompt format, or proprietary agent runtime. Providers and harnesses are plugins with declared capabilities.

### G-02 — Evidence-based completion

A task is complete only when every required acceptance criterion has produced the required evidence. A single model-generated “looks good” judgment is insufficient.

### G-03 — Durable and resumable execution

A workflow must survive worker crashes, model limits, network outages, process restarts, infrastructure failures, and intentional pauses without restarting completed work.

### G-04 — Complete provenance

The factory must retain a logically complete account of what happened, why it happened, which inputs were used, which model and tools acted, what changed, and what evidence justified each decision.

### G-05 — Accessible organizational knowledge

Domain knowledge must be human-readable, agent-readable, versioned, attributable, portable, and retrievable with progressive disclosure.

### G-06 — Specification-driven and test-driven delivery

Intent, constraints, acceptance criteria, and evaluation design must precede implementation. Tests are part of design, not merely a final verification step.

### G-07 — Safe parallelism

The factory should support hundreds or more concurrent work units while detecting duplicated work, dependency conflicts, overlapping file ownership, resource contention, and incompatible plans.

### G-08 — Continuous improvement

Historical traces and outcomes must support controlled improvements to prompts, context packs, skills, tests, routing policies, decomposition strategies, and models.

### G-09 — Open control plane

Every non-model component of the factory should be open source or self-built. The meaning of this requirement for proprietary foundation-model APIs remains an explicit interview question.

### G-10 — Simple human interface

A requester or operator should be able to submit a task and understand current state, blockers, decisions, costs, artifacts, evidence, and next actions without reading raw logs.

---

## 5. Non-goals

The initial product should not attempt to:

1. Build or train a frontier foundation model.
2. Replace every existing ticketing, source-control, chat, documentation, or CI system.
3. Make autonomous business-priority or product-strategy decisions without accountable ownership.
4. Treat raw execution logs as curated knowledge.
5. Depend on direct pushes to production as proof of autonomy.
6. turn every logical module into a separately deployed microservice.
7. Achieve million-task scale in the first prototype.
8. Allow the learning system to modify production prompts, policies, permissions, or evaluators without controlled evaluation and promotion.
9. Use an LLM as the primary queue watcher, retry scheduler, lock manager, policy engine, or workflow state machine.
10. Force all work, including discovery spikes, into a rigid process where the process costs more than the task.

---

## 6. Core design principles

### P-01 — Deterministic shell, probabilistic workers

Code owns lifecycle and authority. Models own bounded reasoning tasks.

### P-02 — Evidence over confidence

Claims are linked to test results, traces, diffs, approvals, measurements, or cited source material.

### P-03 — Global visibility, local context

The organization may possess enormous context, but each model call should receive only the smallest sufficient, versioned context pack. “Org-wide context” must not mean pasting the entire organization into every prompt.

### P-04 — Events describe facts; commands request actions

The factory should distinguish immutable facts such as `SpecificationApproved` from commands such as `GenerateImplementationPlan`. This avoids an ungoverned event soup.

### P-05 — Durable workflows over ad hoc agent loops

Long-running missions are explicit state machines or durable workflows. Events integrate and observe those workflows; they do not replace ownership of the workflow.

### P-06 — Small, independently verifiable work units

Complex missions should be decomposed, but not atomized blindly. A work unit is useful when it has a clear contract, bounded context, explicit dependencies, an observable result, and a reliable evaluator.

### P-07 — Portable source, derived indexes

Human- and agent-readable files are the portable knowledge source. Vector, graph, search, and cache systems are rebuildable indexes, not the only copy of organizational truth.

### P-08 — Security and policy outside prompts

Permissions, spend caps, network access, secret access, risk gates, and deployment authority are enforced by code and infrastructure.

### P-09 — Independent criticism

The authoring agent must not be the only reviewer. High-risk work should receive independent review with separate context and, when useful, a different model family.

### P-10 — Learning requires promotion gates

The factory may propose improvements autonomously, but improvements become active only after replay, evaluation, comparison, and approval appropriate to their risk.

---

## 7. Actors and responsibilities

| Actor | Responsibility |
|---|---|
| Business requester | Describes the desired outcome, motivation, urgency, and business constraints. |
| Product owner | Owns value, scope, user-facing acceptance, and prioritization. |
| Domain owner | Provides authoritative domain rules and resolves domain ambiguity. |
| Lead architect | Owns system-level constraints, boundaries, dependencies, and technical risk decisions. This may be an agent role with human governance. |
| Security / compliance owner | Defines restricted data, approval gates, threat requirements, and prohibited actions. |
| Platform operator | Operates the factory, policies, models, runners, and capacity. |
| Planner agent | Produces or revises a plan and dependency graph. |
| Worker agent | Implements a bounded work unit in an isolated workspace. |
| Evaluator agent | Maps criteria to evidence, runs qualitative evaluations, and identifies gaps. |
| Deterministic evaluator | Runs builds, tests, static checks, policies, and other executable oracles. |
| Reviewer / adjudicator | Resolves disagreement, inspects evidence, and approves risk-sensitive transitions. |
| Knowledge curator | Converts validated outcomes into durable knowledge and retires stale knowledge. |

A person may hold several roles. Agent roles are logical roles, not permanent bindings to a specific model.

---

## 8. Canonical product entities

The factory should establish a stable semantic vocabulary independent of any external tracker or model provider.

| Entity | Meaning |
|---|---|
| Request | Raw intent submitted by a person or external signal. |
| Work Item | Canonical, normalized item owned by the factory. |
| Mission | End-to-end attempt to deliver an approved outcome. |
| Specification | Versioned statement of intended behavior, constraints, exclusions, and interfaces. |
| Acceptance Criterion | Atomic claim that must be satisfied and evaluated. |
| Evaluation Oracle | Deterministic or governed method used to judge a criterion. |
| Plan | Versioned technical approach for satisfying the specification. |
| Work Unit | Small, bounded unit in the execution dependency graph. |
| Run | One execution of a mission or work unit. |
| Step | Durable semantic transition in a run. |
| Attempt | One try at completing a step. |
| Agent Session | Logical interaction history with an agent or harness. |
| Model Invocation | One request/response exchange with a model. |
| Tool Invocation | One request/result exchange with an external tool. |
| Artifact | Immutable or versioned output such as a prompt, response, diff, test log, plan, screenshot, binary, or deployment manifest. |
| Evidence | Artifact or measurement explicitly used to support a criterion or decision. |
| Gate | Policy-controlled transition requiring stated conditions. |
| Decision | An accountable choice with alternatives, rationale, evidence, and owner. |
| Change Set | Proposed code, configuration, schema, documentation, or infrastructure changes. |
| Deployment | Release of a specific change set into an environment. |
| Signal | Event from users, production, CI, security, cost, or another system. |
| Knowledge Item | Curated, attributable fact, rule, guide, decision, relationship, or lesson. |
| Context Pack | Purpose-built, versioned bundle supplied to a reasoning step. |
| Policy | Deterministic rule governing access, authority, risk, budget, or transition. |
| Model Profile | Versioned declaration of a model/harness’s capabilities and observed performance. |

Every entity must have a stable ID and lineage links.

---

## 9. Proposed lifecycle

### Stage 0 — Intake

A request arrives from an external ticket system, native UI, API, chat integration, production signal, or recurring goal.

### Stage 1 — Deterministic pickup

A code-based dispatcher validates the envelope, deduplicates it, acquires a lease, creates the canonical Work Item, and starts a durable workflow. No LLM is required to monitor the queue.

### Stage 2 — Triage

A bounded triage agent classifies request type, probable domain, affected systems, urgency, risk, missing information, and required owners. Deterministic policies verify required fields and routing constraints.

### Stage 3 — Clarification

A specification or architect agent asks focused questions through the originating interface. The mission cannot enter implementation while blocking ambiguity remains. Answers become versioned inputs, not untracked chat.

### Stage 4 — Specification

A specification is created with goals, non-goals, scenarios, constraints, interfaces, invariants, failure behavior, operational requirements, and assumptions.

### Stage 5 — Acceptance and evaluation design

Each acceptance criterion is assigned an oracle, pass condition, evidence requirement, severity, and owner. This is the principal Definition-of-Ready gate.

### Stage 6 — Architecture and planning

A lead architect role proposes a plan. Independent critics may inspect it for omitted dependencies, unsafe assumptions, architectural drift, security gaps, and testability. Significant disagreements are adjudicated.

### Stage 7 — Decomposition and scheduling

The approved plan becomes a dependency graph of bounded work units. The scheduler detects conflicts, allocates isolated workspaces, selects models and effort, and enforces resource and permission budgets.

### Stage 8 — Test-driven execution

For each behavior-changing unit, the agent first creates or updates a failing executable test or other oracle, demonstrates the expected failure, implements the smallest compliant change, and refactors while preserving green tests. Exceptions require a declared policy reason.

### Stage 9 — Independent evaluation

Deterministic checks and independent reviewers evaluate every acceptance criterion. Failures create targeted repair work, not an unbounded “try again” prompt.

### Stage 10 — Change review

The factory produces a review package containing the specification delta, plan, change set, risk report, test evidence, trace summary, unresolved concerns, and rollback information.

### Stage 11 — Release

Authority is risk-based. The initial product may be production-deployed while retaining PR-only or non-production rights. Higher autonomy is earned per work class through measured reliability.

### Stage 12 — Post-deployment verification

The system validates runtime health, acceptance signals, telemetry, and regressions. Failed verification triggers rollback or a new repair mission according to policy.

### Stage 13 — Knowledge update

Validated changes update relevant documentation, architecture relationships, runbooks, ownership, known constraints, and lessons. Knowledge updates are linked to the code and evidence that justified them.

### Stage 14 — Kaizen

Offline processes cluster failures, identify repeated corrections, propose tests or skills, compare model routes, detect stale context, and generate improvement candidates. Candidates are evaluated before promotion.

---

## 10. Functional requirements

### 10.1 Intake and control plane

- **FR-001:** Support multiple intake adapters without changing the canonical Work Item model.
- **FR-002:** Preserve the originating system, author, timestamps, attachments, comments, and permissions.
- **FR-003:** Use a deterministic dispatcher for queue monitoring, leasing, deduplication, retry, backoff, and dead-letter handling.
- **FR-004:** Allow pause, cancel, resume, reprioritize, and reroute operations at defined safe points.
- **FR-005:** Track dependencies and prevent duplicate or materially overlapping work.
- **FR-006:** Separate human/business priority from model-estimated complexity and technical risk.
- **FR-007:** Enforce per-mission limits for cost, time, attempts, concurrency, tools, and authority.
- **FR-008:** Represent all lifecycle transitions as durable, versioned facts.

### 10.2 Triage and clarification

- **FR-010:** Classify work into configurable types such as feature, bug, incident, refactor, infrastructure, security, documentation, migration, research, and maintenance.
- **FR-011:** Identify likely affected domains, repositories, services, owners, data classes, and deployment environments.
- **FR-012:** Produce an ambiguity and contradiction report.
- **FR-013:** Ask minimal, high-value questions through the original request surface.
- **FR-014:** Distinguish blocking questions from assumptions that may be recorded and safely accepted.
- **FR-015:** Require accountable approval of the clarified intent before high-cost implementation for configured risk classes.

### 10.3 Specification and Definition of Ready

- **FR-020:** Store specifications as versioned, diffable, human-readable artifacts.
- **FR-021:** Include goals, non-goals, actors, scenarios, constraints, invariants, interfaces, data behavior, failure behavior, security, observability, migration, and rollback where relevant.
- **FR-022:** Link every acceptance criterion to its originating requirement or decision.
- **FR-023:** Define an evaluation oracle and evidence requirement for each blocking criterion before implementation.
- **FR-024:** Detect criteria that are subjective, untestable, contradictory, or implementation-prescriptive without need.
- **FR-025:** Block execution when required owners, inputs, or oracles are missing.

### 10.4 Architecture and planning

- **FR-030:** Produce versioned plans linked to an exact specification version and repository state.
- **FR-031:** Capture alternatives, tradeoffs, assumptions, risks, affected boundaries, migration strategy, and rollback.
- **FR-032:** Support independent adversarial review by one or more models or humans.
- **FR-033:** Require explicit adjudication for material reviewer disagreement.
- **FR-034:** Decompose work into a dependency graph with contracts and evaluators.
- **FR-035:** Reject work units that are too broad to evaluate or too small to justify orchestration overhead.
- **FR-036:** Detect likely merge conflicts and incompatible concurrent plans before execution.

### 10.5 Execution

- **FR-040:** Run each work unit in an isolated, reproducible workspace.
- **FR-041:** Supply only a purpose-built context pack, declared tools, permissions, budget, and expected outputs.
- **FR-042:** Normalize agent and model outputs into typed artifacts rather than relying only on prose chat.
- **FR-043:** Support multiple model providers, open-source models, and coding harnesses through adapters.
- **FR-044:** Allow model fallback and migration without losing canonical run state.
- **FR-045:** Make TDD the default for behavior-changing work: red, green, refactor, evidence.
- **FR-046:** Require infrastructure agents to produce declarative, repeatable, idempotent changes and idempotency evidence.
- **FR-047:** Record every external side effect with an idempotency key and result.
- **FR-048:** Support bounded repair loops with strategy changes and escalation after repeated failure.

### 10.6 Evaluation and Definition of Done

- **FR-050:** Evaluate at criterion level, not only at ticket level.
- **FR-051:** Prefer deterministic oracles: compile, lint, unit, property, contract, integration, end-to-end, migration, security, policy, performance, visual, and runtime checks.
- **FR-052:** Use LLM judges only where deterministic evaluation is not practical, with explicit rubric, evidence, model identity, and confidence.
- **FR-053:** Prevent the implementation agent from being the sole evaluator.
- **FR-054:** Produce a machine-readable pass/fail result and evidence bundle for each criterion.
- **FR-055:** Define overall completion as the conjunction of all required gates, not an average score.
- **FR-056:** Detect evaluator reward hacking, test weakening, skipped tests, removed assertions, and changes to the oracle that merely make a failure disappear.
- **FR-057:** Cap retries and escalate rather than looping indefinitely until an unreliable judge says yes.
- **FR-058:** Support Definition-of-Done profiles by work class and risk level.

### 10.7 Resumability

- **FR-060:** Persist workflow state at every semantic transition.
- **FR-061:** Resume from the last completed durable step after worker, server, or provider failure.
- **FR-062:** Re-execute only the current incomplete activity unless previous side effects cannot be proven complete.
- **FR-063:** Require activities to be idempotent or to declare compensation behavior.
- **FR-064:** Build a provider-independent Resume Capsule containing goal, spec version, plan version, completed steps, current step, artifacts, evidence, decisions, blockers, workspace state, and next action.
- **FR-065:** Store provider session identifiers when available but never make them the sole resume mechanism.
- **FR-066:** Test crash recovery deliberately by terminating workers at arbitrary stages.

### 10.8 Observability, logs, and provenance

- **FR-070:** Capture 100% of workflow spans and model/tool invocations at the control-plane boundary.
- **FR-071:** Retain raw prompts, responses, streaming chunks, tool inputs/results, system instructions, context manifests, token counts, model parameters, retries, timings, and errors where policy permits.
- **FR-072:** Retain plans, specs, diffs, commits, build outputs, test results, screenshots, recordings, environment manifests, binaries, deployments, approvals, and runtime verification.
- **FR-073:** Use stable correlation identifiers linking request → mission → run → step → invocation → artifact → evidence → change → deployment → production signal.
- **FR-074:** Use content hashes for immutable artifacts and capture parent/derived-from relationships.
- **FR-075:** Provide both a human-readable timeline and machine-queryable event history.
- **FR-076:** Separate immutable raw storage from searchable projections, metrics, and curated knowledge.
- **FR-077:** Encrypt restricted content, enforce access by data class, and prevent accidental credential duplication.
- **FR-078:** Make replay and audit possible without depending on a vendor dashboard.

### 10.9 Knowledge and context

- **FR-080:** Store curated knowledge in a portable, versioned, human- and agent-readable representation.
- **FR-081:** Support concept links, citations, ownership, authority, confidence, freshness, valid-from/valid-to, supersession, and related code versions.
- **FR-082:** Treat vector, graph, relational, and full-text systems as rebuildable retrieval indexes.
- **FR-083:** Support progressive disclosure: index → summary → relevant sections → authoritative source.
- **FR-084:** Generate context packs for specific roles and steps with explicit token budgets.
- **FR-085:** Preserve retrieval provenance so an agent and reviewer can see exactly which knowledge influenced a decision.
- **FR-086:** Expose knowledge and tools through open protocols where useful; MCP is an access interface, not the knowledge store itself.
- **FR-087:** Update or challenge knowledge after validated code changes, incidents, decisions, and review findings.
- **FR-088:** Detect stale, conflicting, orphaned, and low-authority knowledge.

### 10.10 Multi-model and multi-agent behavior

- **FR-090:** Maintain a capability and performance profile per model and harness version.
- **FR-091:** Route using task type, risk, modality, context size, tool support, latency, cost, historical success, and policy.
- **FR-092:** Support patterns including single worker, proposer–critic, independent parallel proposals, debate, tournament, consensus, and adjudication.
- **FR-093:** Use multi-model execution selectively; it must not be mandatory for routine deterministic work.
- **FR-094:** Preserve independence by hiding one critic’s answer from another until their initial assessment is complete.
- **FR-095:** Record why a route was selected and whether escalation improved the result.
- **FR-096:** Allow new providers and future models to be added without changing workflow semantics.

### 10.11 Human collaboration and UI

- **FR-100:** Show current stage, state, owner, model, budget, elapsed time, blockers, dependencies, and next transition in real time.
- **FR-101:** Present a concise live summary while retaining access to raw events and artifacts.
- **FR-102:** Allow authorized humans to answer questions, edit specs or plans, approve gates, pause, cancel, and steer future steps.
- **FR-103:** Support shared sessions and comments so product, design, engineering, operations, and agents can align before and during implementation.
- **FR-104:** Show why an agent made a decision through linked context, artifacts, and evidence—not hidden reasoning.
- **FR-105:** Visualize the dependency graph and highlight conflicts, stalled units, repeated failures, and critical path.
- **FR-106:** Provide a replay view of completed missions.
- **FR-107:** Preserve links back to external tickets, code reviews, deployments, and incidents.

### 10.12 Continuous learning and kaizen

- **FR-110:** Cluster repeated failures, corrections, review comments, regressions, and high-cost patterns.
- **FR-111:** Propose improvements to specifications, context, skills, tests, prompts, routing, decomposition, and policies.
- **FR-112:** Convert validated historical defects into regression tests or policy checks when possible.
- **FR-113:** Replay representative historical tasks against proposed changes before promotion.
- **FR-114:** Compare candidate and control configurations using outcome metrics, not only model preference.
- **FR-115:** Version every prompt, skill, context template, evaluator, router, and policy.
- **FR-116:** Keep generated improvement candidates quarantined until required evaluation and approval complete.
- **FR-117:** Support offline “dreaming” jobs that search for missing tests, stale knowledge, architecture drift, repeated toil, and opportunities for automation.

### 10.13 Security and governance

- **FR-120:** Give each agent/run a distinct workload identity and least-privilege authorization.
- **FR-121:** Broker credentials so raw secrets do not need to enter model context.
- **FR-122:** Restrict filesystem, network, tools, repositories, paths, environments, and data sources by policy.
- **FR-123:** Separate read, propose, merge, deploy, and production-operate authority.
- **FR-124:** Require stronger gates for authentication, authorization, payments, secrets, data migrations, infrastructure, compliance, and destructive operations.
- **FR-125:** Support emergency stop, global pause, model disablement, key revocation, and task isolation.
- **FR-126:** Sign or otherwise attest released artifacts and preserve build provenance.
- **FR-127:** Make policy decisions deterministic, testable, versioned, and auditable.

---

## 11. Logical data architecture requirement

The requirement to “store everything” should be implemented as several cooperating logical stores rather than one database.

### 11.1 Operational state plane

Stores current Work Items, workflow state, leases, gates, retries, budgets, and resumable execution history. This plane must support low-latency transactional correctness.

### 11.2 Event plane

Stores and distributes immutable domain events and integration events. Events use versioned envelopes, correlation IDs, causation IDs, timestamps, actor identity, schema version, and artifact references.

### 11.3 Immutable artifact plane

Stores the large payloads: prompts, responses, streams, tool results, source snapshots, diffs, logs, test reports, screenshots, videos, binaries, environment captures, and evidence bundles. Artifacts should be content-addressed where practical.

### 11.4 Analytics lakehouse plane

Stores normalized events, spans, invocations, token/cost data, evaluations, outcomes, and derived features for large-scale analysis and kaizen. Apache Iceberg is a plausible table format for this analytical plane because of schema evolution and reproducible snapshots, but it should not be the only operational workflow or event store.

### 11.5 Search and trace projection plane

Provides fast timeline, trace, log, full-text, and operational queries. OpenTelemetry-compatible traces are a useful interoperability layer; long-term raw retention may live in the artifact/lakehouse planes.

### 11.6 Lineage and relationship plane

Represents relationships such as:

`request → spec → criterion → plan → work unit → session → invocation → artifact → commit → build → deployment → signal → lesson`

A graph index may be useful, but the underlying IDs and relationships must remain exportable and reconstructable.

### 11.7 Curated knowledge plane

Stores authoritative domain concepts, policies, architecture, decisions, service ownership, interfaces, runbooks, incidents, glossary, known failure patterns, and practices. A Git-versioned Open Knowledge Format-style bundle is a strong candidate for the portable source; graph/vector/full-text indexes can be generated from it and other authoritative sources.

### 11.8 Safety qualification for “everything”

“Complete logging” should mean complete provenance, not uncontrolled replication of credentials, regulated data, or unnecessary personal information. The system should store:

- exact raw content where policy allows;
- encrypted restricted content where retention is required;
- references or cryptographic attestations where duplicating the secret is unsafe;
- sanitized searchable projections for routine use.

One petabyte of capacity solves neither authority nor retrieval quality. The semantic model, lineage, classifications, and indexes are the actual product requirement.

---

## 12. Acceptance criteria and Definition of Done

### 12.1 Who creates acceptance criteria?

Acceptance criteria should be created during the **Specification and Evaluation Design stage**, before planning is approved.

- Product/domain roles own whether the desired behavior is correct.
- The specification agent drafts atomic criteria and identifies ambiguity.
- The architect owns technical invariants and system-level constraints.
- The evaluator role maps each criterion to an oracle and evidence.
- Security/operations roles add risk-specific criteria.
- A human or policy-defined accountable owner approves criteria for relevant risk classes.

The implementation agent may suggest improvements, but it must not silently redefine the target after seeing implementation difficulty.

### 12.2 Criterion schema

Each criterion should contain at least:

- stable criterion ID;
- originating requirement and spec version;
- plain-language statement;
- criterion class: business, functional, invariant, security, reliability, performance, usability, operability, migration, or documentation;
- severity: blocking, required, advisory;
- oracle type and location;
- precise pass condition;
- evidence required;
- owner;
- automation status;
- current result and artifact links.

### 12.3 Boolean completion

The factory can expose a final Boolean result, but it should be computed rather than guessed:

`DONE = all blocking gates pass AND all required criteria pass AND no unresolved prohibited risk exists`

The UI should preserve criterion-level detail rather than hiding it behind the final Boolean.

### 12.4 Evaluation hierarchy

Preferred order:

1. Formal or deterministic checks.
2. Property, contract, metamorphic, and model-based tests.
3. Reproducible integration or end-to-end experiments.
4. Runtime measurements and production verification.
5. Human judgment for product and risk decisions.
6. Rubric-based LLM judgment as supporting evidence when no stronger oracle exists.

### 12.5 Bounded convergence

“Work until yes” must be bounded and diagnostic:

1. Run the oracle.
2. Classify the failure.
3. Produce a targeted repair hypothesis.
4. Change the smallest relevant unit.
5. Re-run affected and regression checks.
6. After configured repeated failures, change model/strategy, revisit the plan/spec, or escalate to a person.

An unlimited loop can waste tokens, weaken tests, or optimize against a flawed judge.

---

## 13. TDD requirement

TDD is retained as a core design discipline because it forces observable component contracts and tends to expose coupling before implementation.

For behavior-changing work, the expected sequence is:

1. Select one criterion or invariant.
2. Write the smallest meaningful failing test/oracle.
3. Demonstrate the failure for the intended reason.
4. Implement the smallest compliant change.
5. Demonstrate the new test and relevant regression suite passing.
6. Refactor while preserving behavior.
7. Attach the red/green/refactor evidence to the work unit.

TDD should be a mandatory default, not an inflexible ritual. Policy-defined exceptions may include exploratory spikes, documentation-only work, generated code validated elsewhere, or legacy seams where characterization tests must precede true TDD. Every exception should be explicit and auditable.

---

## 14. Resumability model

Resumability is a first-class product property, not a feature added to agent chat.

### 14.1 Semantic checkpointing

Checkpoints occur after meaningful steps such as:

- request normalized;
- clarification answer accepted;
- specification version approved;
- acceptance criteria approved;
- plan version approved;
- work unit claimed;
- test demonstrated failing;
- change committed;
- evaluation completed;
- review gate passed;
- deployment verified.

Raw model streams may be retained, but replay should use semantic state rather than resend the entire history.

### 14.2 Resume Capsule

A provider-independent Resume Capsule should include:

- mission and work-unit goal;
- exact spec, plan, policy, prompt, skill, model-profile, and repository versions;
- completed and incomplete steps;
- decisions and rationale summaries linked to raw evidence;
- current workspace/branch/commit and environment manifest;
- current failing criteria and latest evaluator output;
- outstanding questions and blockers;
- remaining budget and permissions;
- recommended next action.

### 14.3 Side-effect safety

Every non-read action must be idempotent, deduplicated, or compensatable. The factory must know whether a commit, ticket comment, deployment, schema action, or external API mutation completed before retrying it.

---

## 15. Token and context efficiency

Token efficiency is a correctness and scale requirement, not merely a cost concern.

Required practices:

- progressive disclosure rather than full-context loading;
- role-specific Context Packs;
- symbol-, dependency-, and diff-aware code retrieval;
- authoritative summaries linked to raw sources;
- provider prompt caching where available without making it canonical state;
- stable context manifests and content hashes to avoid repeated transmission;
- retrieval budgets and explicit justification for large context;
- separate working memory, episodic run history, and curated semantic knowledge;
- compaction at semantic boundaries;
- feedback on which retrieved items were actually useful;
- no repeated multi-model review for tasks already settled by deterministic checks.

The desired form of GitHub Ace-like organizational context is a **shared social and decision fabric that agents can query**, not a monolithic prompt.

---

## 16. Multi-model architecture requirement

The factory should expose a normalized contract while preserving provider-specific strengths.

### 16.1 Common contract

Every adapter should support, where available:

- structured input and output;
- streaming;
- tool invocation;
- cancellation;
- token/cost reporting;
- context and output limits;
- reasoning/effort controls;
- multimodal inputs;
- prompt caching;
- provider session continuation;
- error and rate-limit semantics.

### 16.2 Capability registry

The router should reason from capabilities and measured outcomes, not brand names alone. A model profile should contain:

- supported modalities and tools;
- context/output limits;
- structured-output reliability;
- observed success by task class;
- latency and throughput;
- token and financial cost;
- failure modes;
- security/data-retention constraints;
- current availability and version.

### 16.3 Collaboration patterns

Use multi-model work where disagreement can improve quality:

- architecture proposals;
- threat models;
- ambiguous debugging;
- plan review;
- difficult migrations;
- qualitative product review;
- release adjudication.

Avoid multi-model debate for queueing, state transition, deterministic test execution, formatting, or routine operations.

---

## 17. Requirements disposition: keep, modify, defer, or drop

| Mind-dump idea | Disposition | Refined requirement |
|---|---|---|
| Use a ticket system or Taskwarrior | **Keep, modify** | Build intake adapters and a canonical Work Item model. Do not make an external tracker’s schema the factory’s internal ontology. Avoid building a full tracker first. |
| Watcher / dispatcher | **Keep** | Pure code/event consumer with leases, dedupe, idempotency, retry, and policy. No LLM in the hot queue-control path. |
| Smart triage agent | **Keep** | Bounded classifier and ambiguity detector after deterministic pickup. |
| Lead architect agent | **Keep, govern** | Logical role with explicit outputs, critics, approval thresholds, and no direct lifecycle authority. |
| Event-driven architecture everywhere | **Keep, constrain** | Durable orchestrated workflows own missions; events expose facts and connect systems. Avoid choreography-only spaghetti. |
| Store every action and trace | **Keep, qualify** | Complete provenance with immutable artifacts, lineage, encryption, classification, and sanitized indexes. Never duplicate raw secrets casually. |
| Iceberg | **Keep as candidate** | Strong candidate for analytical history/kaizen, not the sole workflow, event, search, or artifact store. |
| Graph DB + vector DB + RAG + MCP | **Modify** | Portable curated knowledge first; graph/vector/full-text as derived indexes; MCP as an access protocol. Do not equate four technologies with a knowledge strategy. |
| Token efficiency | **Keep** | Progressive disclosure, Context Packs, caching, compaction, retrieval budgets, and usefulness feedback. |
| Open source or self-built only | **Keep; clarify** | Apply to the control plane and infrastructure. Clarify whether proprietary paid model APIs are an intentional exception. |
| GitHub ACE-style shared context | **Keep** | Shared, collaborative workspace and queryable social/decision fabric; not indiscriminate context injection. |
| Dreaming / kaizen | **Keep, gate** | Offline improvement proposals, replay, experiments, and controlled promotion. No direct self-modification. |
| Boolean evaluation | **Keep, refine** | Boolean per criterion and computed overall Boolean backed by evidence. |
| Architect asks questions in ticket | **Keep** | Clarification loop is mandatory before a Definition-of-Ready gate. |
| Google OKF | **Keep as candidate** | Portable human/agent knowledge format and interchange layer; not a database replacement. |
| Spec-driven development | **Keep** | Lightweight, versioned, executable specifications focused on behavior and invariants; avoid document inflation. |
| Resumability | **Keep; non-negotiable** | Durable workflow history, semantic checkpoints, idempotent activities, and provider-independent Resume Capsules. |
| Microservices / RISC / SRP | **Keep at work-unit level** | Prefer small contracts and simple steps. Do not prematurely deploy every component as a microservice. “Microtasks, macro-architecture.” |
| Learn from Factory, Symphony, Cognee, Buzz, Tessl, etc. | **Keep** | Extract patterns and use eligible open components; do not reproduce vendor branding or depend on proprietary platforms. |
| Future-proof any-model architecture | **Keep; foundational** | Stable workflow semantics, adapter interfaces, capability registry, versioned policies, and exportable state. |
| Built-in multi-model collaboration | **Keep selectively** | Use independent proposals/critics/adjudication for risk and ambiguity; avoid default debate overhead. |
| Simple real-time UI | **Keep** | Progress, timeline, graph, evidence, cost, blockers, questions, approvals, and replay. |
| TDD religiously | **Keep, modify wording** | Mandatory default for behavior changes with auditable exceptions. Optimize for design quality, not test-count theater. |
| Idempotent IaC | **Keep** | Declarative output plus repeated-apply, drift, rollback, and environment evidence. |
| Build a new ticket system | **Defer** | Build only the factory-specific UI and canonical work model first; integrate existing open trackers through adapters. |
| Dedicated graph database on day one | **Defer** | Prove knowledge entities, relationships, retrieval queries, and freshness needs before adding a specialized graph engine. |
| Direct autonomous production from day one | **Drop as initial authority** | Deploy the factory in production on day one, but begin with bounded rights such as branch/PR creation and non-production deployment. Expand authority by measured class. |
| Million-way execution from day one | **Defer implementation** | Preserve horizontal and partitionable semantics, but validate correctness and recovery at smaller scale first. |

---

## 18. Landscape synthesis and lessons

This product should borrow concepts, not copy products.

### OpenAI Symphony and harness engineering

Useful lesson: make the issue/work system the human control surface, let agents pull durable work, and invest in agent-friendly repositories, automated tests, and guardrails. Symphony is an orchestration specification rather than a complete enterprise factory.

### Factory.ai

Useful lesson: treat the factory as a full loop from external signals through triage, planning, building, validation, shipping, monitoring, and new signals. Factory is a product inspiration, not an eligible open component under the current constraint.

### Stripe Minions

Useful lesson: production impact comes from deterministic rails, unattended execution, strong internal tooling, verification, and tasks that are scoped well enough for an agent to finish end to end. Stripe’s internal implementation is an architectural case study, not a reusable component.

### Ramp Inspect

Useful lesson: give agents complete, reproducible development environments and close the verification loop rather than stopping after code generation.

### GitHub Next Ace

Useful lesson: software creation is multiplayer. Product, design, engineering, and agents need shared plans, shared sessions, isolated cloud workspaces, live artifacts, and organization-level orientation before work reaches a giant review queue.

### Agentic Context Engineering (a different “ACE”)

There is a name collision. Agentic Context Engineering focuses on evolving playbooks through generation, reflection, and curation. Its lesson is relevant to the kaizen plane: execution traces should produce evaluated, curated context improvements rather than ever-growing chat history.

### Google Open Knowledge Format

Useful lesson: knowledge portability can be achieved with a minimally opinionated, Markdown-based format, normal links, progressive indexes, and producer/consumer independence. It can be the interchange/source layer while specialized indexes remain optional.

### GitHub Spec Kit

Useful lesson: specifications can be first-class inputs to implementation across many coding agents. The factory should adopt the principle while guarding against verbose, stale, or non-executable document generation.

### Omnigent

Useful lesson: a meta-harness can normalize different agents while enforcing policies, sandboxing, spend caps, shared history, and real-time collaboration outside prompts. Its Apache-2.0 status makes it a candidate for later technical evaluation, not an automatic selection.

### Cognee

Useful lesson: persistent agent memory benefits from combined relational, graph, and vector retrieval, citations, and explicit remember/recall/improve semantics. It should be evaluated against the factory’s knowledge ontology, temporal requirements, provenance, rebuildability, and operational simplicity.

### Tessl Agent

Useful lesson: continuously scan tickets, PRs, and session logs; convert repeated mistakes into context, skills, checks, and automation; and evaluate whether those improvements actually reduce recurrence. Its proprietary product can inspire the kaizen requirements but does not satisfy the open-component constraint.

### Claude Tag

Useful lesson: agents become more useful when they have a persistent, governed identity in shared team spaces, with access and memory boundaries. The factory should support this interaction pattern through open integrations rather than depend on one proprietary channel agent.

### Buzz

Public information is currently too limited to derive concrete architecture. Treat it as an emerging collaborative-agent product to monitor, not a design dependency.

---

## 19. Candidate Definition-of-Done profiles

These are preliminary requirement examples, not final implementation policy.

### 19.1 Application feature

- clarified and approved specification;
- every blocking criterion has an oracle;
- new behavior demonstrated failing before implementation where applicable;
- code compiles and static checks pass;
- relevant unit, property, contract, integration, and end-to-end tests pass;
- security and dependency checks pass;
- telemetry and error behavior are present;
- documentation and knowledge are updated;
- migration and rollback are validated where relevant;
- independent review passes;
- reproducible evidence bundle exists;
- post-deployment verification passes before final closure.

### 19.2 Infrastructure change

- desired state and invariants specified;
- plan and destructive actions identified;
- policy/security checks pass;
- dry run or plan is captured;
- repeated apply is idempotent;
- drift behavior is defined;
- rollback or recovery is tested;
- environment-specific secrets are brokered, not embedded;
- observability and ownership exist;
- deployment evidence is captured.

---

## 20. Candidate success metrics

Targets are intentionally unset until the interview establishes the initial domain and baseline.

### Outcome quality

- percentage of required criteria passed on first implementation attempt;
- escaped defect and rollback rate;
- regression rate within a defined period;
- reviewer-found severity distribution;
- spec-to-implementation gap rate.

### Autonomy and human load

- percentage of work completed with no intervention after Definition of Ready;
- human minutes per landed change;
- clarification effectiveness;
- number and type of escalations;
- review burden per change.

### Flow

- request-to-ready time;
- ready-to-change time;
- change-to-verified-production time;
- critical-path idle time;
- parallelism efficiency and conflict rate.

### Reliability

- successful recovery from injected crashes;
- duplicated side-effect rate;
- trace completeness;
- reproducibility of environments and evaluations;
- percentage of runs resumable without repeating completed steps.

### Intelligence efficiency

- tokens and cost per accepted criterion;
- retrieval usefulness rate;
- model escalation rate and benefit;
- repeated-context ratio;
- failure rate by model, task class, prompt/skill, and context version.

### Learning

- repeated-error recurrence rate;
- percentage of validated defects converted into durable checks or knowledge;
- improvement-candidate promotion success;
- stale knowledge rate;
- measured gain from routing/context/prompt changes.

---

## 21. Proposed prototype boundary — hypothesis only

This boundary is not approved and exists to make interview questions concrete:

- one organization;
- one or two representative repositories;
- one intake adapter plus native factory UI;
- branch/PR creation and non-production deployment authority;
- OpenAI/Codex, Claude, Gemini, and one open-source model adapter;
- deterministic dispatcher and durable mission state;
- clarification, spec, criteria, plan, work-unit DAG, TDD execution, evaluation, review package, and resume;
- complete trace/artifact capture for the selected repos;
- a small curated knowledge bundle and derived retrieval indexes;
- real-time mission UI;
- no unattended high-risk production deployment;
- no autonomous modification of active production policies.

The final prototype boundary depends on the interview.

---

## 22. Open product decisions

1. Does “open source or self-built” permit paid proprietary model APIs, provided the control plane and data plane remain open/self-hosted?
2. What is the first production domain, repository set, language stack, deployment platform, and regulatory environment?
3. What authority may the first release have: read-only, branch creation, PR creation, merge, staging deploy, canary, or production deploy?
4. Who is accountable for product intent and who can approve a Definition of Ready?
5. Which work classes should the first prototype support and explicitly reject?
6. What current source-control, CI/CD, ticket, chat, documentation, identity, and secret systems must be integrated?
7. What data is prohibited from leaving the organization or entering a model provider?
8. Does complete retention include personal data and secrets, or should policy permit reference/attestation instead of duplicated raw values?
9. What quality and throughput baseline exists today?
10. What is the smallest end-to-end outcome that would make the prototype undeniably valuable?
11. Is the primary operating model centralized factory ownership, team-owned pipelines on a shared platform, or a federation of both?
12. How much human approval is desired at specification, plan, code-review, and release gates?
13. Is the initial target greenfield software, brownfield repositories, infrastructure, or a mix?
14. Which non-functional requirements are mandatory from the first release: security, performance, availability, compliance, cost, data residency, or air-gap?
15. Is the knowledge system intended only for software engineering, or for broader business and product context as well?

---

## 23. Interview plan

### Round 1 — Mission and boundaries

Clarify open-source scope, first domain, first users, authority, data boundary, existing systems, and the definition of prototype success.

### Round 2 — Work and governance

Clarify supported work types, product ownership, clarification rules, approval gates, risk classes, and human responsibilities.

### Round 3 — Correctness

Clarify specification depth, test philosophy, acceptance oracle types, non-functional requirements, and Definition-of-Done profiles.

### Round 4 — Knowledge and learning

Clarify authoritative sources, knowledge ownership, retention, privacy, curation, organizational context, and kaizen promotion rules.

### Round 5 — Scale and experience

Clarify concurrency, latency, UI, notifications, collaboration, cost expectations, availability, and operational ownership.

After these decisions, this PRD can be promoted from discovery draft to an approved product contract. Only then should a separate technical architecture and phased implementation plan be created.

---

## 24. Referenced inspirations

- OpenAI, “An open-source spec for Codex orchestration: Symphony” — https://openai.com/index/open-source-codex-orchestration-symphony/
- OpenAI, “Harness engineering: leveraging Codex in an agent-first world” — https://openai.com/index/harness-engineering/
- Factory.ai, “Factory 2.0: From coding agents to software factories” — https://factory.ai/news/software-factory
- Factory.ai software factory product overview — https://factory.ai/product/software-factory
- Stripe, “Minions: Stripe’s one-shot, end-to-end coding agents” — https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents
- Ramp, “Why We Built Our Own Background Agent” — https://builders.ramp.com/post/why-we-built-our-background-agent
- Maggie Appleton / GitHub Next, “One Developer, Two Dozen Agents, Zero Alignment” — https://maggieappleton.com/zero-alignment
- Google Cloud, “How the Open Knowledge Format can improve data sharing” — https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing
- GitHub Spec Kit — https://github.com/github/spec-kit
- Agentic Context Engineering — https://github.com/ace-agent/ace
- Omnigent — https://omnigent.ai/
- Cognee — https://www.cognee.ai/
- Tessl Agent — https://tessl.io/agent/
- Anthropic, “Introducing Claude Tag” — https://www.anthropic.com/news/introducing-claude-tag
- OpenTelemetry Generative AI semantic conventions — https://opentelemetry.io/docs/specs/semconv/gen-ai/
- CloudEvents — https://cloudevents.io/
- Apache Iceberg — https://iceberg.apache.org/
- Temporal durable workflow execution — https://docs.temporal.io/workflow-execution

