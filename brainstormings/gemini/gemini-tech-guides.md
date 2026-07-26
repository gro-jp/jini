# 🏗️ MASTER TECHNICAL BLUEPRINT: "The Factory" v4.0

**Project Type:** Autonomous Event-Driven Software Assembly Line  
**Target Audience:** Autonomous AI Developer Agents (Claude 3.5 Sonnet, Fable, Opus, Gemini) & Human Lead Architects  
**Core Philosophy:** 100% Rust Backend, Zero-Bloat Vanilla JS, Restate-Driven Resumability, Incus Sandboxing, Cost-Arbitrage Multiplexing, and Strict Lineage Tracking.

---

## 1. SYSTEM ARCHITECTURE & TECH STACK CONSTRAINTS

**🔴 DIRECTIVE FOR AI AGENTS: DO NOT DEVIATE from these technologies without explicit human authorization. Do not invent custom architectures, do not introduce NodeJS, Python backends, or heavy frontend frameworks.**

### 1.1 Core Backend & Orchestration
*   **API & Workers:** 100% Rust (Edition 2021) using the `axum` web framework on the `tokio` async runtime.
*   **Orchestration Engine:** **Restate** (`restate.dev`). Use the official `restate-sdk-rust`. Restate is the sole authority on state, retries, and durable execution. Do not implement manual `while` loops in memory for long-running processes; use Restate's native durability and `ctx.awakeable()` for human-in-the-loop gates.
*   **Intake Polling:** No inbound webhooks to prevent security exposure. Restate durable timers will securely poll internal ticket systems (e.g., Taskwarrior, Zulip) to initiate workflows.

### 1.2 Execution Substrate & Sandboxing (The Factory Floor)
*   **Bare-Metal Host:** Linux running **Incus** (the open-source, community-driven successor to LXD).
*   **Sandboxing Mechanism:** Interact exclusively via the local Incus REST API or Unix socket.
    *   **Hot Path (Code Generation & TDD):** Ephemeral **LXC System Containers** for rapid code compilation, testing, and standard loops (sub-second boot times).
    *   **IaC Dry-Runs:** Full **KVM MicroVMs** (via Incus) for Infrastructure-as-Code dry-runs (e.g., Terraform, Kubernetes).
*   **State Management (The ZFS Circuit Breaker):** Utilize **Instant ZFS Snapshots** natively via Incus. Before running untrusted AI code or tests, snapshot the container. If the test fails (`exit != 0`), perform a sub-second ZFS rollback to guarantee a pristine state. This mathematically prevents hallucination drift and dirty file systems.
*   **Agent Harness:** A self-built **"Thin Loop"** binary written in Rust. It runs *inside* the Incus sandbox, receives shell commands from Restate, executes them, and returns `stdout`/`stderr` and the integer `exit code`. It holds no conversation state.

### 1.3 AI Gateway & Cost Strategy (The Multiplexer)
*   **AI Multiplexer (Custom Rust Binary):** A host-side load balancer to pool and orchestrate multiple $200/mo enterprise/ultra subscriptions (Claude Team, Gemini Ultra). This achieves massive compute arbitrage compared to pay-per-token APIs.
*   **Execution Method:** The Multiplexer executes official CLI tools (e.g., `claude`, `antigravity`) as stateless, one-shot subprocesses on the host machine (e.g., `claude -p "prompt"`). 
*   **Isolation Rule:** AI CLIs are kept *outside* the sandbox. Each subscription uses a dedicated configuration directory (`/opt/factory/auth/claude_seat_X`) on the host. This prevents ZFS rollbacks inside the sandbox from wiping the CLI's internal auth tokens or background state.

### 1.4 Data Layer, Memory & Telemetry (1PB Scale)
*   **Relational & Graph State:** **PostgreSQL 16** + **Apache AGE** extension. Accessed via `sqlx` in Rust, utilizing Cypher queries inside standard SQL for GraphRAG memory traversals.
*   **Vector Database (Hot Context):** **Qdrant** (Dedicated Rust binary). Supports memmap storage for massive scalability with low RAM footprint.
*   **Hot Tracing:** **OpenTelemetry (OTel)** emitted natively from the Rust `tracing` crate -> **ClickHouse** (hyper-optimized C++ columnar database for hot tracing and lineage DAG storage).
*   **Cold Storage:** ClickHouse natively flushes aged telemetry to **Apache Iceberg** (Parquet files) for permanent, cheap petabyte-scale archival.

### 1.5 Frontend UI (The Control Room)
*   **Framework:** Vanilla JavaScript (ES6+), Native Web Components (`customElements`), Shadow DOM, standard HTML/CSS.
*   **Constraint:** **ZERO framework bloat.** No React, Vue, Next.js, Node.js servers, or NPM bundlers. Axum serves the static assets and handles WebSockets (`tokio-tungstenite`) directly.

---

## 2. THE SEMANTIC WORK TAXONOMY & LINEAGE GRAPH

To prevent context-window bloat, "God Prompts" are strictly forbidden. Work must adhere to a strict taxonomic hierarchy based on advanced agentic software engineering principles.

