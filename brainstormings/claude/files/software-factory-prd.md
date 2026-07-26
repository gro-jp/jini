# PRD — Org-Wide Autonomous Software Factory

**Version:** 0.1 (draft for review) · **Date:** 2026-07-26 · **Owner:** you · **Status:** awaiting approval before implementation planning

---

## 1. Vision

A self-hosted, event-sourced software factory where business requests become specifications, specifications become tested code, and code merges itself when — and only when — a deterministic policy engine judges the evidence sufficient. Humans set intent and review where the policy demands it; agents do the work; every action is recorded, replayable, and mined for continuous improvement. The factory is its own first tenant and builds itself.

## 2. Priority stack (governs every tradeoff)

1. **Correctness / determinism** — when in conflict, always wins.
2. **Autonomy level** — maximized, but only as evidence permits; must be able to retreat.
3. **Delivery speed.**
4. **Token cost** — bounded per ticket, never optimized at the expense of 1–3. Verification is the sanctioned place to spend.

## 3. Locked decisions (from interviews)

| Decision | Value |
|---|---|
| V1 intake scope | Everything from day one (all repos, all request types onboarded) |
| Merge authority | Full auto-merge on green gates via policy engine; **no permanent human gates** |
| Human involvement | Only where policy routes it (low harness score × high blast radius) |
| Component sourcing | Open source or self-built only; **frontier model APIs are the sole exception** |
| Org scale | 10–50 developers |
| Build capacity | One human + agents (bootstrap strategy mandatory) |
| Runtime | On-prem, bare metal (KVM available) |
| Target languages | Rust, TypeScript, JavaScript, PHP; Ruby/Rails legacy in phase-out |
| Storage posture | Store everything, forever, immutable; right-sized infra now, scale later |

## 4. Users & agent roles

**Humans:** Requester (business/PM — files requests, answers clarifications, approves specs), Developer (reviews PRs the policy routes to humans; can file tickets like anyone), Operator (you — runs the factory, holds break-glass).

**Agents:** Triage (classifies, routes, estimates blast radius), Architect (interviews requester, authors specs + acceptance tests), Implementer (builds inside sandbox until green), Adversarial Reviewers (independent models critiquing plan and diff), Librarian (curates knowledge bundle; runs the kaizen loop), Infra (IaC changes under the same gate regime), Harness-Uplift (self-assigned: raises repo harness scores).

## 5. Functional requirements

### F1 — Intake & control plane
- F1.1 All work enters as tickets in a self-hosted OSS forge (issues + git + CI + webhooks in one; candidate: Forgejo). We do **not** build a ticket system.
- F1.2 Dispatcher is deterministic code — a queue consumer, no LLM. LLMs appear only where judgment is required (triage, spec, review).
- F1.3 Ticket lifecycle is an explicit state machine (received → triaged → clarifying → spec-approved → building → verifying → merged/demoted-to-human → deployed → verified-in-prod), every transition an event.
- F1.4 Any human or agent interaction with a ticket happens through ticket comments/labels — the ticket is the API.

### F2 — Specification & clarification (SDD)
- F2.1 No implementation begins before an approved spec. The Architect interviews the requester **on the ticket**, one question at a time, until ambiguity is resolved.
- F2.2 A spec contains: intent, constraints, blast-radius class, and acceptance criteria **written as executable, initially-failing tests**. The test suite is the Definition of Done.
- F2.3 Spec approval by the requester freezes the acceptance tests. **Any later change to acceptance tests re-triggers spec approval.** (Anti-test-tampering; existential under auto-merge.)
- F2.4 Unit of work = smallest independently verifiable change: one spec → one green PR. No RISC-style micro-decomposition within a change; parallelism happens **across** tickets.

### F3 — Execution
- F3.1 Every session runs in an isolated microVM sandbox (bare-metal KVM; Firecracker-class) with the full dev toolchain, spawn time in seconds, filesystem snapshot/restore.
- F3.2 Closed-loop verification inside the sandbox: agents run builds, tests, linters, and (for frontend) visual checks before ever opening a PR.
- F3.3 Credentials are brokered by the harness; agents never hold raw secrets. All model-API egress passes through a scrubber.
- F3.4 **Resumability (non-negotiable):** durable-execution workflow checkpoints every step (candidate: Temporal); sandbox snapshots preserve in-flight state; progress notes/artifacts are written back to the ticket. Conversation history is never load-bearing state. Any interruption (token limit, session cap, reboot) loses at most the current micro-step.

### F4 — Verification & merge policy
- F4.1 Merge authority is **policy-as-code**: deterministic, versioned, replayable. No LLM in the merge decision.
- F4.2 `merge_mode = f(harness_score(repo), blast_radius(change))`. Earned autonomy: auto-merge is granted per repo × change-class when evidence supports it, else routed to human review.
- F4.3 Harness score is measured per repo: coverage, test hermeticity, flake rate, mutation score — language-aware rubric (Rust ≻ TS/JS ≻ PHP expected at start).
- F4.4 Blast-radius classes: low (docs, internal tools) / medium (flagged product code) / high (auth, secrets, payments, destructive data ops, public APIs, IaC applies). High class demands near-ceiling harness scores plus the full gate stack. No class is permanently human-gated — per decision.
- F4.5 Gate stack for auto-merge eligibility: spec acceptance tests green → mutation/fault-injection check (tests must kill injected defects) → adversarial multi-model review of the diff → security gates (secret scan, dependency audit, sandbox-verified build) → policy verdict.
- F4.6 **Self-demotion:** degradation signals (rising flake rate, falling mutation score, prod incident attributed to a factory PR) automatically downgrade the affected repo/class to human review. Autonomy that cannot retreat violates priority #1.
- F4.7 Flake management is first-class: detection, quarantine, and flake-fix tickets. Retry-until-green is treated as gate-gaming and blocked.
- F4.8 Auto-merge ≠ naked auto-deploy: feature flags, canary, telemetry watch, automatic rollback on SLO breach. Post-merge verification closes the loop and feeds F4.6.
- F4.9 IaC gate: apply-twice-plan-clean (idempotency proof) required for infra changes.
- F4.10 Break-glass: operator can pause the factory globally or per repo; every override is itself an event.

