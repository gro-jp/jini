# jini — Task Breakdown

**Version:** 0.3 (final) · **Date:** 2026-07-26 · **Companions:** `software-factory-prd.md`, `jini-stack.md`, `jini-plan.md`

Conventions: `P<phase>.<n>` task IDs; `→` = depends on; each task carries an **AC** (acceptance check) an agent can verify. Phases 0–1 are fully decomposed (these are hand-built/human-merged); Phases 2–4 are decomposed to epic level — their fine-grained tickets will be authored *by jini's own spec stage* once Phase 1 exits (dogfooding per PRD P1). All ADRs are locked (jini-stack v0.3); no tasks are blocked.

---

## Phase 0 — Foundation

- **P0.1 Host prep** — install Incus on bare metal; storage pool (ZFS or btrfs), bridge network, `/dev/kvm` verified. AC: `incus launch` of a test VM and a test container both succeed.
- **P0.2 IaC skeleton** → P0.1 — OpenTofu project with Incus provider (pinned) + cloud-init templates; remote state in MinIO once P0.6 lands (local state until then). AC: `tofu apply` creates a disposable test instance; `tofu destroy` cleans it.
- **P0.3 Forgejo** → P0.2 — Incus instance; org `jini`; Actions enabled; 2 runner instances (one privileged-for-nested-virt runner profile for later sandbox tests). AC: webhook test fires to a netcat listener; hello-world Action runs green.
- **P0.4 Postgres 17** → P0.2 — instance + pgBackRest sidecar config; `jini` database; sqlx migration bootstrap (empty schema v0). AC: `sqlx migrate run` applies; backup job writes to local dir (MinIO target in P0.8).
- **P0.5 Restate server** → P0.2 — single-binary instance, data dir on pool; version pinned per D6. AC: `restate` CLI registers and invokes a sample service from a workstation.
- **P0.6 MinIO** → P0.2 — instance; buckets `traces-cold`, `backups`, `tofu-state`; versioning + object-lock on `traces-cold` (immutability, PRD F6.2). AC: versioned put/get; delete of locked object is refused.
- **P0.7 LiteLLM** → P0.2 — instance; providers configured via env-injected keys (keys live only here); per-key budgets on; request/response logging OFF at gateway (tracing happens in `kun` post-scrub, PRD F6.3). AC: completion via each provider through the proxy; a direct-to-provider call from the sandbox network profile is blocked (default-deny proof).
- **P0.8 Backups & drills** → P0.4, P0.6 — pgBackRest → MinIO schedule; restore runbook. AC: Phase-0 exit restore drill passes.
- **P0.9 Monorepo scaffold** → P0.3 — cargo workspace with empty crates per D2, CI (fmt, clippy -D warnings, test), CODEOWNERS, `docs/` seeded with OKF-style runbook concepts. AC: trivial PR merges through green CI.
- **P0.10 Smoke & nightly** → P0.3..P0.7, P0.11 — `jini-smoke` script checks all service healths; nightly Action. AC: smoke green in CI; failure alerts (email/webhook).
- **P0.11 ClickHouse + OTel collector** → P0.2, P0.6 — instances; jini span schema (OTel GenAI conventions + ticket_id/step/model/tokens/cost); nightly Parquet export → MinIO `traces-cold` (object-locked). AC: sample span posted to the collector is queryable in ClickHouse; export produces a locked object.

## Phase 1 — The Loop

**Epic A — Control plane (`jinid`)**
- **P1.1 Domain events** — `jini-events`: append-only Postgres event store (event_id, ticket_id, type, payload, hash-chain prev_hash), replay reader. AC: property test — replay of N random event streams reconstructs identical projections; chain verifies.
- **P1.2 Ticket state machine** → P1.1 — states per PRD F1.3 as a typed Rust enum; illegal transitions unrepresentable; projection table. AC: exhaustive transition test matrix; invalid transition = compile error or rejected event.
- **P1.3 Forgejo ingestion** → P1.2 — webhook handler (HMAC-verified) mapping issues/labels/comments → domain events. AC: replayed fixture webhooks produce expected event sequences.
- **P1.4 Restate workflow v0** → P1.2, P0.5 — `TicketFlow`: triage → clarify (Awakeable per question) → spec-approval (Awakeable on label) → build → PR → CI (Awakeable on webhook) → human-merge. AC: fake-agent integration test drives a ticket end-to-end; server restart mid-flow resumes correctly.
- **P1.5 Credential broker** → P1.4 — per-session short-lived Forgejo token minting; injection into sandbox at spawn; revocation on session end. AC: token scoped to single repo; expired token refused; token absent from any trace.

