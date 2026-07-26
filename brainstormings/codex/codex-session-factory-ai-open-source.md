# Factory AI Open Source — ChatGPT session transcript

**Source:** https://chatgpt.com/share/6a660476-01b8-83e8-a4ee-99b763f8763e  
**Model:** gpt-5-6-pro · **Shared:** 2026-07-26 12:58 UTC · **User prompts:** 1

> Full dump of the shared ChatGPT session. Assistant reasoning summaries are kept as blockquotes; `web.run` blocks are the assistant's web-search/browse tool calls. Tool outputs are redacted by ChatGPT's share mechanism and omitted. Citation markers are converted to inline links.


---

## 👤 User

dark factory ai concepts 
do we have any practical usable open source solutions ?
I am looking into 
https://fabro.sh/
https://gethuman.sh/
https://github.com/coleam00/archon
https://github.com/swamp-club/swamp
https://github.com/owainlewis/factory

I need to use it for prod code building so need something that mature and usable and can work with claude, gemini and codex alike 
better using multiple 200$ subscriptions


## 🤖 Assistant

> 🔍 **Tool call → `web.run`**

```json
{
  "open": [
    {
      "ref_id": "https://fabro.sh/"
    },
    {
      "ref_id": "https://gethuman.sh/"
    },
    {
      "ref_id": "https://github.com/coleam00/archon"
    },
    {
      "ref_id": "https://github.com/swamp-club/swamp"
    },
    {
      "ref_id": "https://github.com/owainlewis/factory"
    }
  ],
  "response_length": "long"
}
```

*I’ll compare maturity, provider and subscription portability, orchestration, isolation, recovery, Git/CI integration, observability, licensing, and production safeguards, then recommend a practical architecture and shortlist.*

> 💭 **Searched 3 websites**

> 💭 **Assessing repository options**
> I’m comparing the projects’ actual execution models, especially whether they orchestrate API-backed models or consumer CLI subscriptions. I’ll check documentation, repository metadata, licensing, and workflow features before judging their fit.

> 💭 **Assessed repository options**

> 🔍 **Tool call → `web.run`**

```json
{
  "click": [
    {
      "ref_id": "turn491774view0",
      "id": 1
    },
    {
      "ref_id": "turn491774view1",
      "id": 5
    }
  ],
  "response_length": "medium"
}
```

> 💭 **Searched 1 website**

> 💭 **Expanding the comparison**
> I’m broadening the search beyond the named projects to include mature agent platforms and custom orchestration. I’m also separating API-based deployments from subscription-backed CLI workflows, since that distinction determines practical cost and reliability.

> 💭 **Expanded the comparison**

> 🔍 **Tool call → `web.run`**

```json
{
  "open": [
    {
      "ref_id": "https://api.github.com/repos/fabro-sh/fabro"
    },
    {
      "ref_id": "https://api.github.com/repos/gethuman-sh/human"
    },
    {
      "ref_id": "https://api.github.com/repos/coleam00/archon"
    },
    {
      "ref_id": "https://api.github.com/repos/swamp-club/swamp"
    },
    {
      "ref_id": "https://api.github.com/repos/owainlewis/factory"
    }
  ],
  "response_length": "long"
}
```

> 💭 **Searching github.com**

> 💭 **Tailoring the recommendation**
> I’m mapping each option against the stated architecture: GitLab, self-hosting, autonomous execution, customer-data controls, and subscription-backed model access. I’m also checking whether alternatives offer more mature orchestration.

> 💭 **Tailored the recommendation**

> 🔍 **Tool call → `web.run`**

```json
{
  "search_query": [
    {
      "q": "site:docs.openhands.dev self-hosted enterprise multi provider GitLab OpenHands runtime sandbox"
    },
    {
      "q": "site:github.com/All-Hands-AI/OpenHands README GitLab provider LiteLLM sandbox production"
    },
    {
      "q": "site:docs.all-hands.dev OpenHands GitLab integration self hosted"
    },
    {
      "q": "site:github.com/SWE-agent/SWE-agent README multi model production sandbox"
    }
  ],
  "response_length": "long"
}
```