### F5 — Knowledge & learning (kaizen)
- F5.1 Source of truth is an OKF-style markdown knowledge bundle in git — atomic, cross-linked concept files, updated by humans and agents via PRs (the Librarian curates).
- F5.2 Vector and graph indexes (candidates: cognee, pgvector) are **derived, disposable** artifacts rebuilt from the bundle, served to agents over MCP.
- F5.3 ACE-pattern learning loop: a Reflector periodically mines traces for wins/failures; a Curator turns lessons into playbook-delta PRs against the bundle; approved playbooks are injected into future agent contexts. Uplift is measured, not assumed.

### F6 — Observability & the archive
- F6.1 Event-sourced backbone: every state change is an immutable event on a durable log (right-sized: NATS JetStream or Postgres-backed queue — not Kafka).
- F6.2 100% capture: every prompt, response, tool call, artifact, decision, and policy verdict, under OpenTelemetry GenAI conventions. Hot store for debugging/UI (candidate: Langfuse/ClickHouse); cold immutable archive on MinIO. Iceberg deferred until volume demands it.
- F6.3 **Redaction at ingest** (secrets, credentials, PII) before anything is persisted or leaves the building. A trace lake without a scrubber is a breach amplifier.
- F6.4 Every merge decision must be reproducible from the archive alone (audit requirement).

### F7 — Model layer
- F7.1 Provider-agnostic proxy (candidate: LiteLLM) is the only path to models: routing, per-ticket spend caps, audit, and a zero-rearchitecture door to self-hosted open-weights later.
- F7.2 Routing table is configuration, not code. V1 defaults: Opus 5 high/xhigh for architect + hard implementation, Sonnet-class low/medium for subagent chores, Fable 5 xhigh reserved for multi-day/architecture runs; revisit on every model release.
- F7.3 Multi-model adversarial review uses ≥2 distinct providers on high-blast-radius diffs.
- F7.4 Provider data-retention terms reviewed; zero-retention agreements where offered.

### F8 — Interface
- F8.1 Realtime progress view = thin read-only web board subscribed to the event stream. All writes go through tickets. No custom workspace app.

## 6. Special programs
- **P1 Factory builds itself:** the factory repo is tenant #1; v0 (hand-built harness, human merges) builds v1 through its own pipeline.
- **P2 Harness uplift:** self-assigned tickets raising repo harness scores — the factory works to expand its own autonomy.
- **P3 Rails exit:** the Ruby/Rails phase-out is the flagship workload — long-horizon, spec-able, mechanically verifiable, and a deliberate stress test of the high-blast-radius policy tier.

## 7. Explicitly dropped
- Building our own ticket system (forge issues suffice) and any custom chat workspace (Buzz-class scope).
- Kafka-scale streaming and petabyte lake infrastructure in v1 (semantics now, heavy plumbing when volume arrives).
- RISC-style micro-step decomposition within a change (token-inefficient, drift-prone; conflicts with priority #1).
- Permanent human gates (replaced by blast-radius-weighted policy + self-demotion, per decision).
- Custom rich UI beyond the read-only board; self-hosted model serving in v1 (interface kept open via F7.1).
- Commercial platforms (factory.ai, Tessl SaaS, Claude Tag, etc.) as components — inspiration only.

## 8. Success metrics (initial targets; revisit at each phase gate)
- ≥95% of intake reaches an approved spec without human escalation beyond the requester.
- Auto-merge share of merged PRs: ramps from 0% (v0) to ≥30% (pilot exit) to policy-determined ceiling.
- Revert/incident rate of auto-merged PRs ≤ human-merged baseline (hard requirement — breach triggers F4.6).
- 100% of merge decisions reproducible from the archive; 0 unredacted secrets in stored traces.
- Resume-from-interruption success ≥99%, max loss = one micro-step.
- Median spec-approval → green-PR lead time and cost-per-merged-PR: tracked from day one, targets set after baseline.
- Kaizen loop demonstrates measurable uplift (e.g., first-pass gate success rate) within two months of P1.

## 9. Top risks
- **Gate gaming** (test edits, retry-until-green) → F2.3, F4.7, test-diffs classed high blast radius.
- **Weak PHP harnesses stall autonomy there** → P2 prioritizes PHP repos; expectation set that PHP earns auto-merge last.
- **Solo-operator bus factor** → factory documents itself (runbooks as OKF concepts, generated and verified by the factory).
- **Provider outage/regression** → F7 multi-provider routing; pinned model versions per repo until re-evaluated.
- **Frontier > published practice** (full auto-merge exceeds anything documented at scale) → mitigated by earned autonomy, self-demotion, post-merge rollback; accepted knowingly.

## 10. Deferred to the implementation plan
Final stack selections (forge, workflow engine, queue, trace store, sandbox tech, graph/vector components), phase breakdown with per-phase evaluation criteria and exit gates, harness-score rubric details per language, policy-engine rule format, budget caps, and the v0 bootstrap task list.

---
*Approve, amend, or strike — every requirement above traces to an interview answer or an agreed pushback. Next artifact: the implementation plan.*
