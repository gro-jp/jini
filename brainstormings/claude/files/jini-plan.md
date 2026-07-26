# jini — Multiphase Build Plan

**Version:** 0.3 (final) · **Date:** 2026-07-26 · **Build capacity:** one human + agents (bootstrap strategy per PRD P1) · **Companions:** `software-factory-prd.md`, `jini-stack.md`, `jini-tasks.md`

Principles: every phase ends with **objectively verifiable exit criteria** (a human or agent can check each box without judgment calls). jini builds itself as early as possible — from Phase 1 onward, jini's own repo is tenant #1 and new jini features flow through jini's own pipeline at whatever autonomy tier it has earned. Timeboxes are estimates for solo+agents, not commitments.

---

## Phase 0 — Foundation (est. 2–3 weeks)
**Goal:** the machines exist, reproducibly. Everything hand-built, human-merged.

**Scope:** Incus host(s) provisioned; OpenTofu + Incus provider + cloud-init defines every instance: Forgejo (+ Actions runners), Postgres 17, Restate server, LiteLLM, MinIO, ClickHouse + otel-collector (trace hot path, D13 — provisioned now so 100% capture holds from the first agent session). Backups (pgBackRest → MinIO; MinIO versioning). jini monorepo scaffolded in Forgejo: cargo workspace (`jinid`, `kun`, `jini-sbx`, `hakam`, `jini-gates`, `jini-events`), CI green on hello-world. Network policy: sandbox profile default-deny egress except LiteLLM. Ops runbook v0 (as OKF-style concepts from day one).

**Out of scope:** any agent execution, any UI.

**Exit criteria:**
- [ ] `tofu apply` run twice from clean state → second plan is empty (idempotency gate passes on jini itself).
- [ ] Smoke script verifies health endpoints of all provisioned services (incl. ClickHouse/otel-collector); runs in CI nightly.
- [ ] A trivial PR to the monorepo builds, tests, and merges through Forgejo Actions.
- [ ] Postgres restore drill: destroy DB instance, restore from backup, smoke passes.
- [ ] Runbook covers: full cold start, backup/restore, service upgrade, break-glass stop.

**Risks:** Incus/OpenTofu provider gaps → fall back to cloud-init heavy lifting; keep provider pinned.

## Phase 1 — The Loop (est. 4–6 weeks)
**Goal:** one ticket travels end-to-end — clarify → spec → build → green PR — with humans at every gate. Resumability proven.

**Scope:** `jinid` v0: Forgejo webhook ingestion, ticket state machine (PRD F1.3) projected in Postgres, domain event store append path, one Restate workflow per ticket with Awakeables for requester-approval and CI-completion. `jini-sbx` v0 on the D12 decision: per-session sandbox from golden image (Rust+Node+PHP toolchains), snapshot/restore. `kun` v0 per D7 charter, including egress scrubber and per-step token accounting; steps journaled in Restate. Spec stage v0 (PRD F2): architect flow interviews requester in ticket comments (one question per turn), commits `SPEC.md` + failing acceptance tests, `spec-approved` label freezes them. Eval harness v0: 10 reference tickets (5 Rust, 3 TS, 2 PHP) with known-good outcomes.

**Out of scope:** auto-merge, mutation gates, knowledge layer, UI.

**Exit criteria:**
- [ ] Golden path demo, unassisted: file ticket → clarifying question answered → spec approved → `kun` implements in sandbox → PR opens with green CI → human merges.
- [ ] Resumability drill: `kill -9` the runner mid-implementation; on resume, ≤1 step is re-executed (verified from Restate journal + event log).
- [ ] Sandbox host reboot mid-session: session resumes from snapshot; same ≤1-step loss bound.
- [ ] Eval: `kun` completes ≥7/10 reference tickets to green without human code edits.
- [ ] 100% of model calls flow through LiteLLM; per-ticket token spend visible; 0 secrets in any stored trace (gitleaks sweep over trace dump).
- [ ] Acceptance-test freeze enforced: an agent commit touching acceptance tests flips ticket to `spec_reapproval` (integration test).

**Risks:** `kun` capability shortfall → iterate prompts/tools against eval before expanding scope; Restate Rust SDK pre-1.0 churn → pinned, vendored, upgrade only at phase boundaries.

## Phase 2 — Gates & Policy (est. 4–6 weeks)
**Goal:** "green" becomes evidence. `hakam` decides in shadow mode.

