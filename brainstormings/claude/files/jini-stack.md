# jini — Tech Stack & Architecture Decision Log

**Version:** 0.3 (final) · **Date:** 2026-07-26 · **Status:** all decisions locked · **Companion docs:** `software-factory-prd.md`, `jini-plan.md`, `jini-tasks.md`

Format: lightweight ADRs. Each decision records status, choice, rationale, and consequences. Coding agents: treat **Locked** decisions as constraints; never silently substitute alternatives.

---

## Sourcing rules (governing all decisions)

- **Rule S1:** Every component is open source or self-built.
- **Exception S1a:** Frontier model APIs (Anthropic / OpenAI / Google) — locked in PRD.
- **Exception S1b (new):** BSL/source-available runtimes admitted when self-hosted free of charge (adopted for D6 Restate).
- **Rule S2:** Prefer components written in Rust or operable as arm's-length services. We write Rust; we *run* polyglot.
- **Rule S3:** Every added service is an ops liability for a solo operator. Default answer to "should we add a service?" is no.

## Locked decisions

**D1 — Name: jini** — the pipeline stages remain **Refine → Author → Certify → Evolve** (spec, implement, gate, kaizen); the name is no longer a backronym. Crate/binary naming below.

**D2 — Implementation language: Rust** — single cargo workspace. Core crates: `jinid` (control-plane daemon, axum), `kun` (the agent loop — "Be!"), `jini-sbx` (sandbox manager), `hakam` (policy engine; Arabic: arbiter), `jini-gates` (gate runners), `jini-events` (event store lib). Toolchain: tokio, axum, sqlx, serde, tracing/OTel. Rationale: correctness-first (priority #1), static binaries (ops), org language, factory dogfoods its best-gated toolchain.

**D3 — Frontend: vanilla JS + Web Components + HTML/CSS** — no framework, no build step beyond esbuild-if-needed. Realtime via SSE from `jinid`. Scope guard: read-only board only (PRD F8.1); all writes go through Forgejo tickets.

**D4 — Forge/CI: Forgejo + Forgejo Actions** — self-hosted; issues are the control plane (PRD F1); webhooks drive `jinid`; Actions run CI. We do not build a ticket system (PRD §7).

**D5 — System of record: PostgreSQL 17** — ticket projections, harness scores, policy state, and the **append-only domain event store** (PRD F6.1, F6.4). Migrations via sqlx. LISTEN/NOTIFY feeds the SSE board.

**D6 — Durable execution: Restate** — server self-hosted single binary (BSL, exception S1b); Rust SDK (MIT/Apache-2.0), **pre-1.0: pin + vendor**. Mapping: ticket = workflow; agent step = journaled operation; approvals/CI/human-review waits = Awakeables; repo = Virtual Object (gives per-repo merge serialization). Boundary rule: Restate journal = *operational* checkpointing; Postgres event store = *semantic* audit truth. Never query Restate for audit.

**D7 — Agent harness: self-built thin loop (`kun`)** — charter (hard scope): prompt assembly (spec + OKF concepts + ACE playbook), tool executor (fs read/write/edit, bash, test-runner), context compaction, step checkpointing into Restate journal, OTel emission, per-step token accounting. Explicitly NOT a framework. Tool-calling via provider-native APIs through D9. MCP client via `rmcp` when knowledge layer lands (Phase 3). Rejected alternatives: goose (capability lag), OpenHands/opencode (polyglot service weight), Claude Code/Codex CLIs (proprietary binaries; would need exception S1c — declined).

**D8 — Host substrate: Incus** — one daemon for system containers (services) and KVM VMs; native stateful snapshots; projects for isolation; clustering available later. All services (Forgejo, Postgres, Restate, LiteLLM, ClickHouse, MinIO) run as Incus instances defined in IaC.

**D9 — Model gateway: LiteLLM (arm's-length service)** — sole egress path to model APIs. Provides provider-agnostic routing, per-ticket spend caps (token-cost bound, PRD §2.4), audit, and a zero-rearchitecture door to self-hosted open-weights. Routing table is config (see jini-plan §Model routing). ≥2 distinct providers for adversarial review (PRD F7.3).

**D10 — Policy engine: `hakam` = Rust + Cedar** — Cedar (Apache-2.0, formally verified core) evaluates `merge_mode = f(harness_score, blast_radius)`; harness-score computation and demotion signal handling are Rust around it. Every verdict is a domain event; replay must be byte-identical (PRD F4.1, F6.4). Test-freeze rule (PRD F2.3) enforced here: acceptance-test diffs force `spec_reapproval`.

**D11 — Message broker: none in v1** — Restate (durable invocations/timers) + Postgres (event store, LISTEN/NOTIFY) absorb the need. NATS JetStream is the named successor *if* fan-out demands emerge. (Rule S3 applied.)

**D15 — IaC: OpenTofu + Incus provider + cloud-init** — jini's own infra must pass its own gate: `tofu apply` twice → empty plan (PRD F4.9). Ansible only if a real gap appears.

**D16 — Gate tooling per language** — Rust: cargo test / clippy / cargo-mutants; TS/JS: vitest or repo-native / eslint / Stryker; PHP: PHPUnit / PHPStan / Infection; cross-cutting: gitleaks (secrets), osv-scanner + cargo-audit (deps). Flake detection: `jini-gates` reruns-on-history heuristic; quarantine via Forgejo labels.

**D17 — Secrets & egress** — sandboxes default-deny egress except LiteLLM gateway; `jinid` brokers short-lived per-session credentials; agents never see raw keys. Scrubber runs in `kun` before any payload leaves (PRD F3.3, F6.3).

## Locked decisions (final round)

**D12 — Sandbox: Incus VMs for all agent sessions** — `jini-sbx` drives the Incus REST API (unix socket). Session spawn = restore from the golden *stateful* snapshot; a pre-warmed pool of snapshotted VMs (configurable depth) keeps pooled spawn p95 ≤10s (AC in P1.7). Firecracker explicitly declined — one substrate for services and sandboxes, no second virtualization stack (Rule S3). Consequence: Phase-4 latency work is pool/image tuning, never new hypervisor code.

**D13 — Trace stack: OTel → ClickHouse + own viewer** — otel-collector + ClickHouse are provisioned in **Phase 0** so 100% capture (PRD F6) holds from the very first `kun` session. We own the span schema: OTel GenAI semantic conventions + jini extensions (ticket_id, step, model, tokens, cost). Viewer is a Web-Components panel in the board (D3). Cold tier: nightly ClickHouse → Parquet export into object-locked MinIO `traces-cold`. Langfuse declined (heavier self-hosted stack; schema ownership preferred).

**D14 — Knowledge index: Qdrant** — dedicated Rust vector DB, provisioned in Phase 3 via IaC; accessed with the `qdrant-client` crate; exposed to `kun` through the MCP knowledge tool (`rmcp`). Collections are **derived and disposable**, rebuilt from the OKF bundle (PRD F5.2); Qdrant snapshots ship to MinIO (its own backup story — accepted cost). Graph queries v1 = link traversal over the OKF bundle itself; cognee/graph-DB admitted only by future amendment if traversal proves insufficient.

## Amendment log
- 2026-07-26: S1b adopted (Restate). D11 decided by consequence of D6. D7 declines proprietary-CLI exception S1c.
- 2026-07-26 (final round): D12 locked — Incus VMs everywhere, Firecracker declined. D13 locked — ClickHouse + own viewer, Langfuse declined; ClickHouse/otel-collector pulled forward into Phase 0. D14 locked — Qdrant; graph layer deferred to OKF-link traversal, cognee only by future amendment.