### 2.1 The Execution Hierarchy (Data Models)
1.  **Request:** The raw business signal / Canonical Work Item (from Taskwarrior/Zulip).
2.  **Mission:** The triaged, clarified intent.
3.  **Plan:** The versioned, Markdown-based specification.
4.  **Work Stream:** A logical grouping of architectural units.
5.  **Work Unit:** A discrete, testable component (Acceptance criteria + evaluation design).
6.  **Durable Step:** A Restate-managed state transition (e.g., write code, run test).
7.  **Tool/Model Invocation:** The raw LLM prompt or Thin Loop execution command.

### 2.2 The Lineage Graph Schema (Kaizen Memory)
Every completed Request must map to this exact property graph in PostgreSQL + Apache AGE. This is how the AI learns from past mistakes (GraphRAG):
`(:Request)-[:CLARIFIED_BY]->(:Clarification)-[:LED_TO]->(:Specification)-[:DEFINED_BY]->(:Criterion)-[:FULFILLED_BY]->(:Plan)-[:DIVIDED_INTO]->(:WorkUnit)-[:EXECUTED_IN]->(:AgentSession)-[:YIELDED]->(:Artifact)-[:RESULTED_IN]->(:Lesson)`

---

## 3. THE TYPED STATE MACHINE (Workflow Routing)

The Restate Virtual Object (`IssueLifecycle`) dictates the factory flow. Transitions are validated and strictly typed.
1.  **`Triaging`**: Reads `AGENTS.md` + context + Request -> Generates Specification.
2.  **`Classified`**: Generates strict TDD Tests (Acceptance criteria).
3.  **`PlanGenerated`**: Generates Architecture. Triggers *Shift-Left Adversarial Review* loop.
4.  **`Approved`**: A HUMAN APPROVES. Never automated.
5.  **`Implementing`**: Parallel TDD execution loops in Incus sandboxes per `Work Unit`.
6.  **`PrOpen`**: Runtime verification and independent multi-model Tribunal review.
7.  **`Releasing`**: Merged and deployed.
8.  **`Done`**: Kaizen knowledge update and graph generation.

---

## 4. PHASE-BY-PHASE IMPLEMENTATION PLAN

### 🟦 PHASE 1: Infrastructure, State Machine & Substrate (Zero AI)
**Objective:** Establish the Rust workspace, Restate engine, and the typed State Machine. Prove Incus ZFS rollbacks work programmatically.

#### Developer Checklist:
- [ ] **Step 1.1: Local Environment.** Deploy Postgres+AGE, Qdrant, and ClickHouse via `docker-compose.yml`. Install the Restate server and `incusd` natively on the bare-metal host.
- [ ] **Step 1.2: Rust Workspace.** Initialize Cargo workspace: `factory_api` (Axum + Restate logic), `factory_multiplexer` (Subscription gateway), and `factory_sandbox` (Incus controller).
- [ ] **Step 1.3: Typed State Machine.** In `factory_api`, define the Restate Virtual Object mapping to the 8 states defined in Section 3. Use Rust Enums to guarantee type safety across transitions.
- [ ] **Step 1.4: Sandbox Controller.** In `factory_sandbox`, build the execution logic to communicate with the Incus API: spawn an ephemeral LXC container, take a ZFS snapshot, run the Thin Loop binary, capture the `exit code`, rollback the snapshot, and destroy the container.
- [ ] **Step 1.5: Polling Intake.** Write a Restate daemon (timer loop) to securely poll Taskwarrior/Zulip. Map incoming tickets to a `Request` struct and trigger the `IssueLifecycle`.

#### Phase 1 Verification Criteria:
*   [ ] Axum server, Restate, and all databases connect seamlessly.
*   [ ] The system polls a dummy ticket, mounts an Incus container, runs `echo "test"`, captures `exit 0`, and destroys the container in under 2 seconds. No LLMs used.

---

### 🟨 PHASE 2: The Taxonomic Assembly Line (The Pre-Code Loop)
**Objective:** Wire up the LLM multiplexer, implement the taxonomic breakdown, and enforce the "Acceptance Criteria First" rule with a human approval gate.

#### Developer Checklist:
- [ ] **Step 2.1: Gateway Integration.** Point the Rust `reqwest` client to the Multiplexer. Ensure Multiplexer manages concurrent $200/mo CLI accounts via distinct config directories on the host.
- [ ] **Step 2.2: The `AGENTS.md` Policy.** The `Triaging` state reads `AGENTS.md` from the target repository and injects it into the Architect's System Prompt to define coding standards.
- [ ] **Step 2.3: Triaging to Plan.** Implement the Restate state transitions (`Triaging` -> `Classified` -> `PlanGenerated`) mapping to the hierarchy in Section 2.1.
- [ ] **Step 2.4: Shift-Left Adversarial Review.** While in `PlanGenerated`, trigger Gemini Deep Think to attack the Plan and Architecture Markdown. The Architect resolves findings in a loop until the architecture is mathematically sound.
- [ ] **Step 2.5: The Human Gate.** The workflow durably pauses using Restate's `ctx.awakeable()`. A human clicks "Approve" in the Vanilla JS UI. State moves to `Approved`.