**Epic B — Sandbox (`jini-sbx`)** (D12: Incus VMs)
- **P1.6 Golden VM image** — Incus VM image: toolchains (Rust, Node, PHP, git), no credentials baked, egress profile default-deny+LiteLLM; booted-and-settled state captured as the golden *stateful snapshot*. AC: image and snapshot build reproducibly from script; egress test passes.
- **P1.7 Session lifecycle** → P1.6 — `jini-sbx` drives the Incus REST API: restore-from-golden-snapshot spawn, pre-warmed pool (configurable depth), workspace clone via brokered token, per-session stateful snapshot, restore, destroy. AC: spawn→snapshot→kill→restore round-trip preserves a mid-build cargo target dir; pooled spawn p95 recorded and ≤10s.

**Epic C — Agent loop (`kun`)**
- **P1.8 Loop core** → P0.7 — provider-native tool-calling via LiteLLM; tools: `read`, `write`, `edit`, `bash`, `run_tests`; context compaction at threshold; hard step/token budgets. AC: scripted-model harness (canned responses) exercises every tool path deterministically in CI.
- **P1.9 Scrubber & telemetry** → P1.8 — regex+entropy secret scrub pre-egress; OTel spans per step (model, tokens, cost, tool, duration) → collector. AC: planted secrets in workspace never appear in egress capture; spans queryable in ClickHouse for a full session.
- **P1.10 Journaled steps** → P1.8, P1.4 — each loop iteration runs as a Restate journaled operation keyed by session; resume replays journal, re-executes only the uncommitted step. AC: `kill -9` drill from jini-plan Phase-1 exit passes in CI (automated chaos test).
- **P1.11 Architect flow** → P1.8 — spec-stage prompt set: interview (one question/turn, posted as ticket comment via `jinid`), then `SPEC.md` + failing acceptance tests committed to a spec branch. AC: on the 10-ticket eval, specs contain runnable failing tests 10/10; freeze rule fires on acceptance-test edits (integration test with P1.2).
- **P1.12 Implementer flow** → P1.10, P1.7 — branch, implement to green locally, push, open PR with spec-linked description. AC: eval ≥7/10 tickets to green PR without human code edits.

**Epic D — Eval & exit**
- **P1.13 Reference eval set** — 10 tickets (5 Rust / 3 TS / 2 PHP) with golden acceptance tests, runnable via `jini-eval` command; results logged as events. AC: eval runs unattended and emits a scorecard artifact.
- **P1.14 Phase-1 exit drills** → all — automate the exit criteria from jini-plan as a single `jini-drills phase1` suite. AC: suite green.

## Phase 2 — epics (tickets to be authored by jini)
- **P2.E1** `jini-gates` runners + mutation thresholds (D16). **P2.E2** Flake detector + quarantine. **P2.E3** Adversarial review v1 (second provider). **P2.E4** `hakam`: Cedar policy set, harness-score job, blast-radius classifier, shadow mode + agreement tracking. **P2.E5** Trace viewer over ClickHouse + thin board v0 (SSE, Web Components). **P2.E6** Seeded-defect and flake drills as CI suites.

## Phase 3 — epics
- **P3.E1** Auto-merge enablement + policy config for low blast-radius. **P3.E2** Self-demotion signals + revert detector + pilot canary probe. **P3.E3** OKF bundle + Librarian + Qdrant index over MCP (`rmcp` + `qdrant-client`; Qdrant provisioned via IaC, snapshots → MinIO). **P3.E4** ACE Reflector/Curator nightly + playbook injection + uplift measurement. **P3.E5** Harness-uplift ticket generator. **P3.E6** Break-glass + demotion fire-drill suites.

## Phase 4 — epics
- **P4.E1** Org repo onboarding waves + score publication. **P4.E2** PHP harness uplift program. **P4.E3** Rails-exit: inventory → strangler-fig spec series → migration pipeline at high-tier gates. **P4.E4** Operator dashboards (spend, autonomy share, demotions). **P4.E5** Cold-start rebuild drill. **P4.E6 (optional)** Sandbox pool tuning: pre-warm depth, snapshot cadence, image slimming (D12).

---
*All decisions locked (jini-stack v0.3). Every Phase 0–1 task is executable now; Phase 2–4 tickets get authored by jini itself after Phase-1 exit.*
