# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this workspace is

A documents-only planning workspace for designing an **org-wide autonomous software factory** — a system where tickets become specs, specs become tested code, and a deterministic policy engine decides merges/deploys with minimal human involvement. There is no code here: no build, lint, or test commands.

It is a git repository; the remote is GitHub `gro-jp/jini`. Changes land on `main` via pull request (`gh pr create`), not by pushing to `main` directly.

The same design brief was given in parallel to three AI assistants. Each track's output lives in its own directory under `brainstormings/` and is a **competing alternative, not part of one consistent spec**:

- `brainstormings/gemini/gemini-tech-guides.md` — Gemini's final deliverable: "The Factory" Master Technical Blueprint **v4.0**. Prescriptive stack (Rust/axum + Restate, Incus sandboxes with ZFS snapshot-rollback, self-built "Thin Loop" harness, host-side CLI multiplexer pooling $200/mo subscriptions, Postgres+Apache AGE, Qdrant, ClickHouse→Iceberg, vanilla-JS Web Components UI) plus a 4-phase implementation plan.
- `brainstormings/gemini/gemini-full-session.md` — raw transcript of the Gemini session that produced it. Contains **superseded** blueprint versions v2.0/v3.0 and the decision debates (Restate vs Temporal vs Windmill vs DBOS, Incus vs k3s vs NixOS, harness options, subscription strategy). Ends with a data-URI export of v4.0 — which is exactly what `gemini-tech-guides.md` is. Quote v4.0, not the embedded older versions.
- `brainstormings/claude/` — Claude's track, codename **jini** (Refine → Author → Certify → Evolve): `software-factory-prd.md` (PRD v0.1) plus `files/` holding the full doc set: `jini-stack.md` (locked ADRs D1–D16: Forgejo forge, Postgres 17, Restate, LiteLLM, MinIO, ClickHouse, Cedar policy engine), `jini-plan.md` (Phases 0–4 with objectively checkable exit criteria), `jini-tasks.md` (task breakdown with acceptance checks), and a byte-identical duplicate of the PRD. Planned Rust crates: `jinid` (control-plane daemon), `kun` (agent loop), `jini-sbx` (sandbox manager), `hakam` (policy engine), `jini-gates`, `jini-events`. Also holds full claude.ai session transcripts behind this track (dumped from claude.ai share links via the chat-snapshot API; `web_fetch`/`view`/`str_replace` tool inputs are stripped by the share mechanism): `claude-session-open-source-ai-factory-solutions.md` (open-source dark-factory landscape survey) and `claude-session-model-and-effort-selection.md` (model/effort strategy, the interview rounds via interactive questions, and the authoring of the PRD + jini docs — their full text is embedded in the `create_file` calls).
- `brainstormings/codex/` — OpenAI Codex's track: model-agnostic discovery PRDs that **deliberately select no stack**. `-v0.2.md` supersedes `-v0.1.md` (incorporates interview Round 1; Rounds 2–5 planned, Round 2 next: canary authority, deployment substrate, customer-data definition). New revisions are added as new `-v0.N.md` files, not edited in place. Also holds full ChatGPT session transcripts behind this track (`codex-session-*.md`, dumped from chatgpt.com share links; web-tool outputs are redacted by the share mechanism): `software-factory-model-strategy` (the main brainstorm — model/effort choice, the wish-list mind-dump, and the Round-1 interview answers that fed the PRD), `factory-ai-open-source` (open-source dark-factory landscape survey), and `codex-cli-headless-mode` (short Q&A on `codex exec`).

## How the tracks relate (read before editing or synthesizing)

All three agree on the core doctrine: deterministic control plane with LLMs only where judgment is required; durable/resumable execution (all pick or shortlist Restate/Temporal-class engines); spec-first + TDD with executable acceptance criteria frozen at approval; 100% provenance/trace capture with redaction at ingest; everything open-source or self-built **except** frontier-model APIs; sandboxed execution with snapshot/rollback; a kaizen loop that mines traces into curated knowledge.

They deliberately diverge on fundamentals — do not "fix" one track to match another; synthesis belongs in a new file, not in edits to a track's deliverable:

- **Intake:** Gemini polls Taskwarrior/Zulip (no inbound webhooks); jini uses self-hosted Forgejo issues + webhooks; Codex integrates the org's existing Laravel ticket app + GitLab.
- **Human gates:** Gemini mandates a human plan-approval gate ("never automated"); jini locks **no permanent human gates** (policy-as-code, earned autonomy, self-demotion); Codex stops autonomous authority at bounded production canaries.
- **Prescriptiveness:** Gemini and jini lock tech stacks (with conflicting choices, e.g. Apache AGE graph vs. "defer graph DB"); Codex's PRD is requirements-only by design.

## Org constraints shared by all tracks

10–50 developer org; the factory is built by one human operator + agents and is its own first tenant. On-prem bare metal with KVM. Existing systems: self-built Laravel ticketing app, GitLab + GitLab Runners + Jenkins, Slack, Keycloak, Markdown docs in a monorepo. Target languages Rust > TS/JS > PHP; legacy Ruby/Rails phase-out is the flagship workload. Greenfield preference: Rust + Axum backends, vanilla JS Web Components frontend, no frameworks. All documents are dated 2026-07-26.