**Scope:** `jini-gates`: per-language runners (D16), mutation gates with per-repo thresholds, secret/dep scanning, flake detector + quarantine flow (PRD F4.7). Adversarial review v1: second provider critiques diff against spec; blocking findings post to ticket. `hakam` v1: Cedar policies for `merge_mode = f(harness_score, blast_radius)`; harness-score computation job; blast-radius classifier (path- and label-based rules, conservative defaults); every verdict a domain event. Trace viewer over ClickHouse (D13) inside the thin board v0 (SSE: ticket lanes, live step feed, spend, span drill-down). Shadow mode: `hakam` renders verdicts on every PR; humans still click merge; agreement tracked.

**Exit criteria:**
- [ ] Replay determinism: re-running `hakam` over the event log reproduces byte-identical verdicts for 100% of decisions.
- [ ] Seeded-defect drill: 20 injected mutants across languages → gate stack blocks ≥18; the ≤2 escapes get written up as gate tickets.
- [ ] Flake drill: a known-flaky test is auto-quarantined within N runs and a flake-fix ticket is filed; retry-until-green is demonstrably impossible (CI config test).
- [ ] Shadow-mode agreement: over ≥50 real PRs, `hakam` auto-merge verdicts agree with human decisions ≥95%; every disagreement has a written postmortem note.
- [ ] Board shows live progress for a running ticket end-to-end; page weight <200KB, no framework (D3 audit).

**Risks:** mutation runtimes on PHP/TS slow CI → scoped/incremental mutation runs; adversarial-review noise → tune to blocking-findings-only.

## Phase 3 — Autonomy & Knowledge (est. 4–6 weeks)
**Goal:** first unattended merge, and the factory starts learning.

**Scope:** Auto-merge live for low blast-radius classes on repos above harness bar (PRD F4.2/F4.4); self-demotion signals wired: flake-rate trend, mutation-score trend, revert detector, post-merge SLO probe for one pilot service behind flags/canary (PRD F4.6/F4.8). OKF bundle repo + Librarian agent; Qdrant index (D14) rebuilt from the bundle, served over MCP into `kun` context. ACE loop v1: nightly Reflector over traces → playbook-delta PRs → human-curated merge; playbook injected into prompts; uplift measured on the (now 20-ticket) eval. Harness-uplift program: jini files its own coverage/hermeticity tickets (PRD P2).

**Exit criteria:**
- [ ] First fully unattended merge of a real (non-synthetic) ticket, with complete audit trail reproducible from the event log alone.
- [ ] Self-demotion fire drill: inject degradation signal → affected repo/class demotes to human review automatically; alert fires; event recorded.
- [ ] Break-glass drill: operator pause halts all in-flight sessions ≤60s; resume drill passes afterward.
- [ ] Kaizen evidence: first-pass gate success on the eval set improves ≥10% relative after 4 weeks of ACE playbook accrual (vs. Phase-2 baseline, same model versions).
- [ ] ≥25 auto-merges accumulated with revert rate ≤ the org's human-PR baseline.

**Risks:** premature autonomy on a weak repo → harness bar is conservative and rises only via P2 evidence; playbook bloat → Curator token-budget cap on injected context.

## Phase 4 — Org rollout & Rails exit (est. 8+ weeks, ongoing)
**Goal:** everything onboarded; the flagship migration begins; jini is boringly operable.

**Scope:** all org repos onboarded with published harness scores; PHP uplift wave; Rails-exit program (PRD P3): inventory → strangler-fig module specs → migrations through the full pipeline at the high blast-radius tier; docs-by-factory (runbooks and OKF concepts maintained by jini); operator dashboards (spend, autonomy share, demotion history); sandbox pool tuning (pre-warm depth, snapshot cadence) if spawn latency hurts (D12).

**Exit criteria:**
- [ ] 100% of org repos onboarded; harness score + autonomy tier published per repo on the board.
- [ ] Auto-merge share ≥30% of merged PRs org-wide (PRD §8) with revert rate ≤ baseline sustained ≥4 weeks.
- [ ] First Rails-exit module migrated, deployed behind canary, and verified in prod by post-merge probes.
- [ ] Cold-start drill: rebuild the entire factory from IaC + backups on a fresh host in ≤1 day, documented.
- [ ] Every PRD §8 metric has a live dashboard and a recorded baseline.

---

## Standing tracks (all phases)
**Security:** scrubber before any external call (from Phase 1); quarterly secret-scan sweep of archives; sandbox escape review at each phase gate. **Model routing (config, revisit each release):** architect/hard-implementation = Opus-class high/xhigh; subagent chores = Sonnet-class low/medium; multi-day/architecture = Fable-class xhigh; adversarial review = distinct second provider. **Spend:** per-ticket caps enforced at LiteLLM; weekly cost-per-merged-PR review. **Docs:** every phase updates the OKF runbook concepts; drift between docs and reality is a P1 bug.