#### Phase 2 Verification Criteria:
*   [ ] The system successfully generates a complete hierarchical plan for a feature request (Specs -> Tests -> Work Units).
*   [ ] The Restate workflow halts indefinitely at `PlanGenerated` until a mock approval payload is sent via Axum to fulfill the awakeable promise.

---

### 🟧 PHASE 3: Implementation, TDD & Verification
**Objective:** Implement the ZFS-backed TDD loop, execution sandboxes, and runtime verification (`PrOpen` state).

#### Developer Checklist:
- [ ] **Step 3.1: Implementing (The Circuit Breaker Loop).** For each `Work Unit`, execute the following durable loop in Restate:
    *   AI writes code to pass the generated criteria.
    *   Incus pushes code and runs the Thin Loop (`cargo test`, `pytest`, etc.).
    *   If `exit == 0`, mark Work Unit complete.
    *   If `exit != 0`, **Trigger an Incus ZFS rollback to wipe the dirty state**, increment the fail count, and append `stderr` to the prompt.
    *   If `fail_count == 5`, abort the task, durably halt, and route back to the Architect.
- [ ] **Step 3.2: Parallel Tribunal (`PrOpen`).** Use `tokio::join!` wrapped in Restate contexts to query the multi-model swarm (Claude, Gemini, Codex) simultaneously with the final diff. Evaluate for security, SOLID principles, and UX. If any model returns `approved: false`, aggregate the feedback and route back to `Implementing`.
- [ ] **Step 3.3: Incus KVM MicroVMs.** For Work Units tagged `infrastructure`, instruct Incus to launch a **KVM Virtual Machine** instead of an LXC. Inject short-lived IAM tokens and execute `terraform plan` or `kubectl apply --dry-run`.

#### Phase 3 Verification Criteria:
*   [ ] Submit a task with failing logic. The Factory loops, restores the ZFS snapshot each time for a clean slate, fixes the bug on attempt 2 or 3, passes the test, and completes.
*   [ ] **Resumability:** Kill the Restate server process mid-loop. Reboot it. Verify it resumes the exact loop iteration without losing `fail_count` state.

---

### 🟥 PHASE 4: The Lineage Graph (Kaizen Memory) & UI
**Objective:** Implement the definitive GraphRAG memory system using the explicit Lineage Taxonomy and build the zero-bloat UI.

#### Developer Checklist:
- [ ] **Step 4.1: Telemetry & Tracing.** Ensure all Rust `axum` and `restate` functions are instrumented with `tracing` spans, exporting OTel data directly to ClickHouse.
- [ ] **Step 4.2: The Lineage Pipeline.** Write a scheduled Restate cron job that reads ClickHouse telemetry and upserts the exact Lineage Graph (from Section 2.2) into Apache AGE via Cypher `sqlx` queries. Cold data flushes to Iceberg.
- [ ] **Step 4.3: Vector Sync.** Embed the `Artifact` and `Lesson` nodes using the LLM Multiplexer and store them in **Qdrant**, storing the Postgres Node ID as the vector payload.
- [ ] **Step 4.4: MCP Context Injection (Continuous Learning).** Before Phase 2 generates a Plan, the Architect queries Qdrant for similar historical `Lessons`, traverses the Apache AGE graph to find the exact `Artifacts` and `Criteria`, and injects this context to prevent repeating past mistakes.
- [ ] **Step 4.5: Web Components Control Room.** Create the Vanilla JS UI (`<factory-dag-visualizer>`). Use `tokio-tungstenite` WebSockets to stream live Restate state changes and Incus CLI outputs to the browser without any frontend framework bloat.

#### Phase 4 Verification Criteria:
*   [ ] Submitting a bug identical to one solved previously results in the Architect querying Qdrant/AGE, retrieving the historical lesson, and routing around the hallucination on the first attempt.
*   [ ] The Vanilla JS UI loads instantly and visualizes the state machine DAG in real-time via WebSockets.

---

### ⚠️ EXECUTION DIRECTIVES FOR THE AI CODING AGENT
1. **Strict Phase Isolation:** You are strictly forbidden from writing code for Phase `N+1` until the Verification checklist for Phase `N` evaluates to absolute `true`.
2. **Minimize Dependencies:** In Rust, heavily vet Cargo crates; do not use heavy ORMs, use `sqlx` for raw SQL/Cypher. In Frontend JS, do not `npm install` any UI libraries; rely exclusively on browser-native DOM APIs.
3. **Idempotency & Safety:** All Rust Axum handlers and Restate activities must be purely idempotent. Map all internal errors to custom `AppError` enums. 
4. **Fail Loudly:** If a database connection fails, or an Incus CLI command is missing from the host, panic the Rust binary explicitly or return a strict `Err`. Restate is explicitly designed to catch, handle, and safely retry panics.