> 💭 **Searched 16 websites**

> 🔍 **Tool call → `web.run`**

```json
{"open":[{"ref_id":"turn783416view0","lineno":185},{"ref_id":"turn783416view0","lineno":238},{"ref_id":"turn308254view12","lineno":280},{"ref_id":"turn783416view3","lineno":185},{"ref_id":"turn308254view0","lineno":240},{"ref_id":"turn308254view5","lineno":250},{"ref_id":"turn308254view6","lineno":240},{"ref_id":"turn289961view2","lineno":390},{"ref_id":"turn783416view11","lineno":210},{"ref_id":"turn574977view13","lineno":245},{"ref_id":"turn783416view12","lineno":315},{"ref_id":"turn168985view3","lineno":245},{"ref_id":"turn168985view3","lineno":310},{"ref_id":"turn168985view4","lineno":20},{"ref_id":"turn
```

*Fabro is the strongest factory control plane but relies on API keys; OpenHands Agent Canvas reuses official CLI subscriptions across providers, though production safeguards remain immature or commercial-only.*

> 💭 **Searched 2 websites**

> 💭 **Weighing production options**
> I’m distinguishing orchestration maturity from subscription compatibility. Fabro looks like the strongest control-plane foundation, while Archon best fits CLI subscriptions; neither fully covers GitLab, Gemini, and unattended production safely.

> 💭 **Updating the assessment**
> I’m correcting one detail: Fabro supports Codex or ChatGPT subscription authentication, but Claude and Gemini still generally require provider credentials. Archon is the best GitLab subscription prototype, not yet a mature production control plane.

> 💭 **Weighed production options and updated the assessment**

> 🔍 **Tool call → `web.run`**

```json
{
  "search_query": [
    {
      "q": "site:docs.fabro.sh ACP backend Claude Code Codex Gemini CLI Fabro"
    },
    {
      "q": "site:docs.fabro.sh GitLab Fabro repository integration"
    },
    {
      "q": "site:github.com/fabro-sh/fabro GitLab ACP Gemini Claude Code Codex"
    },
    {
      "q": "site:github.com/coleam00/archon TypeScript workflow engine migration April 2026"
    }
  ],
  "response_length": "long"
}
```

> 💭 **Searched 5 websites**

> 🔍 **Tool call → `web.run`**

```json
{
  "search_query": [
    {
      "q": "site:docs.temporal.io production deployment durable execution human-in-the-loop Temporal official"
    },
    {
      "q": "site:github.com/temporalio/sdk-core Rust SDK Temporal status official"
    },
    {
      "q": "site:argo-workflows.readthedocs.io Argo Workflows production Kubernetes official human approval suspend"
    },
    {
      "q": "site:docs.gitlab.com GitLab CI protected environments deployment approvals official"
    }
  ],
  "response_length": "long"
}
```

*Fabro’s newer ACP backend can reuse external CLI subscriptions, but loses some native features and lacks complete GitLab support. Use durable orchestration with isolated agent workers.*

> 💭 **Searched 3 websites**

*Worked for 17m 36s*

## Verdict

**Yes, practical open-source building blocks exist. No, there is not yet one turnkey open-source “dark factory” that I would trust as the scheduler, security boundary, GitLab integration, multi-model router, audit system, and autonomous production-delivery platform.**

As of **July 26, 2026**, my recommendation is:

> **Use a mature durable orchestrator and Kubernetes as the factory shell, then run Fabro CLI as the coding workflow harness inside disposable workers.**

For your environment, that means:

- **Axum + Keycloak** for the factory API and policy layer.
- **Temporal** for durable orchestration, retries, human signals, cancellation, and recovery.
- **Kubernetes Jobs** as the actual agent isolation boundary.
- **Fabro CLI** inside each job for plan/implement/verify/review loops.
- **GitLab** as the source-of-truth for branches, MRs, CI status, review apps, and protected production deployment.
- **Claude Code, Codex, and Gemini CLI through ACP**, or their APIs for unattended production runs.
- **S3 + OTLP** for evidence, logs, traces, artifacts, and long-term audit.

A correction to my initial scan: **Fabro can now technically run Claude Code, Codex, and Gemini CLI through its generic ACP backend.** Fabro can launch any preinstalled stdio ACP agent, and currently published ACP commands exist for all three. That is an inference from Fabro’s generic ACP support and the existing agent adapters, rather than Fabro explicitly bundling those three integrations. ACP stages also lose some Fabro-native capabilities such as provider failover, Fabro subagents, and consistent session caching. ([Fabro](https://docs.fabro.sh/core-concepts/agents))

## Assessment of the projects

| Project | What it really is | Multi-agent situation | Production judgment |
|---|---|---|---|
| **Fabro** | AI coding workflow engine | Native Anthropic/OpenAI/Gemini model APIs; actual Claude/Codex/Gemini CLIs through ACP | **Best specialist harness, not yet a production platform** |
| **OpenHands Agent Canvas** | Multi-agent UI, agent server, SDK and automations | Explicit Claude Code, Codex and Gemini CLI ACP support | **Best compatibility/evaluation environment; OSS admin and isolation controls are insufficient** |
| **Archon** | YAML coding workflow engine | Claude and Codex first-class; no first-class Gemini provider | **Good fast GitLab POC, too uneven for the final platform** |
| **human** | Secure development rig and connector proxy | Claims standalone compatibility, but strongly Claude-oriented | **Useful sidecar and source of security ideas, not the factory brain** |
| **Factory** | Minimal durable ticket dispatcher | Codex and GitHub only in v1 | **Excellent reference design, not deployable for your requirements** |
| **Swamp** | Deterministic infrastructure/operations workflow DSL | Skills for Claude, Codex, OpenCode and Cursor | **Wrong layer for software delivery; potentially useful later for operations** |
| **Temporal + Kubernetes** | General durable workflow and execution infrastructure | Runs whatever agent adapter you supply | **Best production backbone, but requires integration work** |

### 1. Fabro: the best inner workflow harness

Fabro has the strongest specialist architecture here:

- Version-controlled workflow graphs with branches, loops, parallel work and human gates.
- Command nodes for deterministic builds and tests.
- Automatic retry/fix loops.
- Git checkpoints after stages.
- Structured run events and retrospectives.
- Native Anthropic, OpenAI and Gemini model support.
- A generic ACP backend for external coding-agent processes. ([Fabro](https://fabro.sh/))

The problem is not the workflow design. The problem is the control-plane maturity.

Fabro’s own security documentation calls it a **research preview**, says it has not received third-party penetration testing, and states that it lacks multi-tenancy, roles, ACLs, source-IP restrictions and rate limiting. All authenticated users receive full access to all workflows, runs and API endpoints. Authentication is currently limited to a development token or GitHub OAuth. The server interface is also described as being in private early access. ([Fabro](https://docs.fabro.sh/administration/security))

I also found no documented first-party GitLab integration in the current Fabro integration list; GitHub is the documented forge integration. ([Fabro](https://docs.fabro.sh/core-concepts/agents))

There is another important operational limitation: **ACP works with Fabro’s local and Docker sandboxes, but not Daytona**. For your Kubernetes design, I would therefore run Fabro in local mode *inside an already-hardened Kubernetes Job*. The pod becomes the security boundary; Fabro does not.

**Decision:** adopt Fabro’s CLI and workflow format, pinned to a tested release or commit. Do not make the central Fabro server your factory’s only durable scheduler, authorization layer or audit database.

### 2. OpenHands: strongest explicit Claude/Codex/Gemini compatibility

OpenHands Agent Canvas explicitly supports:

- Claude Code through an ACP wrapper.
- Codex through `codex-acp`.
- Gemini CLI through its native `--acp` mode.
- Subscription logins or API keys.
- GitLab, GitHub and Slack integration.
- Scheduled and polling automations. ([OpenHands Docs](https://docs.openhands.dev/openhands/usage/agent-canvas/acp-agents))

However, its own comparison table places isolated sandboxes, authentication, RBAC with Keycloak, multi-user organizations, scalable always-on agents and related controls outside the local OSS backend. Those are available in hosted/enterprise variants, or listed as roadmap items for some backends. ([OpenHands Docs](https://docs.openhands.dev/enterprise/enterprise-vs-oss))

The basic no-sandbox installation gives agents full access to the host filesystem. The Docker mode mounts a project directory into the agent container, but that is not equivalent to a separately provisioned, tightly scoped sandbox for each autonomous run. ([GitHub](https://github.com/OpenHands/openhands))

**Decision:** use OpenHands as:

- A local operator UI.
- A compatibility test bench for ACP agents.
- A source of agent adapter implementations.
- Possibly an optional human-steering frontend.

Do not use the OSS local backend as the security boundary for unattended production code generation.

### 3. Archon: fastest GitLab proof of concept

Archon is attractive because it already has:

- YAML-defined deterministic workflows.
- Planning, implementation, validation, review and approval nodes.
- Isolated Git worktrees.
- A community adapter supporting both GitLab.com and self-hosted GitLab.
- Issue/MR webhook handling and `glab`-based MR operations. ([GitHub](https://github.com/coleam00/archon))

But its provider behavior is uneven. Claude and Codex are first-class providers, while Gemini is not listed as a provider. Claude supports more of Archon’s controls: hooks, tool restrictions, budgets, fallback models and container execution. Codex lacks many of those capabilities in the current matrix. ([Archon](https://archon.diy/reference/provider-capabilities/))

Container isolation also currently applies to folder projects, while repository projects use worktrees; the container runner shown in the documentation is Claude-specific. ([Archon](https://archon.diy/guides/container-isolation/))

Another maturity warning: the current workflow engine replaced the original Python task-management/RAG version. Consequently, the repository’s long history and popularity do not all represent operational experience with the current engine. ([GitHub](https://github.com/coleam00/archon))

**Decision:** Archon is the fastest way to demonstrate:

```text
GitLab issue → workflow → branch → MR
```

It is a strong benchmark against Fabro, but I would not make it the final durable production control plane.

### 4. human: security and context sidecar

`human` has genuinely useful ideas:

- An outbound firewall.
- Secret-redacting filesystem access.
- Vault-resolved credentials.
- An isolated development container.
- GitLab and other context connectors.
- Guardrails, approval gates and audit views. ([human](https://gethuman.sh/))

It says the standalone CLI can work with any coding agent, but its integrated development container, lifecycle skills and documentation are heavily centered on Claude Code.

**Decision:** evaluate its credential-proxy and context-connector approach. It could be used beside your worker, but it is not a substitute for durable ticket leasing, retries, idempotency, model routing and deployment orchestration.

### 5. Factory: copy the concepts, not the current product

Owain Lewis’s Factory gets several architectural boundaries exactly right:

- The ticket queue is the control plane.
- Triggering is based on a trusted state transition, not arbitrary issue content.
- Ticket bodies, comments and attachments remain untrusted.
- The dispatcher owns durable claims, deduplication, concurrency, timeouts, cancellation, supervision and recovery.
- The worker receives narrow credentials and cannot bypass protected branches. ([GitHub](https://github.com/owainlewis/factory))

But v1 intentionally supports one repository, one GitHub source and Codex workers.

**Decision:** mine this repository for your dispatcher state machine, lease model and trust-boundary design. It is particularly relevant because you are already writing the factory API in Rust.

### 6. Swamp: useful later, not for coding orchestration

Swamp is primarily an operations automation language. Its examples cover EC2 inventory, DNS auditing, server checks and credential rotation. It offers models, typed definitions, workflows, versioned data and vaults, and it supplies skills for several coding tools. But it assumes locally available shell credentials and is not a ticket-to-MR coding factory. ([GitHub](https://github.com/swamp-club/swamp))

**Decision:** revisit it when agents begin creating and reviewing operational workflows. Do not use it as the central software-development factory.

---

## The consumer-subscription problem

The idea of several `$200` subscriptions is attractive economically, but **consumer subscriptions are not a uniform production service-account layer**.

### Claude

Anthropic says Pro and Max limits assume ordinary individual use. OAuth is intended for subscription users using native Anthropic applications. Developers building products or services should use API authentication, and Anthropic explicitly says third parties may not route Free, Pro or Max credentials on behalf of users. A shared factory that round-robins several Max credentials is therefore not a design I would put into production without a specific commercial agreement. ([Claude Platform Docs](https://docs.anthropic.com/en/docs/claude-code/legal-and-compliance))

Practical policy:

- Claude subscription: named developer, interactive or explicitly developer-owned jobs.
- Autonomous shared queue: Anthropic API, Bedrock, Vertex AI or an approved enterprise arrangement.
- Do not round-robin multiple Max accounts to evade account limits.

### Codex

OpenAI has the most permissive documented path of the three. `codex exec` can reuse saved ChatGPT-managed authentication, and OpenAI documents using that authentication on trusted CI runners as an advanced option. However, it still recommends API keys as the default for automation and says `~/.codex/auth.json` must be treated like a password. ([OpenAI Developers](https://developers.openai.com/codex/non-interactive-mode))

Practical policy:

- A Codex subscription lane can run on a dedicated, trusted worker.
- Never copy one `auth.json` into a general shared secret store accessible by jobs.
- One auth volume per named seat.
- API authentication remains the normal production lane.

### Gemini

This changed recently and invalidates part of the “three consumer subscriptions” plan.

Starting **June 18, 2026**, Google stopped serving Gemini CLI requests for Gemini Code Assist for individuals, Google AI Pro and Google AI Ultra accounts. “Login with Google” no longer provides Gemini CLI access for those consumer tiers. Gemini Code Assist Standard and Enterprise are unaffected. ([Google for Developers](https://developers.google.com/gemini-code-assist/docs/deprecations/code-assist-individuals))

OpenHands documentation still describes a consumer Google login for Gemini CLI, but Google’s later deprecation notice supersedes that description. ([OpenHands Docs](https://docs.openhands.dev/openhands/usage/agent-canvas/acp-agents))

Practical policy:

- Use the Gemini API for autonomous work.
- Alternatively use Code Assist Standard/Enterprise if its commercial model suits you.
- Do not plan around Google AI Ultra consumer seats for Gemini CLI workers.

### Recommended authentication split

| Lane | Purpose | Authentication |
|---|---|---|
| **Developer lane** | Interactive exploration and supervised tickets | Named Claude/Codex subscriptions where permitted |
| **Evaluation lane** | Benchmarking agents and workflows | Named subscriptions or capped API projects |
| **Production factory lane** | Unattended jobs, retries and scheduled work | API or enterprise/service authentication |
| **Emergency/overflow lane** | Provider outage or quota exhaustion | Separate API provider/account, activated at stage boundaries |

Do not fail over from one agent to another in the middle of a conversational session. Fail over at a checkpoint or restart the stage with a clean context and recorded reason.

---

## Recommended architecture for your stack

```text
┌────────────────────────────────────┐
│ Laravel ticketing                  │
│ feature request, acceptance tests  │
└─────────────────┬──────────────────┘
                  │ signed event
                  ▼
┌────────────────────────────────────┐
│ Axum Factory API + Policy Engine   │
│ Keycloak, RBAC, risk classification│
│ immutable ticket snapshot          │
└─────────────────┬──────────────────┘
                  ▼
┌────────────────────────────────────┐
│ Temporal outer workflow            │
│ lease, dedupe, retry, timeout,      │
│ cancellation, approval signals     │
└─────────────────┬──────────────────┘
                  ▼
┌────────────────────────────────────┐
│ Kubernetes Job per attempt         │
│ isolated namespace / pod           │
│ pinned source SHA                  │
│                                    │
│ Fabro CLI                          │
│   ├── Claude ACP/API               │
│   ├── Codex ACP/API                │
│   └── Gemini ACP/API               │
└─────────────────┬──────────────────┘
                  │ patch + evidence
                  ▼
┌────────────────────────────────────┐
│ GitLab broker                      │
│ branch, commits, MR, comments      │
└─────────────────┬──────────────────┘
                  ▼
┌────────────────────────────────────┐
│ GitLab CI + Jenkins                │
│ tests, SAST, SBOM, policy, deploy  │
└─────────────────┬──────────────────┘
                  ▼
       Review app / automatic canary
                  │
                  ▼
       Protected production approval
```

Temporal is an open-source durable-execution platform designed to preserve workflow state across crashes and infrastructure failures, and it explicitly supports long-running human-in-the-loop patterns. ([Temporal Docs](https://docs.temporal.io/?utm_source=chatgpt.com))

One caveat for your Rust preference: the official native Temporal Rust SDK is still marked **Public Preview** and its API may continue changing. I would keep your API, policy engine and domain model in Rust/Axum, but run the small Temporal workflow worker in Go or TypeScript until the Rust SDK reaches general availability. ([GitHub](https://github.com/temporalio/sdk-core/blob/master/README.md?raw=true))

### What the outer workflow must own

Fabro should own the adaptive engineering loop. The outer platform should own everything requiring hard operational guarantees:

1. **Ticket trust and leasing**

   Anyone may create a ticket, but only an authorized transition—such as a trusted label, approval or status change—may place it in the runnable queue. Store an immutable snapshot of the ticket and acceptance criteria at dispatch time.

2. **Idempotency**

   Use an idempotency key such as:

   ```text
   project_id + ticket_id + ticket_revision + workflow_version
   ```

   Replayed webhooks must not create a second run, branch or MR.

3. **Sandbox lifecycle**

   One Kubernetes Job per attempt, with:

   - No host Docker socket.
   - No default Kubernetes service-account token.
   - Read-only base filesystem.
   - Ephemeral writable workspace.
   - CPU, memory, process and wall-clock limits.
   - Restricted outbound network policy.
   - No production database access.
   - No production customer identity data.
   - Synthetic or redacted fixtures only.

   Run Fabro with its local backend inside the pod. The Kubernetes pod is the sandbox, not Fabro’s local execution mode.

4. **Credential brokerage**

   The coding process should preferably receive:

   - Read-only repository access.
   - A narrow package-registry token where required.
   - Provider authentication for the selected agent.
   - No GitLab Maintainer token.
   - No deployment credential.

   A separate GitLab broker should accept a patch or commit bundle and perform the branch push and MR creation. This prevents the coding agent from modifying unrelated branches, project settings or CI policy.

5. **Evidence collection**

   Upload an immutable run bundle to S3 containing:

   ```text
   ticket snapshot
   repository SHA
   workflow version
   sandbox image digest
   agent, provider and model
   authentication mode
   prompt and instruction hashes
   stage events
   commands executed
   changed-file manifest
   patch/commits
   test and security results
   token/cost accounting
   final risk report
   ```

6. **Cancellation and recovery**

   Killing the dispatcher, worker pod or model process must not lose the authoritative run state. A retry should either resume from a verified checkpoint or deliberately start a clean attempt. It must never silently continue from an uncertain workspace.

### What GitLab must continue to own

Agents should not become an alternative CI/CD authority.

Use GitLab for:

- Protected branches and merge rules.
- Code-owner and reviewer policies.
- Required CI jobs.
- Review apps for each MR.
- Canary deployments.
- Protected production environments.
- Production deployment approvals.

GitLab supports protected branches, temporary review apps and approval-gated protected-environment deployments. Deployment approvals require the appropriate GitLab tier; otherwise use a protected manual job or an equivalent approval in Jenkins/control plane. ([GitLab Docs](https://docs.gitlab.com/user/project/repository/branches/protected/))

I would make **GitLab CI the authoritative merge-quality gate**. Jenkins can remain the deployment executor where needed, but avoid giving GitLab and Jenkins independent, conflicting definitions of whether an artifact is promotable.

---

## Suggested first factory workflow

The first workflow should be deliberately conservative:

```text
intake
  ↓
ticket-quality check
  ↓
risk classification
  ├── ambiguous → ask human
  ├── sensitive → mandatory plan approval
  └── normal
        ↓
read-only planning
        ↓
implementation by one writer
        ↓
format / compile / unit test / lint
        ↓
bounded repair loop, maximum 3 attempts
        ↓
read-only review by a different provider
        ↓
acceptance-criteria verification
        ↓
produce patch and evidence bundle
        ↓
GitLab branch + MR
        ↓
GitLab CI / Jenkins
        ↓
review app or canary
        ↓
human production approval
```

A good initial provider strategy is:

- **Planning:** Gemini or Claude, read-only.
- **Implementation:** whichever of Claude or Codex wins your internal benchmark.
- **Review:** a different provider from the implementer.
- **Final acceptance check:** deterministic checks plus a read-only model review.

Use **one writer per branch**. Multiple models can propose plans or independently review a diff, but they should not concurrently modify the same workspace.

For changes involving authentication, authorization, customer identity, encryption, database migrations, CI policy, dependency provenance or infrastructure permissions, force a human plan approval and human merge review regardless of the model’s confidence.

---

## Production qualification tests

Before enabling automatic canaries, the factory should survive all of these:

1. Kill the worker while it is editing, then confirm recovery creates neither lost work nor duplicate MRs.
2. Deliver the same ticket webhook repeatedly and confirm exactly one active run.
3. Expire the model credential mid-run and confirm the run pauses or retries safely.
4. Return provider `429`, timeout and malformed-output responses.
5. Make GitLab unavailable during branch creation and during MR creation.
6. Put prompt-injection instructions in the ticket body, comments, repository files and test output.
7. Attempt to read Kubernetes secrets, service-account credentials, other repositories and cloud metadata.
8. Attempt outbound data exfiltration to an unapproved host.
9. Cancel a run at every stage and verify all pods, volumes and credentials are cleaned up.
10. Confirm the worker cannot push to protected branches, change CI configuration outside the allowed patch, approve its own deployment or access production credentials.

The release criterion should not merely be “the agent writes good code.” It should be:

> **A bad, confused, compromised or rate-limited agent still cannot bypass the factory’s operational and security boundaries.**

## Final recommendation

For your particular factory:

- **Adopt Temporal, Kubernetes and GitLab as the production skeleton.**
- **Embed Fabro CLI as the first coding harness.**
- **Use ACP as the portability boundary for Claude Code, Codex and Gemini CLI, while retaining API-based runners.**
- **Use OpenHands as an operator/evaluation environment, not the production authorization boundary.**
- **Run Archon as a short GitLab-oriented benchmark, not as the final foundation.**
- **Borrow Factory’s durable dispatcher and ticket-trust concepts.**
- **Borrow human’s credential proxy, firewall and connector patterns.**
- **Keep Swamp for later infrastructure/operations automation.**
- **Treat subscription seats as developer capacity, not pooled production compute.**

That gives you an open-source factory whose critical reliability and security do not depend on any one young agent framework—and lets you replace Fabro, Claude, Codex or Gemini without replacing the factory itself.

