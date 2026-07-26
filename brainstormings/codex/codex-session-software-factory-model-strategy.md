# Software Factory Model Strategy — ChatGPT session transcript

**Source:** https://chatgpt.com/share/6a65d9ca-fab0-83e8-b04e-4bae45ad24d7  
**Model:** gpt-5-6-pro · **Shared:** 2026-07-26 09:56 UTC · **User prompts:** 3

> Full dump of the shared ChatGPT session. Assistant reasoning summaries are kept as blockquotes; `web.run` blocks are the assistant's web-search/browse tool calls. Tool outputs are redacted by ChatGPT's share mechanism and omitted. Citation markers are converted to inline links.


---

## 👤 User

I'd like to work on building a org-wide software factory with complete automation. something similar to factory.ai , openai's symphony tool, or https://buzz.xyz/ etc
my primary question is what model and effort will handle this challenge the best?
my idea: fable5 with max effort
should I go with it or should I switch to opus5 with max
and should the effort be kept at max or xhigh is better
my rationale being we need a lot of thinking and analysis so a better model with max effort might gimme a more accurate results
final goal being a working prototype POC that we can throw into prod from day 1 and then start evolving it.
goal is to link all 3 major players, gemini, claude and openai codex into the mix and build an ultimate powerhouse of intelligence that can deliver feature after feature at near assembly line speed 
for gemini which is better, pro3.1 or flach 3.6 and thinking deep or extended ?
for chatgpt/codex, I think gpt5.6sol with extra-high or pro thinking


## 🤖 Assistant

*I’ll verify which of those model names and effort modes are actually current, then map them to a practical multi-model architecture and a realistic path to a production-grade POC.*

> 🔍 **Tool call → `web.run`**

```json
{
  "system1_search_query": [
    {
      "q": "site:openai.com OpenAI GPT-5.6 Codex extra high reasoning effort official"
    },
    {
      "q": "site:anthropic.com Claude Opus 5 official max effort extended thinking"
    },
    {
      "q": "site:ai.google.dev Gemini 3.1 Pro Flash 3.6 deep thinking extended official"
    },
    {
      "q": "factory.ai official software factory AI coding agents"
    }
  ],
  "response_length": "long"
}
```

> 💭 **Searched 14 websites**

*The first important finding: this should not be designed around one “smartest” model at maximum effort. The winning pattern is a routed system—frontier models for planning and review, faster models for execution, and deterministic CI/security gates for authority.*

> 🔍 **Tool call → `web.run`**

```json
{
  "system1_search_query": [
    {
      "q": "site:buzz.xyz software factory AI agents"
    },
    {
      "q": "buzz.xyz autonomous software engineering official"
    },
    {
      "q": "site:openai.com/index/open-source-codex-orchestration-symphony Symphony official"
    },
    {
      "q": "site:developers.openai.com codex GPT-5.6 Sol reasoning effort API pricing"
    }
  ],
  "response_length": "long"
}
```

> 💭 **Searched 15 websites**

> 💭 **Assigning model roles**
> I’m organizing the software factory around planning, execution, verification, and governance. I’d use GPT-5.6 Sol as the primary orchestrator, Opus 5 for independent review and refactoring, and Fable 5 only for exceptional long-running tasks.

> 💭 **Assigned model roles**

> 💭 **Refining effort strategy**
> I’m separating default execution from rare escalation. I’d use GPT-5.6 Sol high/xhigh routinely, reserve Pro or max for final judgment, and make Opus 5 the independent reviewer. Gemini can handle high-throughput workers and targeted architecture tasks.

> 🔍 **Tool call → `web.run`**

```json
{
  "open": [
    {
      "ref_id": "https://buzz.xyz/"
    }
  ],
  "response_length": "long"
}
```

> 💭 **Searched 1 website**

*Worked for 4m 28s*

## Recommendation

Build a **routed, multi-model software factory** rather than choosing one model at maximum effort for everything.

My recommended hierarchy is:

1. **GPT-5.6 Sol** as the primary orchestrator and difficult implementation model.
2. **Claude Opus 5** as the default independent architect, reviewer, and critic.
3. **Gemini 3.6 Flash** as the high-throughput worker for exploration, test generation, repository analysis, and routine implementation.
4. **Claude Fable 5** and **Gemini 3.1 Pro** as escalation models for specific difficult workloads.

### Direct answers

- **Fable 5 max or Opus 5 max?**  
  Use **Opus 5 at high effort** as your Anthropic default. Use **Fable 5 at high or xhigh** only for unusually long-running or capability-sensitive projects. Do not run either at max by default.

- **Max or xhigh?**  
  Neither should be the default. Use **high normally**, **xhigh for demonstrably difficult work**, and **max only after a task fails or for rare, quality-first adjudication**.

- **Gemini 3.1 Pro or Gemini 3.6 Flash?**  
  Use **3.6 Flash medium/high for the factory’s worker fleet**. Use **3.1 Pro high for architecture, complex multimodal reasoning, or difficult cross-repository planning**.

- **Extended or Deep Think?**  
  Use Extended thinking for interactive, difficult planning. Reserve Deep Think for occasional offline architecture or research exercises. In the production API, the comparable control is generally `thinking_level`, where both Gemini 3.6 Flash and 3.1 Pro support `high`; 3.6 Flash defaults to medium and 3.1 Pro defaults to high. ([Google Help](https://support.google.com/gemini/answer/16275805?hl=en&utm_source=chatgpt.com))

- **GPT-5.6 Sol Extra High or Pro?**  
  Use **Sol at high/xhigh for normal factory operation**. Use **Pro mode with xhigh**, or occasionally max, for final architecture decisions, release adjudication, incident analysis, or repeated failures. Pro mode and reasoning effort are independent controls, not two competing model choices. ([OpenAI Developers](https://developers.openai.com/api/docs/guides/latest-model))

## Suggested model routing

| Workload | Primary model | Effort | Independent check |
|---|---|---:|---|
| Requirement normalization and task decomposition | GPT-5.6 Sol | High | Opus 5 high |
| System architecture or major migration | GPT-5.6 Sol | Xhigh | Fable 5 or Opus 5 xhigh |
| Routine feature implementation | GPT-5.6 Terra or Gemini 3.6 Flash | Medium/high | Sol or Opus 5 high |
| Difficult feature implementation | GPT-5.6 Sol | High/xhigh | Opus 5 high |
| Multi-day refactor or migration | Fable 5 | High, then xhigh | Sol xhigh |
| Repository exploration and dependency mapping | Gemini 3.6 Flash | Medium | Deterministic tooling |
| Test generation and test-gap analysis | Gemini 3.6 Flash | Medium/high | Sol high |
| UI screenshot and rendered-result checking | Gemini 3.6 Flash or 3.1 Pro | High | Visual regression suite |
| Security and threat-model review | Opus 5 | Xhigh | Sol Pro xhigh |
| Final high-risk release adjudication | GPT-5.6 Sol Pro | Xhigh | Opus 5 xhigh plus human |

The important pattern is that **the model that authors a change should not also be its only reviewer**.

## Why I would not default to Fable 5 max

Fable 5 is explicitly positioned for ambitious, long-running coding projects and multi-day autonomous sessions. However, it costs **$10 per million input tokens and $50 per million output tokens**, versus **$5/$25 for Opus 5**. Fable 5 also requires 30-day retention and is unavailable under zero-data-retention arrangements, which could matter significantly for proprietary organizational source code. Anthropic itself recommends starting Fable 5 at `high`, reserving `xhigh` for capability-sensitive workloads, and running your own effort sweep rather than carrying over an old max setting. ([Anthropic](https://www.anthropic.com/claude/fable))

There is also no universal benchmark winner. OpenAI reports GPT-5.6 Sol max ahead of Fable 5 on the Artificial Analysis Coding Agent Index, while the same published table shows Fable 5 materially ahead on SWE-Bench Pro. That disagreement is exactly why your internal task suite—not a global leaderboard—must select the model. ([OpenAI](https://openai.com/index/gpt-5-6/))

Therefore:

> **Opus 5 high should be the default Anthropic lane. Fable 5 should be an escalation lane, not the foundation of every run.**

## Why maximum effort everywhere will slow the factory

Your factory’s throughput will come mainly from:

- Parallel workspaces.
- Good task decomposition.
- Reliable test and validation harnesses.
- Fast failure detection.
- Selective escalation.
- Small, independently mergeable changes.

It will not come from making every agent think for the maximum possible duration.

OpenAI recommends medium as a balanced starting point, high or xhigh where measured reasoning gains exist, and max only for the hardest quality-first workloads. Anthropic similarly recommends fresh effort evaluations and high as the normal Fable setting. ([OpenAI Developers](https://developers.openai.com/api/docs/guides/latest-model))

A sensible initial compute distribution would be:

- **50–60% medium:** exploration, triage, documentation, test generation and simple fixes.
- **30–40% high:** normal implementation and review.
- **5–10% xhigh:** architecture, difficult debugging and security-sensitive changes.
- **Under 3% max or Pro:** repeated failures, final adjudication and exceptional migrations.

Those percentages should be tuned against your own landed-PR and escaped-defect data.

## Gemini configuration

Gemini 3.6 Flash should be your default Gemini worker. It is designed for speed and high-throughput reasoning, supports medium and high thinking, and currently costs **$1.50 input and $7.50 output per million tokens** at standard rates. Gemini 3.1 Pro Preview costs **$2/$12** for prompts up to 200,000 tokens and should be reserved for tasks where its higher reasoning or multimodal capability actually improves results. Because 3.1 Pro is still labelled Preview, keep a fallback and avoid coupling your orchestration state to model-specific behavior. ([Google AI for Developers](https://ai.google.dev/gemini-api/docs/pricing))

Recommended Gemini policy:

```text
Repository scanning             -> 3.6 Flash / medium
Test generation                 -> 3.6 Flash / medium
Routine coding                  -> 3.6 Flash / high
Complex multimodal inspection   -> 3.1 Pro / high
Architecture second opinion     -> 3.1 Pro / high
Deep Think                      -> Offline exceptional analysis only
```

## OpenAI/Codex configuration

I would make **GPT-5.6 Sol high** your root planner and difficult coding agent, with `xhigh` triggered by task risk or prior failure. GPT-5.6 Sol currently supports `none`, `low`, `medium`, `high`, `xhigh`, and `max`; Pro mode adds more model work but should be reserved for quality-first workflows where latency and token consumption are secondary. ([OpenAI Developers](https://developers.openai.com/api/docs/guides/latest-model))

For routine tasks, evaluate **GPT-5.6 Terra high** as a cheaper executor. Use Sol for:

- Cross-repository architecture.
- Ambiguous requirements.
- Difficult implementation.
- Integration failures.
- Release and security judgments.
- Work that has already failed on a cheaper model.

For the actual platform, use the Responses API or Codex app-server/headless interfaces rather than making ChatGPT conversations the control plane. Symphony itself uses programmatic Codex app-server operation for scalable runs. ([OpenAI](https://openai.com/index/open-source-codex-orchestration-symphony/))

## Architecture for the POC

The right initial flow is:

```text
Signal
  ↓
Requirement normalizer
  ↓
Risk classifier and acceptance criteria
  ↓
Planner creates task DAG
  ↓
Router selects model + effort + permissions
  ↓
Isolated implementation workspace
  ↓
Deterministic verification
  ↓
Independent model review
  ↓
PR / merge policy
  ↓
Canary deployment
  ↓
Monitoring, rollback and follow-up tickets
```

This matches the broader factory pattern: external signals become planned changes, which are built, tested, reviewed, secured, shipped and monitored in a continuous feedback loop. Symphony provides a useful issue-tracker-driven control-plane pattern and reportedly increased landed PRs by 500% on some OpenAI teams. ([Factory](https://factory.ai/news/software-factory))

However, Symphony is an orchestration specification, not a complete enterprise security system. Its sandbox, approvals and operator-confirmation posture are deliberately implementation-defined. You will need to add:

- Ephemeral containers or microVMs.
- Per-task credentials.
- Network egress policies.
- Secret brokering.
- Repository and path-level permissions.
- Signed artifacts and provenance.
- Audit logs and kill switches.
- Resource, token and duration budgets. ([OpenAI](https://openai.com/index/open-source-codex-orchestration-symphony/))

## What “production from day one” should mean

Deploy the POC into your production environment from day one, but give it **limited authority**:

**Initial authority**

- Read approved repositories.
- Create branches and pull requests.
- Run tests and previews.
- Comment on issues and PRs.
- Produce deployment candidates.
- Never push directly to main.
- Never hold standing production credentials.

After sufficient evidence, allow low-risk classes such as documentation, generated tests, dependency patches and narrowly scoped refactors to auto-merge. Application logic, authorization, payments, database migrations, infrastructure and security controls should retain stronger approval policies.

This matters because empirical research on coding-agent adoption has found that velocity improvements can coexist with increased static-analysis warnings and complexity debt. The factory needs a stronger quality system than the agents generating the code. ([arXiv](https://arxiv.org/abs/2601.13597?utm_source=chatgpt.com))

## Realistic implementation effort

For a **production-grade vertical slice over one or two repositories**, my planning estimate would be:

- **Team:** four to six experienced people.
- **Duration:** approximately eight to twelve weeks.
- **Roles:** platform/orchestration engineer, two agent/backend engineers, DevSecOps/SRE, QA/evaluation engineer and a technical product or architecture lead.

A reasonable sequence is:

1. **Weeks 1–2:** historical-ticket evaluation suite, risk taxonomy and model adapters.
2. **Weeks 3–6:** issue orchestration, workspaces, routing, retries and PR generation.
3. **Weeks 6–9:** CI, security, independent review, observability and cost controls.
4. **Weeks 9–12:** shadow operation, low-risk production tasks and controlled auto-merge.

An organization-wide rollout is more likely a **two-to-four-quarter program**, especially if repositories currently have weak tests, inconsistent build systems or undocumented engineering workflows.

## Final configuration I would start with

```yaml
orchestrator:
  model: gpt-5.6-sol
  effort: high
  escalation: xhigh

routine_workers:
  - model: gemini-3.6-flash
    effort: medium
  - model: gpt-5.6-terra
    effort: medium

hard_implementation:
  model: gpt-5.6-sol
  effort: high

primary_reviewer:
  model: claude-opus-5
  effort: high

long_horizon_escalation:
  model: claude-fable-5
  effort: high

architecture_escalation:
  models:
    - gpt-5.6-sol
    - claude-opus-5
    - gemini-3.1-pro-preview
  effort: xhigh_or_high

critical_release_gate:
  author_model: gpt-5.6-sol
  author_mode: pro
  author_effort: xhigh
  reviewer_model: claude-opus-5
  reviewer_effort: xhigh
  human_approval: required
```

So the decisive recommendation is:

> **Do not choose Fable 5 max as the universal model. Start with GPT-5.6 Sol high as the lead, Opus 5 high as the independent reviewer, and Gemini 3.6 Flash medium/high as the worker fleet. Escalate to xhigh, Fable 5, Gemini 3.1 Pro or Sol Pro only when task risk and measured results justify it.**

Buzz currently exposes only an early-stage public landing page, so Factory’s documented loop and Symphony’s open orchestration specification provide much more concrete architectural material for the initial implementation. ([Buzz](https://buzz.xyz/))

A monthly model-routing, benchmark and pricing review would be useful because this landscape is changing rapidly; say the word and I’ll schedule it.


---

## 👤 User

got it. lets us brainstorm and design our factory and see how it will work
here are my ideas/wish list 

* biz sends a feature request to ticket system (we build the ticket system or use simple system already available like taskwarrior because LLMs don't need training to use it )
* something in the factory monitoring the jobs pool picks it up (watcher ? dispatcher? , a pure code loop?no llm? or should it be llm?)
* triage/sorter a smart agent looks at the request and requests to the lead architect to look at the issue and decide what to do
* we use best of the EDA and every stage emits events 
* everything is logged and 100% traces are stored (we don't care about storage space, we want to store every single action/prompt/response/session/artifacts logged). we will use 1PB space for this so dont worry about space. just think how to logically and semantically store EVERYTHING happening in this factory (iceberg ? )
* domain knowledge MUST be stored in a very accessible way. I am thinking of some kind of graph-db + vectorDB rag ? mcp?
* token efficiency must be considered
* every component used in this factory/harness MUST be either open source or self built . no commercial paid solutions needed
* github presented a concept called ACE, where communication combines the work thus bringing everything org-wide into the context providing enormous info for agents . I believe something similar can help us
* dreaming feature , kaizen, continuous learning is the benefit we will get from storing ALL logs 
* a way to evaluate the tasks and boolean results : is the implementation doing what it was supposed to be doing : yes/no and then work till the yes is received 
* which step will decide what are the evaluation / acceptance criteria? what will be the definition of done ?
* I think architect agent LLM should post questions to ticket system when ambiguity is there so that before work on a ticket is started, everything is clear 
* can goole OKF play any role in this ?
* spec driven development ? should we consider ? as technical corrrectness and deterministic results are needed, I think having a specs creator/verifier/evaluator might help ?
* resumability: this is non-negotiable. work can stop abruptly like tokens finished, session limit reached, server got rebooted etc. so every in progress session MUST keep a state and resumable . usually we can mark steps and on resume we can see which last step was done and start working from there. this will eliminate full rework and on in progres mini/micro step will need to be redone.
* micro-service, RISC and SRP are concepts from different domains but we can leverage them in our factory design to build something where hundredrd/thousands/millions of small simple steps in parallel can  handle complex problems with much higher confidence and deterministic way than large sessions doing a huge task at once and getting hallucinated 
*  use existing solutions like factory.ai, cognee, buzz.xyz , github ACE, google OKF, karpathy's frameworks etc as inspirations where they can help steer the flow. something like instead of reinventing the wheel , stand on shoulders of giants 
* future proofing: as new frontier models will keep coming in in one year or so we can have much smarter models that can handle a lot of work autonomously, so DO NOT try to build something that agents of the future can automatically handle. build something that can work with ANY model from gemini/claude/openai/opensource etc . plug the model architecture 
* builtin multi-model architecture. sometimes you can get better results if multiple LLM models work together . something like https://omnigent.ai/. like we ask claude to create a plan, both gemini and codex perform an adversarial review etc 
* interface simplicity is also important. when user submits a task, we need to be able to tap into the UI and see the progress in realtime 
* an important aspect is testing . TDD must be religiously performed in this flow. TDD is NOT for testing, but TDD will force the LLM to think a better component based decoupled architecture . TDD must be used for better architectural design / software components . this is NOT only for verification.
* infra agents must produce IaC that is 100% repeatable and idempotent 
* tessl agent is another contender in software factory concept just like factory.ai droid
* stripe minions, ramp inspect, claude tag are also some concepts in org wide factory 

this is all just a mind dump. DO. NOT jump into building anything. 
goal of this session is to look into the concept, analyze the current and future landscape, and then  interview me 

* brainstorm together and cleanly outline the actual requirements one by one. 
* create a simple PRD file with refined details of what do we actually need, what shuold we build and what should we drop
* once PRD is ready, we use this PRD to create an actual implementation plan with tech details like what tech stack to use, build phases, evaluation criteria of each phase etc


## 🤖 Assistant

> 💭 **Clarifying the product**
> I’m treating this as a discovery session, not an implementation task. I’ll map the current agent landscape, identify relevant patterns, and interview the user before shaping a lightweight PRD.

> 🔍 **Tool call → `web.run`**

```json
{
  "search_query": [
    {
      "q": "site:factory.ai software factory official"
    },
    {
      "q": "site:openai.com Symphony software engineering orchestration official"
    },
    {
      "q": "site:github.blog ACE agentic context engineering GitHub official"
    },
    {
      "q": "Google OKF agent framework official software engineering"
    }
  ],
  "response_length": "long"
}
```

*I’ll structure and validate the ideas into a conceptual PRD separating requirements, hypotheses, and open questions, then begin a focused interview before considering architecture or implementation.*

*An initial design principle is emerging: use a deterministic, model-neutral control plane for lifecycle and resumability, while confining LLMs to bounded semantic tasks.*

> 💭 **Searched 16 websites**

> 💭 **Researching the landscape**
> I’m mapping the relevant agent-workflow patterns and separating verified products from speculative or ambiguous references. I’ll use those findings to guide discovery questions and a lightweight PRD, without moving into implementation yet.

> 💭 **Distinguishing patterns**
> I’m separating shared workspaces, context engineering, knowledge interchange, memory systems, multi-agent orchestration, event logs, and spec-driven development. I’ll treat sparse or ambiguous references as inspiration rather than dependencies.

> 💭 **Researched the landscape and distinguished patterns**

> 💭 **Shaping the discovery plan**
> I’m organizing the research into a practical landscape review, then translating recurring ideas into provisional product requirements. I’ll keep the PRD explicitly draft-level until the user answers the core discovery questions.

> 🔍 **Tool call → `web.run`**

```json
{
  "search_query": [
    {
      "q": "site:openai.com/index/open-source-codex-orchestration-symphony Symphony software engineering agents issue tracker control plane"
    },
    {
      "q": "site:openai.com/index harness engineering Codex agents environment feedback loops"
    },
    {
      "q": "site:githubnext.com Ace multiplayer coding agents workspace"
    },
    {
      "q": "site:github.blog agentic primitives context engineering GitHub"
    }
  ],
  "response_length": "long"
}
```

> 💭 **Searched 13 websites**

> 🔍 **Tool call → `web.run`**

```json
{
  "search_query": [
    {
      "q": "site:factory.ai software factory self improving SDLC continuous signals deploy"
    },
    {
      "q": "site:buzz.xyz software factory agents event log self hosted"
    },
    {
      "q": "site:tessl.io \"self-improving\" software factory agent"
    },
    {
      "q": "site:omnigent.ai docs Debby debate multi model"
    }
  ],
  "response_length": "long"
}
```

> 💭 **Searched 8 websites**

> 🔍 **Tool call → `container.exec`**

```unknown
bash -lc cat > /mnt/data/org_wide_software_factory_discovery_prd_v0.1.md <<'EOF'
# Org-Wide Software Factory
## Discovery PRD v0.1

**Date:** 2026-07-26  
**Status:** Discovery draft; not approved for implementation  
**Purpose:** Convert the initial vision into explicit product requirements, provisional design decisions, non-goals, and interview questions.  
**Out of scope for this version:** Product naming, detailed technology selection, infrastructure sizing, implementation phases, and delivery estimates.

---

## 1. Executive summary

The proposed product is an **organization-wide, model-agnostic software-delivery operating system**. It accepts business intent, turns that intent into a versioned and testable specification, decomposes the work into bounded tasks, assigns those tasks to replaceable agent harnesses and models, verifies the results with deterministic evidence, coordinates human decisions, releases changes under policy, observes production outcomes, and converts validated experience into reusable organizational knowledge.

The product is **not primarily a coding agent**. Frontier models will improve rapidly and individual coding harnesses will be replaced frequently. The enduring product is the system around them:

- durable workflow and resumability;
- intent, specification, and evaluation contracts;
- policy and authority boundaries;
- isolated and reproducible execution environments;
- event, trace, artifact, and provenance capture;
- context compilation and organizational knowledge;
- evidence-based completion decisions;
- model and harness portability;
- continuous, evaluation-gated improvement.

The core design thesis is:

> **Deterministic software owns control, state, permissions, scheduling, retries, and evidence. Models provide bounded semantic judgment and generation.**

A second critical distinction is:

> **The evidence lake records what happened; the knowledge system contains only what has been curated and validated as reusable truth.**

Storing every trace is valuable, but raw traces, model claims, failed attempts, and temporary hypotheses must never automatically become authoritative organizational knowledge.

---

## 2. Product vision

A requester should be able to describe a desired outcome in a familiar work system and then observe a transparent factory process that:

1. determines whether the request is actionable;
2. asks concise, high-value clarification questions when it is not;
3. creates an approved, versioned specification and evaluation plan;
4. plans the work as a dependency graph of small, testable work packages;
5. executes work in isolated, resumable environments;
6. applies test-first development and deterministic verification;
7. uses one or more models when independent judgment adds value;
8. produces a complete evidence package for every decision;
9. deploys only within explicit risk and approval policies;
10. observes the outcome and proposes validated improvements to the factory.

The long-term aspiration is assembly-line delivery speed without sacrificing correctness, security, auditability, or human authority.

---

## 3. Problem statement

Current coding agents can generate substantial amounts of code, but organization-wide delivery still fails at the boundaries around code generation:

- business requests are incomplete, ambiguous, or contradictory;
- agents lack authoritative organizational context;
- sessions are fragile and difficult to resume;
- large tasks exceed reliable context and planning horizons;
- agents can write tests that merely confirm their own implementation;
- “green CI” does not necessarily mean the business outcome is correct;
- multiple tools and agents produce disconnected traces and artifacts;
- model-specific sessions and prompt formats create vendor lock-in;
- production permissions are too broad or poorly governed;
- lessons from prior work remain buried in chat histories;
- teams cannot explain exactly why a change was considered complete;
- continuous self-improvement can silently promote bad lessons.

The factory must solve these coordination, evidence, context, and governance problems rather than merely wrap several coding models in a queue.

---

## 4. Goals

### G1. Intent-to-evidence delivery
Convert a business request into an executable specification, verified change, and traceable completion decision.

### G2. Durable, resumable execution
Survive process crashes, model limits, network failures, machine restarts, deployment interruptions, and worker replacement with minimal repeated work.

### G3. Model and harness independence
Support OpenAI, Anthropic, Google, open-weight models, and future providers through stable internal contracts. Treat provider sessions as replaceable optimizations rather than canonical state.

### G4. Closed-loop correctness
Use deterministic tests, independent review, runtime evidence, and explicit acceptance criteria to decide whether the requested behavior has been delivered.

### G5. Organization-wide context
Make relevant product, domain, architecture, operational, security, and historical knowledge available within bounded token budgets and with source provenance.

### G6. Complete permissible observability
Capture every externally visible factory action, input, output, tool call, environment change, artifact, decision, and evaluation result that policy permits.

### G7. Incremental autonomy
Begin with limited authority and expand automation only for task classes whose measured evidence supports it.

### G8. Continuous learning with guardrails
Turn production feedback and historical traces into proposed improvements, evaluate those proposals, and publish only validated knowledge, skills, policies, or routing changes.

### G9. Open and self-hostable control plane
Use open-source or internally built components for the control plane, execution plane, data plane, observability, knowledge, user interface, and policy enforcement.

### G10. Simple human experience
Keep task submission and status consumption simple while preserving deep operator-level inspection when needed.

---

## 5. Non-goals

The first product should not attempt to:

- build a new general-purpose issue tracker;
- replace source control, CI/CD, or infrastructure-as-code ecosystems;
- create a single universal “super-agent” that owns the whole lifecycle;
- make an LLM responsible for queue polling, liveness, retries, or permission enforcement;
- use a graph database or vector database as the sole source of organizational truth;
- run multi-model debates for every routine task;
- make high-risk production changes without explicit policy and human authority;
- allow agents to modify prompts, policies, tests, or knowledge directly in production without evaluation and approval;
- create a network microservice for every conceptual agent role;
- promise exact resumption in the middle of an unfinished model token stream;
- claim access to unexposed model internals or hidden reasoning;
- launch across every repository and task class in the first pilot;
- reduce completion to an unexplained single Boolean.

---

## 6. Product principles

### P1. Deterministic control plane
Scheduling, state transitions, permissions, retries, budgets, deduplication, and release gates are code and policy—not model decisions.

### P2. Replaceable intelligence
Every model and agent harness is behind an adapter with explicit capabilities, limits, and measured performance.

### P3. Specifications before implementation
No implementation starts until the task reaches a defined Definition of Ready, except an explicitly classified research or discovery workflow.

### P4. Evidence before completion
A task is complete only when its required evidence has been produced and independently evaluated against the approved specification.

### P5. Resumability by construction
Each meaningful activity produces a durable checkpoint and immutable result reference.

### P6. Test-first by default
Behavioral and technical checks are authored before implementation whenever the behavior is testable. Exceptions must be explicit.

### P7. Least privilege and isolation
Each task receives the minimum tools, repositories, credentials, network access, and production authority required.

### P8. Events for visibility; workflows for control
The architecture is event-driven, but a durable orchestrated workflow owns what must happen next. Pure event choreography must not obscure business state.

### P9. Raw history is not knowledge
Traces and logs are evidence. Reusable knowledge must be attributed, scoped, validated, versioned, and reversible.

### P10. Roles are contracts, not services
Architect, reviewer, tester, and implementer are logical responsibilities. They need not become separate deployed services.

### P11. Small work packages, not microscopic fragmentation
Decompose until each unit has a clear contract, bounded context, isolated change surface, and deterministic verification. Stop before coordination overhead exceeds reliability gains.

### P12. Humans retain authority
Business owners decide intent and tradeoffs. Platform and security owners define policy. Agents may recommend, execute, and verify only within delegated authority.

---

## 7. Scope by priority

### 7.1 Must have for the first credible product slice

- Work-item adapters for at least one existing ticket or forge system.
- Canonical internal work-item, specification, plan, run, artifact, and evaluation schemas.
- Deterministic intake watcher and dispatcher.
- Semantic triage and clarification workflow.
- Versioned specification and evaluation-plan creation.
- Durable workflow state and checkpointing.
- Isolated per-task execution workspace.
- Model and harness adapter layer.
- Context compiler with token budgets and source manifests.
- Test-first execution loop.
- Independent verification and review.
- Immutable event, trace, model-call, tool-call, and artifact capture.
- Pause, cancel, resume, retry, and fork controls.
- Risk-based policy and approval gates.
- Real-time task-progress user interface.
- Pull-request or change-set output with a completion evidence package.
- Infrastructure-as-code validation for infrastructure tasks.

### 7.2 Should have after the first vertical slice

- Multiple workflow templates by task and risk class.
- Multi-model architecture review and adversarial review gates.
- Cross-repository planning and integration.
- Production observation linked back to specification and change.
- Curated organizational knowledge packs.
- Graph, vector, and lexical derived indexes.
- Automated learning-proposal generation from traces and outcomes.
- Low-risk auto-merge and controlled staging deployment.
- Historical replay and regression evaluation suites.
- Task and model routing based on measured internal performance.

### 7.3 Later capabilities

- Proactive “dreaming” or opportunity-discovery agents.
- Incident-to-remediation loops.
- Continuous architecture and dependency-health agents.
- Autonomous low-risk production deployment.
- Organization-wide portfolio optimization.
- Automated creation of new agent skills and workflow templates after gated evaluation.
- Large-scale experiment loops that optimize factory policies against business metrics.

---

## 8. Human and machine actors

### Human actors

| Actor | Primary authority |
|---|---|
| Business requester | Desired outcome, urgency, business constraints |
| Domain owner | Domain correctness and behavioral acceptance |
| Engineering owner | Repository ownership and technical accountability |
| Architecture authority | Cross-cutting design constraints and exceptions |
| Security/platform owner | Mandatory controls, access, release policy |
| Reviewer/approver | Human judgment at configured gates |
| Factory operator | Capacity, incidents, routing, policy operation |
| Auditor | Reconstruction of actions, evidence, and authority |

### Logical machine roles

| Role | Responsibility |
|---|---|
| Intake normalizer | Convert external tickets into the canonical work-item schema |
| Triage agent | Classify intent, scope, risk, affected domains, and likely workflow |
| Clarification/specification agent | Identify ambiguity, ask structured questions, and draft the specification |
| Architecture agent | Review boundaries, constraints, dependencies, and plan shape when risk warrants it |
| Evaluation designer | Convert acceptance criteria into executable and reviewable checks |
| Planner | Produce a dependency graph of bounded work packages |
| Implementer | Execute a work package using a selected model and harness |
| Reviewer/challenger | Independently inspect implementation, assumptions, and evidence |
| Integrator | Reconcile work packages and run system-level verification |
| Release agent | Prepare release evidence and perform allowed deployment actions |
| Observer | Connect runtime outcomes, regressions, and incidents to the originating change |
| Learning curator | Propose reusable lessons, skills, and policy changes from evidence |

The **policy engine, workflow orchestrator, dispatcher, credential broker, and audit recorder are not LLM agents**.

---

## 9. Conceptual architecture

```text
Human surfaces
  Ticket / Forge / API / Chat / Factory UI
                     │
                     ▼
Control plane
  Intake adapters ─ Canonical work item ─ Durable workflow/state machine
         │                 │                         │
         │                 ├─ Policy & risk engine   ├─ Scheduler/dispatcher
         │                 ├─ Spec/eval service      ├─ Model/harness gateway
         │                 ├─ Context compiler       ├─ Resource manager
         │                 └─ Approval service       └─ Event publisher
                     │
                     ▼
Execution plane
  Ephemeral sandbox / worktree / dev environment
  Agent harness adapter → model provider or open-weight runtime
  Tools → source control, build, test, scanners, IaC, preview, deployment
                     │
                     ▼
Evidence and knowledge plane
  Durable workflow history
  Append-only event ledger
  Content-addressed artifact store
  Trace and metric backend
  Analytical lakehouse
  Operational read models
  Curated knowledge repository
  Graph/vector/lexical derived indexes
  Provenance and lineage graph
                     │
                     ▼
Real-time UI, reporting, audit, eval analytics, and learning proposals
```

### Architectural boundary

The factory should own a **model-neutral task protocol**, not a provider-specific conversation protocol. A task must be reconstructible from factory artifacts even when the original provider session no longer exists.

---

## 10. End-to-end lifecycle

### 10.1 Intake

A business requester creates or updates a ticket. A deterministic webhook consumer or polling adapter normalizes it into an internal `WorkItem` and emits an intake event.

The external ticket remains the human-facing control surface. The internal workflow ledger is authoritative for machine execution state. Status summaries and questions are mirrored back to the ticket.

### 10.2 Deterministic eligibility and policy check

Code validates required fields, requester authority, repository scope, duplicate requests, policy restrictions, and whether the requested action is supported.

### 10.3 Semantic triage

A bounded triage agent determines:

- request type;
- affected products, services, repositories, and teams;
- likely risk class;
- whether the task is implementation, investigation, migration, infrastructure, documentation, or another workflow;
- missing information;
- whether architecture review is required;
- an initial complexity and confidence estimate.

Low-confidence or high-impact classifications may receive a second independent review. Routine classifications should not automatically invoke the most expensive model.

### 10.4 Clarification

A clarification/specification agent posts a **small grouped set of structured questions** to the ticket. Each question should include:

- why the answer matters;
- the decision it affects;
- a recommended default when appropriate;
- the consequence of accepting that default;
- who has authority to answer.

The workflow enters `NEEDS_CLARIFICATION` and does not begin implementation until required answers or explicitly approved assumptions exist.

A centralized “lead architect” should not review every ticket. Architecture review is a risk-based gate; otherwise it becomes an expensive serial bottleneck.

### 10.5 Specification and evaluation design

The factory creates a versioned specification package:

1. **Intent specification** — user, problem, outcome, scope, constraints, exclusions.
2. **Behavioral specification** — scenarios, examples, invariants, failure behavior, compatibility requirements.
3. **Technical contract set** — interfaces, schemas, dependency boundaries, data migrations, architecture fitness rules.
4. **Evaluation plan** — tests, runtime observations, security checks, performance checks, review criteria, rollout evidence.
5. **Release and rollback plan** — deployment scope, canary, observability, rollback trigger.

The output should be concise and executable, not a large prose document created for its own sake.

### 10.6 Definition of Ready decision

The task becomes ready only when the required specification fields, approvals, risks, dependencies, and evaluation criteria are present.

### 10.7 Planning

The planner produces a dependency graph rather than one long to-do list. Each node has:

- one bounded objective;
- explicit inputs and outputs;
- repository and path scope;
- allowed tools and permissions;
- preconditions and dependencies;
- required tests and evidence;
- completion conditions;
- checkpoint policy;
- maximum attempts, token budget, and time budget;
- escalation path.

Independent work packages may run in parallel, normally in separate worktrees or isolated workspaces.

### 10.8 Test-first execution

For testable behavior, the relevant failing acceptance, contract, or unit tests are produced before implementation. The implementer then executes a red–green–refactor loop and records each iteration.

### 10.9 Continuous verification

Every bounded step can invoke deterministic tools. Failing evidence routes the work back to the smallest responsible work package rather than restarting the entire feature.

### 10.10 Independent review and integration

A reviewer that did not author the change examines the specification, changed code, tests, evidence, and unresolved risks. For high-risk changes, the first review should be blind to the author agent’s persuasive rationale to reduce anchoring.

The integrator combines accepted work packages and runs system-level checks.

### 10.11 Release

Policy determines whether the factory may:

- open a pull request only;
- deploy a preview environment;
- deploy to staging;
- auto-merge a low-risk change;
- perform a canary deployment;
- require one or more human approvals.

### 10.12 Observation and learning

Post-release signals are linked to the originating specification, implementation, and deployment. The factory may create learning proposals, regression tests, documentation updates, or follow-up tickets. It may not silently rewrite authoritative knowledge or policy.

---

## 11. Workflow states

```text
RECEIVED
  → NORMALIZING
  → TRIAGING
  → NEEDS_CLARIFICATION ↔ TRIAGING
  → SPEC_DRAFTING
  → SPEC_REVIEW
  → READY
  → PLANNING
  → EXECUTING
  → VERIFYING ↔ EXECUTING
  → REVIEWING ↔ EXECUTING
  → INTEGRATING
  → RELEASE_READY
  → DEPLOYING
  → OBSERVING
  → DONE
```

Any active state may transition to `PAUSED`, `BLOCKED`, `FAILED`, `CANCELED`, or an explicitly approved replanning state. Resume must continue from durable history and the most recent accepted checkpoint.

---

## 12. Definition of Ready

A normal implementation request is ready when all mandatory items are satisfied:

- a named requester and domain owner exist;
- the desired user or business outcome is explicit;
- in-scope and out-of-scope behavior is explicit;
- representative examples and edge cases exist;
- affected systems are identified with adequate confidence;
- required data and security classifications are known;
- compatibility and migration constraints are recorded;
- business acceptance criteria are approved by the appropriate owner;
- technical and policy criteria have been added;
- unresolved assumptions are accepted by an authorized person;
- evaluation feasibility is confirmed;
- the intended release and rollback boundary is known;
- dependencies and blockers are visible;
- a risk class and workflow template are assigned.

Research tasks use a separate Definition of Ready based on a question, evidence plan, bounded search space, and stopping condition.

---

## 13. Definition of Done and completion decision

### 13.1 Ownership of criteria

| Criterion | Drafted by | Approved or enforced by |
|---|---|---|
| Business behavior | Specification agent | Requester/domain owner |
| User scenarios and examples | Specification/evaluation agents | Domain owner |
| Architecture constraints | Architecture agent or repository policy | Engineering/architecture authority |
| Security and compliance | Policy and security tooling | Security/platform authority |
| Performance and reliability | Evaluation agent | Service owner/SRE policy |
| Test implementation | Evaluation agent or test worker | Independent verifier and CI |
| Release evidence | Release agent | Release policy and configured humans |

No single model should create the implementation and be its only judge.

### 13.2 Evidence vector

The internal completion decision is a structured vector, not a bare Boolean:

- behavioral acceptance;
- unit, property, contract, integration, and end-to-end checks as applicable;
- static analysis and dependency policy;
- security controls;
- architecture fitness rules;
- performance and reliability thresholds;
- migration and rollback validation;
- infrastructure repeatability and idempotence;
- independent review;
- evidence completeness and provenance;
- deployment and canary health;
- required human approvals.

The resulting state is one of:

- `PASS` — all mandatory gates satisfied;
- `FAIL` — one or more mandatory gates failed;
- `BLOCKED` — external information or authority is required;
- `INCONCLUSIVE` — the evaluation cannot reliably decide.

The business-facing interface may display “Done: yes/no,” but only `PASS` maps to yes, and the underlying evidence remains visible.

### 13.3 Bounded iteration

“Work until yes” must include:

- maximum attempts and resource budgets;
- no-progress and repeated-failure detection;
- prohibition on weakening tests to obtain a pass;
- escalation to replanning, a stronger model, a different harness, or a human;
- a terminal `INCONCLUSIVE` or `BLOCKED` outcome when correctness cannot be established.

---

## 14. Test-first development policy

Test-first development is a design constraint, not merely a final verification step.

### Required behavior

- Acceptance and contract checks should be created before implementation whenever feasible.
- The implementer should begin from a demonstrably failing check.
- Acceptance tests and mandatory policy checks are versioned and protected.
- An implementer cannot delete, weaken, skip, or rewrite mandatory checks without a specification-change workflow.
- Critical components should use property-based, mutation, fuzz, or model-based testing where valuable.
- Architecture rules should be executable as fitness functions where possible.
- Production regressions should become durable regression cases.
- Some adversarial or holdout evaluations may remain hidden from the implementer to reduce overfitting.

### Explicit exceptions

Research spikes, documentation-only tasks, characterization of unknown legacy behavior, and certain migrations may begin with evidence collection rather than a failing unit test. The workflow must record the exception and substitute an appropriate evaluation plan.

### Infrastructure-as-code requirements

An infrastructure task must, as applicable, demonstrate:

- syntax and policy validation;
- plan or dry-run output;
- repeatable creation from a clean environment;
- a second application that produces no unintended changes;
- drift detection;
- rollback or recovery validation;
- post-deployment health checks;
- artifact and supply-chain provenance.

---

## 15. Resumability requirements

Resumability is a product invariant.

### 15.1 Durable units

Every work item, workflow, specification, plan, task node, attempt, model invocation, tool invocation, artifact, policy decision, and evaluation result receives a durable identifier.

### 15.2 Checkpoint contents

At a meaningful microstep boundary, a worker records:

- current work-item, spec, plan, and task versions;
- completed actions and immutable results;
- current hypotheses and unresolved questions;
- files changed and a workspace commit or snapshot;
- commands executed and their outputs;
- test state and known failures;
- environment image and tool versions;
- exact context manifest supplied to the model;
- next intended action;
- side effects already committed;
- idempotency and deduplication keys.

### 15.3 Resume semantics

A resumed worker receives a model-neutral `ResumePacket` and the corresponding workspace snapshot. It should not need the original provider chat session.

Completed activities are not repeated unless explicitly invalidated. In-progress side-effect-free work may be retried. Side-effecting activities require pre-recorded intent, idempotency keys, and post-recorded results.

The practical minimum loss window is one unacknowledged in-flight model or tool call. Partial streams may be retained for audit, but exact continuation from the middle of a model generation is not guaranteed.

### 15.4 Additional controls

The factory must support:

- pause and resume;
- cancel with cleanup;
- retry from last checkpoint;
- retry from an earlier approved checkpoint;
- fork an alternative plan or model run;
- migrate execution to a different worker;
- replay historical workflows in non-effecting mode;
- workflow and activity versioning across factory upgrades.

---

## 16. Event-driven architecture

The factory should use **orchestrated event-driven architecture**.

### Commands and ownership

A durable workflow receives commands and owns the required next transition. It emits domain events after durable state changes.

### Events and consumers

Events feed:

- real-time user-interface projections;
- ticket updates;
- audit and reporting;
- trace correlation;
- analytical storage;
- production observation;
- knowledge and learning pipelines;
- external integrations.

### Reliability rules

- Delivery is assumed to be at least once.
- Consumers are idempotent.
- State change and event publication use an atomic outbox or equivalent mechanism.
- Events are schema-versioned.
- Causation and correlation identifiers are mandatory.
- Agents cannot subscribe freely and create unbounded work outside policy.
- The event bus is not the workflow state store.

A common event envelope should follow an open, portable convention such as CloudEvents while allowing factory-specific extensions.

---

## 17. Logical evidence and storage architecture

No single database should be forced to serve every purpose.

| Layer | Purpose | Authority |
|---|---|---|
| Durable workflow history | State transitions, timers, retries, checkpoints | Authoritative execution history |
| Operational relational store | Current work items, approvals, policies, projections | Authoritative current operational data where assigned |
| Append-only event ledger | All normalized domain and activity events | Authoritative event record |
| Content-addressed artifact store | Full prompts, responses, tool I/O, files, logs, screenshots, builds, reports | Authoritative bytes, addressed by hash |
| Trace backend | Fast causal navigation across services and agent activity | Operational observability index |
| Analytical lakehouse | Petabyte-scale query, evaluation analytics, replay datasets | Analytical history derived from events/artifacts |
| Curated knowledge repository | Approved reusable facts, rules, decisions, playbooks | Authoritative knowledge within declared scope |
| Graph/vector/lexical indexes | Retrieval and relationship navigation | Rebuildable derived indexes |
| Secret and sensitive-data vault | Restricted values when retention is legally or operationally required | Restricted authority with separate access |

### 17.1 Role of Apache Iceberg

Iceberg is a strong candidate for the analytical history because it supports very large tables, schema evolution, snapshots, and time travel. It should not be treated as the live queue, workflow engine, operational state database, or low-latency artifact store.

### 17.2 Artifact strategy

Large or sensitive payloads are stored as immutable artifacts. Events and traces contain references, hashes, classifications, and compact metadata rather than duplicating the full payload.

Artifact types include:

- ticket snapshots and comments;
- specification versions;
- context manifests and rendered context packs;
- prompt templates and final prompts;
- provider requests, streamed output where available, and normalized responses;
- exposed reasoning summaries where provided;
- tool definitions, calls, outputs, and errors;
- source snapshots, patches, commits, and pull requests;
- terminal transcripts;
- test inputs, outputs, coverage, mutation reports, and screenshots;
- build images, packages, SBOMs, signatures, and attestations;
- policy decisions and approvals;
- deployment plans, events, metrics, and rollback evidence;
- reviewer findings and completion certificates.

Only provider-exposed information can be stored. The factory must not claim to capture inaccessible hidden model reasoning.

### 17.3 Required correlation identifiers

At minimum:

- organization, project, product, repository, and environment;
- work item, specification, plan, task node, run, attempt, and session;
- trace and span;
- actor and logical role;
- model invocation and tool invocation;
- artifact and evidence item;
- change set, deployment, and production observation;
- policy version, prompt version, context version, and evaluation-suite version.

### 17.4 Event metadata

Each normalized event should include:

- event ID, type, and schema version;
- occurrence and ingestion timestamps;
- correlation, causation, and parent identifiers;
- actor identity, role, and delegated authority;
- model provider, model identifier, parameters, effort mode, and harness version when applicable;
- input and output artifact references;
- environment image, workspace, source revision, and tool versions;
- status, error class, latency, token usage, cache usage, and resource consumption;
- security classification, access policy, and retention policy;
- content hashes and optional signatures.

### 17.5 Governance of “store everything”

The requirement is **capture everything permissible**, not copy every secret into an unrestricted data lake.

- Secrets should be brokered and redacted before they reach prompts or general logs.
- Sensitive raw payloads require separate encryption, access control, audit, and retention policy.
- Personal and regulated data require purpose, residency, erasure, and legal-hold rules.
- Immutable audit requirements must coexist with legally required deletion through encryption-key or reference-management strategies.
- Hot, warm, and cold tiers remain useful for query performance and operational safety even when capacity is abundant.

### 17.6 Open standards to align with

- CloudEvents-style event envelopes;
- OpenTelemetry traces, metrics, logs, and emerging GenAI/MCP semantic conventions;
- W3C PROV concepts for entities, activities, agents, and derivation;
- OpenLineage-style run, job, dataset, and artifact lineage;
- content-addressed and signed artifacts.

---

## 18. Knowledge and context architecture

### 18.1 Four distinct memory classes

1. **Authoritative source knowledge**  
   Code, versioned specifications, architecture decisions, policies, service catalogs, runbooks, domain documents, schemas, and approved ticket decisions.

2. **Curated reusable knowledge**  
   Validated playbooks, coding rules, glossary entries, failure patterns, examples, and lessons with ownership and scope.

3. **Derived retrieval indexes**  
   Graph, vector, lexical, code, and metadata indexes built from authoritative and curated sources.

4. **Ephemeral working memory**  
   Task-local hypotheses, summaries, scratch notes, and resume packets. These are evidence, not organizational truth.

### 18.2 Knowledge item metadata

Every reusable knowledge item should state:

- source and provenance;
- owner and approver;
- scope by organization, product, repository, service, and task class;
- validity interval and freshness requirement;
- confidence and validation evidence;
- security classification and access policy;
- superseded and superseding versions;
- retrieval tags and relationships;
- evaluation history and observed usefulness.

### 18.3 Context compiler

Agents should not query the entire organization directly. A context compiler assembles a versioned, budgeted `ContextPack` containing only what the role and task require, such as:

- approved specification and task contract;
- relevant source and architecture map;
- repository instructions and allowed tools;
- domain glossary and constraints;
- similar historical changes and validated lessons;
- known failure modes;
- test and evaluation requirements;
- current workspace state;
- citations and content hashes for every retrieved item.

The compiler should optimize for **accepted outcome per token**, not minimum tokens in isolation.

### 18.4 Graph plus vector retrieval

Graph and vector retrieval are complementary, but both are derived indexes:

- vectors find semantically similar material;
- graphs answer relationship and lineage questions;
- lexical and structured queries provide precision;
- source files and versioned knowledge remain authoritative.

The first product should validate whether a dedicated graph database is necessary rather than assuming one. A simpler relational-plus-vector implementation may be sufficient for the pilot.

### 18.5 Role of MCP

MCP is useful as a model-facing adapter for exposing tools, resources, and reusable prompts. It is not, by itself:

- a knowledge database;
- durable workflow state;
- an authorization system;
- a provenance model;
- a canonical factory schema;
- a replacement for policy enforcement.

### 18.6 Role of Google Open Knowledge Format

OKF is a promising format for portable, human-readable, model-friendly curated knowledge packs. It can be used as an import/export and repository format. It should not replace the operational database, event ledger, artifact store, graph index, or workflow state.

### 18.7 Learning pipeline

```text
Raw evidence and production outcomes
  → candidate lesson extraction
  → provenance and scope assignment
  → deduplication and conflict detection
  → offline evaluation against historical tasks
  → human or policy approval
  → versioned publication to curated knowledge
  → monitored use in future tasks
  → rollback, revise, or promote
```

Agents may propose knowledge. They do not directly promote their own claims into authoritative memory.

---

## 19. Model- and harness-agnostic architecture

### 19.1 Stable internal contracts

The factory should define provider-neutral contracts such as:

- `AgentTask`;
- `ContextPack`;
- `ToolCapabilitySet`;
- `ExecutionPolicy`;
- `Checkpoint` and `ResumePacket`;
- `AgentResult`;
- `ReviewFinding`;
- `EvaluationResult`.

### 19.2 Separate model and harness adapters

A model is not the same as a harness. The factory may integrate:

- a raw model API with its own tool loop;
- Codex app-server or CLI;
- Claude Code;
- Gemini CLI or another Google harness;
- an open-source coding harness;
- an internally built specialized worker.

The harness adapter translates factory tasks, events, tools, and checkpoints. The model adapter handles provider-specific inference controls.

### 19.3 Capability registry

Each adapter should declare and continuously test:

- supported models and context limits;
- structured-output reliability;
- tool and MCP support;
- streaming and cancellation;
- session persistence and compaction;
- sandbox assumptions;
- checkpoint/resume behavior;
- cost, latency, and rate limits;
- data-retention and residency properties;
- known task strengths and failure modes;
- internal evaluation results by task class.

### 19.4 Routing policy

Model routing should use task type, risk, context size, required tools, latency target, cost budget, and measured historical performance. A named frontier model should not be hard-coded as permanent architecture.

### 19.5 Multi-model policy

Use multiple models where independent judgment materially reduces uncertainty:

- specification or architecture decisions;
- high-risk security review;
- repeated implementation failure;
- ambiguous root-cause analysis;
- release adjudication;
- evaluation creation for critical behavior.

Routine tasks should normally use one implementation model plus deterministic checks and an appropriately independent reviewer.

Consensus is not evidence. Models can share correlated blind spots. Disagreement should trigger better tests, more source evidence, replanning, or human judgment rather than majority voting alone.

---

## 20. User experience requirements

### 20.1 Requester experience

The requester should see:

- current plain-language status;
- outstanding questions and who must answer;
- approved scope and acceptance criteria;
- expected next gate;
- delivered behavior and completion evidence;
- links to resulting change sets and deployments.

### 20.2 Engineering and operator experience

A detailed run view should provide:

- live state-machine position;
- task dependency graph and parallel workers;
- active model, harness, tool, and environment;
- streaming progress events;
- checkpoint history;
- exact context manifest;
- diffs and artifacts;
- test and evaluation matrix;
- model and tool errors;
- policy decisions and approvals;
- token, cache, latency, and resource usage;
- pause, cancel, retry, resume, fork, and escalate controls;
- end-to-end provenance from request to production observation.

### 20.3 Ticket integration

The ticket should receive concise, durable updates rather than a flood of raw trace events. Full evidence remains in the factory UI and artifact system.

### 20.4 Real-time design

The UI consumes event-driven read models. It does not infer state from parsing agent prose.

---

## 21. Security, policy, and governance requirements

- Per-task identities and short-lived credentials.
- Explicit repository, path, tool, environment, and network permissions.
- Egress restrictions and domain allowlists.
- Secret broker that prevents routine secret exposure to models.
- Ephemeral, isolated execution environments.
- Signed commits, artifacts, SBOMs, and provenance where applicable.
- Prompt-injection and untrusted-content boundaries.
- Tool-call policy enforcement outside the model.
- Budget, rate, concurrency, and runaway-loop limits.
- Human approval gates by risk class.
- Emergency pause and global kill switch.
- Immutable and queryable policy decisions.
- Separation of author, evaluator, and approver for critical changes.
- Model-provider data policy and residency enforcement.
- Supply-chain and license checks for open-source components and generated dependencies.
- No standing production credentials in coding-agent workspaces.

---

## 22. Build, adopt, evaluate, and defer

### 22.1 Build or own as core intellectual property

- Canonical factory schemas and identifiers.
- Durable lifecycle and state-machine definitions.
- Policy, risk, autonomy, and approval model.
- Model and harness gateway contracts.
- Context compiler and context manifests.
- Specification and evaluation contract system.
- Evidence aggregation and completion-certificate logic.
- Learning-promotion workflow.
- Cross-system provenance model.
- User-facing factory experience and read models.
- Internal evaluation corpus and routing intelligence.

### 22.2 Adopt open-source infrastructure instead of rebuilding

- Issue tracker or software forge.
- Durable workflow runtime.
- Event broker.
- Relational operational database.
- Object and artifact storage.
- Apache Iceberg-compatible lakehouse components.
- OpenTelemetry collection and open-source backends.
- Graph, vector, lexical, and code search engines.
- Container or microVM isolation.
- Source control, CI, test, scanner, and IaC ecosystems.
- Identity, policy, secret, and signing primitives where suitable.

### 22.3 Evaluate as reference implementations or optional components

- OpenAI Symphony for issue-driven orchestration patterns.
- OpenAI harness-engineering practices for agent-legible repositories and feedback loops.
- Factory.ai for full-lifecycle product framing and signal-to-action concepts.
- GitHub Next Ace for a shared multiplayer human-agent workspace.
- GitHub agentic primitives and context-engineering practices.
- Google OKF for portable curated knowledge.
- Cognee for graph/vector/relational memory experiments.
- Omnigent for harness composition, worktree isolation, and cross-vendor review.
- Tessl for spec-driven workflows and continuous improvement loops.
- Stripe Minions for standardized environments and bounded end-to-end tasks.
- Ramp Inspect for closed-loop verification in full development sandboxes.
- Claude Tag for ambient, shared human-agent intake surfaces.
- Karpathy’s autoresearch for bounded modify–measure–keep/discard loops.
- Buzz as a conceptual shared human/agent workspace, pending more public technical detail.

### 22.4 Drop or defer

- A custom ticket system for the pilot.
- Taskwarrior as the authoritative organization-wide control plane; it may remain a personal or adapter-based input surface.
- An LLM watcher, scheduler, retry manager, or policy engine.
- Pure event choreography for the core lifecycle.
- A single long-running architect session that owns an entire feature.
- A universal graph/vector “brain.”
- Multi-model debate on every work package.
- Immediate high-risk auto-merge or autonomous production access.
- Self-modifying prompts, tests, policies, or knowledge without gated evaluation.
- Recording raw secrets in general prompts, logs, or the analytical lake.
- Hundreds of network services corresponding to agent roles.
- Exact replay of nondeterministic model outputs as a correctness claim.
- Full organization-wide rollout before a narrow vertical slice is measured.

---

## 23. How the referenced landscape informs this PRD

| Reference | Durable lesson to adopt | What not to copy blindly |
|---|---|---|
| OpenAI Symphony | Ticket-driven control surface, continuous watcher, isolated per-work-item execution, restart and parallel task graphs | A provider-specific orchestrator as the permanent core |
| OpenAI harness engineering | Agent-legible environments, strong tests, observability, compact repository maps, continuous cleanup | Assuming model capability compensates for weak environments |
| Factory.ai | Full-SDLC, model-independent, signal-to-action product framing | Commercial platform dependency in the critical path |
| GitHub Next Ace | Shared multiplayer workspace for humans and agents | Treating shared chat context as authoritative organizational memory |
| GitHub context engineering | Reusable instructions, prompts, and role-specific primitives | Unversioned prompt files without evaluation |
| Google OKF | Portable curated knowledge packs using files and metadata | Using OKF as a transactional database or workflow engine |
| Cognee | Graph/vector/relational memory patterns and cross-session recall | Selecting a memory platform before the factory’s knowledge semantics are defined |
| Omnigent | Separate worktrees, cross-vendor review, harness composition | Assuming model debate itself proves correctness |
| Tessl | Specification before code and loop engineering | Large speculative documents that are not executable |
| Stripe Minions | Narrow end-to-end tasks, fast standardized environments, human review | Extrapolating one-shot success to every high-risk task |
| Ramp Inspect | Verification in a real sandbox with real tools and APIs | Equating sandbox access with safe production authority |
| Claude Tag | Ambient shared intake and team-visible delegation | Making chat the durable state machine or audit source |
| Karpathy autoresearch | Bounded action surface, objective metric, keep/discard loop, full experiment log | Infinite optimization without stopping conditions or multi-dimensional safety gates |
| Buzz | Shared humans, agents, and project surface | Depending on a still-sparse public architecture description |

A terminology note: **GitHub Next Ace**, the multiplayer workspace, is distinct from **Agentic Context Engineering (ACE)**, the idea of evolving context through generated, reflected, and curated playbooks. Both ideas are useful but address different layers.

---

## 24. Key risks and mitigations

| Risk | Mitigation direction |
|---|---|
| Incorrect specification produces confidently wrong code | Human-owned behavioral criteria, examples, independent spec review, production feedback |
| Agent writes tests that bless its own implementation | Separate evaluation role, protected acceptance tests, hidden holdouts, mutation/property testing |
| Raw trace pollution becomes “knowledge” | Promotion workflow, provenance, scope, evaluation, approval, rollback |
| Context poisoning or stale instructions | Authority metadata, validity intervals, conflict detection, signed/versioned knowledge |
| Central architect becomes throughput bottleneck | Risk-based architecture gates and repository fitness rules |
| Excessive microtask decomposition | Measure context and integration overhead; use minimum independently verifiable unit |
| Runaway loops and token use | Budgets, no-progress detection, max attempts, escalation |
| Duplicate external side effects after retry | Idempotency keys, pre/post event records, compensation workflows |
| Model drift changes behavior | Pin versions where possible, continuous evals, canary routing, adapter contracts |
| Multi-model consensus creates false confidence | Independent evidence, blind review, deterministic tests, human escalation |
| Complete logging exposes secrets or regulated data | Secret brokering, source redaction, classification, encryption, scoped access |
| Event volume becomes unusable | Semantic schemas, correlation IDs, materialized read models, content-addressed artifacts |
| Open-source supply-chain compromise | Pinning, SBOMs, signatures, sandboxing, update evaluation |
| Agent-generated IaC causes irreversible change | Plan/apply separation, idempotence checks, staged environments, rollback and approval |

---

## 25. Success metrics to finalize during discovery

### Delivery

- Time from request to Definition of Ready.
- Time from Ready to first independently verified change set.
- Time from change set to approved deployment.
- Human minutes required per accepted change.
- Parallel throughput without increased defect rate.

### Correctness and safety

- First-attempt evaluation pass rate.
- Reopen, rollback, and escaped-defect rates.
- Percentage of mandatory criteria backed by deterministic evidence.
- Unauthorized-action count.
- Percentage of changes with complete provenance and reproducible evidence.

### Resumability

- Percentage of interrupted runs resumed without repeating completed activities.
- Mean repeated work after interruption.
- Duplicate side-effect incidents.
- Successful migration between workers or harnesses.

### Context and models

- Input and output tokens per accepted change.
- Cache and reused-artifact efficiency.
- Retrieval precision and source-usefulness ratings.
- Model success rate by task class, risk, and harness.
- Value gained from escalation or multi-model review.

### Learning

- Reuse rate of validated knowledge and skills.
- Improvement in pass rate after a promoted lesson.
- Regression caused by promoted knowledge.
- Time from production signal to validated factory improvement.

### Adoption

- Requester satisfaction and clarification burden.
- Reviewer trust and evidence-consumption time.
- Percentage of eligible work completed at each autonomy tier.

Numeric targets are deliberately deferred until the pilot task class and baseline are chosen.

---

## 26. Provisional decisions

These are recommendations, not yet final decisions.

1. Use an existing open-source issue/forge system or an adapter to the organization’s existing tracker. Do not build a ticket system for the pilot.
2. Make watcher, dispatcher, workflow, retry, policy, and permission handling deterministic code.
3. Use a durable orchestrated workflow that emits events; do not make the event bus alone responsible for lifecycle control.
4. Separate operational state, workflow history, full artifacts, traces, analytics, and curated knowledge.
5. Use Iceberg as an analytical history format, not as the workflow or queue system.
6. Treat graph and vector stores as rebuildable indexes, not the source of truth.
7. Use MCP as an interoperability interface for tools and resources, not as factory memory or policy.
8. Introduce specification and evaluation design before implementation.
9. Use a structured evidence vector internally and derive the final yes/no status from it.
10. Make test-first development the default, with explicit workflow-specific exceptions.
11. Make resume packets and workspace checkpoints provider-neutral.
12. Treat logical agent roles as contracts; begin with a small control plane and isolated workers rather than a microservice explosion.
13. Use one model for routine execution and add independent or multi-model review at uncertainty and risk gates.
14. Keep external frontier models as replaceable compute dependencies; keep the factory control and data planes open-source or internally built.
15. Start with pull-request and preview/staging authority, then earn higher autonomy through measured results.

---

## 27. Assumptions requiring confirmation

- Paid frontier-model inference is allowed even though the factory platform itself must be open-source or self-built.
- The first pilot can be limited to one product area and a small number of repositories.
- A business or domain owner will be available to approve intent and answer blocking questions.
- Production deployment authority can initially remain outside the coding agents.
- The organization is willing to create stronger automated tests and agent-legible development environments where they are currently weak.
- Full capture means all policy-permitted externally visible data, not inaccessible provider internals and not unrestricted secret replication.

---

## 28. Discovery interview — round 1

### Pilot and workload

1. **What exact product, repository set, languages, and deployment platform should be the first vertical slice?**  
   A strong default is one backend service plus its closest UI or client, not the whole organization.

2. **Which initial task classes matter most?**  
   Rank: net-new feature, bug fix, test creation, dependency upgrade, refactor, data migration, infrastructure change, documentation, incident remediation.

3. **Is the pilot primarily brownfield, greenfield, or mixed?**  
   Brownfield quality, test coverage, and undocumented behavior will materially change the product requirements.

### Authority and workflow

4. **What authority should the factory have on day one?**  
   Choose the highest allowed level: analysis only; branch/PR; preview environment; staging deployment; low-risk auto-merge; production canary.

5. **Who has final authority for business behavior, architecture exceptions, security, and release?**  
   Also define the expected response time when the factory posts a blocking question.

6. **Should a ticket be allowed to proceed using a documented default assumption when the requester does not answer, or must it remain blocked?**

### Existing environment

7. **What systems already exist for source control, tickets, CI/CD, chat, documentation, service catalog, observability, cloud/on-prem deployment, and secrets?**

8. **Can proprietary source code, logs, and domain data be sent to external model providers?**  
   Specify permitted providers, data classes, regions, retention requirements, and any zero-data-retention requirement.

9. **What exactly does “every component must be open source or self-built” mean for paid model APIs?**  
   Proposed interpretation: no paid SaaS in the factory control/data plane, while external models remain pluggable paid inference.

### Scale and success

10. **What is the expected first-year scale?**  
    Number of repositories, engineers/requesters, concurrent tasks, daily tickets, environments, and geographic or business-unit boundaries.

11. **Which three outcomes define pilot success?**  
    Examples: lead time, human minutes, accepted changes per week, escaped defects, rollback rate, percentage autonomously completed, or token cost per accepted change.

12. **What is the first risk class the factory must handle successfully?**  
    A useful default is a meaningful but reversible feature that touches real business logic, creates a PR, deploys to a preview or staging environment, and is judged by executable acceptance criteria.

---

## 29. Exit criteria for discovery

This PRD can advance to version 1.0 when:

- the pilot workload and repositories are selected;
- autonomy and human authority boundaries are agreed;
- data and model-provider policies are known;
- the open-source constraint is clarified;
- Definitions of Ready and Done are accepted;
- initial success metrics and baselines are selected;
- the canonical lifecycle and evidence requirements are approved;
- build/adopt/defer decisions are accepted at the product level.

Only then should the implementation plan choose technologies, deployment topology, schemas, phase gates, evaluation datasets, staffing, and delivery sequence.

---

## 30. Research basis for this discovery draft

The draft was informed by publicly described concepts and primary documentation from:

- OpenAI: Symphony, harness engineering, Codex harness/app-server, and self-improving agent evaluation loops.
- Factory.ai: full-lifecycle, model-independent software-factory framing.
- GitHub Next and GitHub: Ace multiplayer workspace, Continuous AI, agentic workflows, and context engineering.
- Google Cloud: Open Knowledge Format.
- Cognee: open-source graph/vector/relational agent memory.
- Omnigent: multi-harness composition, separate worktrees, cross-vendor review, and model debate.
- Tessl: spec-driven development and loop engineering.
- Stripe: Minions and standardized end-to-end agent workflows.
- Ramp: Inspect and closed-loop sandbox verification.
- Anthropic: Claude Tag as a shared team-facing agent surface.
- Andrej Karpathy: autoresearch and LLM-wiki patterns.
- CNCF and open standards: CloudEvents, OpenTelemetry, Apache Iceberg, W3C PROV, and OpenLineage.
- Durable execution systems: Temporal and related workflow patterns.

Source links and citations are provided in the accompanying conversation. Product claims should be revalidated during implementation planning because this landscape changes rapidly.
EOF
stat -c '%n %s bytes' /mnt/data/org_wide_software_factory_discovery_prd_v0.1.md
wc -l /mnt/data/org_wide_software_factory_discovery_prd_v0.1.md
```

> 💭 **Drafted software factory discovery PRD**

> 💭 **Confirming the direction**
> I’ve shaped the draft around deterministic orchestration, evidence-first storage, curated knowledge, bounded autonomy, resumability, and spec-driven delivery. I’m now ready to interview the user and refine the requirements before implementation planning.

> 🔍 **Tool call → `container.exec`**

```unknown
bash -lc ls -l /mnt/data/org_wide_software_factory_discovery_prd_v0.1.md && sed -n '1,80p' /mnt/data/org_wide_software_factory_discovery_prd_v0.1.md && printf '\n---END---\n' && tail -n 80 /mnt/data/org_wide_software_factory_discovery_prd_v0.1.md
```

> 💭 **Inspected Software Factory Discovery PRD**

> 🔍 **Tool call → `web.run`**

```json
{
  "open": [
    {
      "ref_id": "turn200504search0"
    },
    {
      "ref_id": "turn200504search1"
    },
    {
      "ref_id": "turn508867search1"
    },
    {
      "ref_id": "turn756639search0"
    },
    {
      "ref_id": "turn756639search1"
    },
    {
      "ref_id": "turn592003search0"
    },
    {
      "ref_id": "turn698607search5"
    },
    {
      "ref_id": "turn756639search3"
    },
    {
      "ref_id": "turn577732search10"
    },
    {
      "ref_id": "turn849975search0"
    },
    {
      "ref_id": "turn633151search0"
    },
    {
      "ref_id": "turn488836search2"
    },
    {
      "ref_id": "turn199870search3"
    },
    {
      "ref_id": "turn199870search1"
    },
    {
      "ref_id": "turn199870search2"
    }
  ],
  "response_length": "long"
}
```

*The PRD now centers on durable Work Packages and separates immutable evidence from curated knowledge, while avoiding premature service boundaries. Remaining questions concern organizational scope and agent authority.*

> 💭 **Searched 13 websites**

*Worked for 18m 49s*

# The product we are actually defining

This is not merely a coding-agent orchestrator. It is an **organization-wide intent-to-production operating system** with three reinforcing loops:

1. **Delivery loop:** request → clarification → specification → plan → implementation → release.
2. **Assurance loop:** acceptance criterion → evaluator → evidence → gate → pass/fail.
3. **Learning loop:** traces → failure patterns → improvement proposal → replay/evaluation → controlled promotion.

The central architectural principle should be:

> **Deterministic control plane outside; probabilistic intelligence inside bounded nodes.**

That means LLMs reason, plan, implement, review, and synthesize. Ordinary code owns lifecycle, state, retries, locks, permissions, budgets, evidence, and release authority.

This is consistent with the strongest ideas in the current landscape. Symphony turns the work tracker into the control surface rather than asking humans to supervise individual coding sessions; GitHub Next’s Ace explores a shared, multiplayer workspace; Factory frames the product as a full signal-to-production feedback loop rather than a standalone agent. ([OpenAI](https://openai.com/index/open-source-codex-orchestration-symphony/))

## The seven logical planes

| Plane | Responsibility |
|---|---|
| **Intent and collaboration** | Requests, discussions, clarification questions, specifications, approvals, and human steering. |
| **Control** | Durable workflows, queueing, scheduling, retries, model routing, budgets, policies, locks, and state transitions. |
| **Execution** | Sandboxed workspaces, coding agents, tools, builds, tests, deployments, and infrastructure operations. |
| **Assurance** | Acceptance criteria, test oracles, independent reviews, evidence collection, risk gates, and Definition of Done. |
| **Evidence and provenance** | Events, traces, prompts, responses, tool calls, artifacts, diffs, environments, costs, and lineage. |
| **Knowledge and context** | Domain knowledge, architecture, glossary, decisions, ownership, APIs, runbooks, incidents, and context compilation. |
| **Kaizen and learning** | Failure mining, prompt and skill improvement, missing-test discovery, routing experiments, replay, and controlled promotion. |

These are logical boundaries. They do not imply seven separately deployed microservices.

A simplified flow is:

```text
Business signal
      ↓
Canonical Work Item
      ↓
Triage and clarification
      ↓
Versioned specification
      ↓
Acceptance criteria + evaluation design
      ↓
Architecture and work-unit DAG
      ↓
Parallel TDD implementation
      ↓
Independent evidence-based evaluation
      ↓
Review / release / runtime verification
      ↓
Knowledge update and kaizen
```

Every semantic transition emits an event, but the mission itself remains owned by a durable workflow.

---

# Decisions I would lock in now

## 1. The watcher should be pure code

The queue watcher or dispatcher should not be an LLM.

It should perform:

- Polling or event consumption.
- Validation and deduplication.
- Lease acquisition.
- Priority and dependency checks.
- Starting or resuming a durable workflow.
- Backoff, retries, and dead-letter handling.
- Budget and capacity enforcement.

After the item has been safely acquired, an LLM-based triage role can classify it, identify ambiguity, estimate affected domains, and recommend routing.

Using an LLM for queue ownership would add nondeterminism, latency, cost, and failure modes without adding useful intelligence.

## 2. Do not build a complete ticketing system first

Build a **canonical internal Work Item model** and intake adapters.

Taskwarrior can be one adapter for a small experiment, but it should not define the product’s internal ontology. For an organization-wide system, the important requirements are not whether an LLM knows how to operate the tracker. They are:

- Human collaboration.
- Comments and clarification.
- Permissions.
- Attachments.
- Accountable approval.
- State history.
- Links to specifications, evidence, PRs, and deployments.
- Real-time progress.

The factory UI should expose factory-specific state, while intake adapters can support an existing open-source tracker, chat, API, CLI, or native submission form.

The canonical model should remain independent of all of them.

## 3. Use orchestration and events together

“Everything emits events” is correct, but a choreography-only system will become an untraceable network of reactions.

Use:

- **Commands** for requested actions: `CreateSpecification`, `RunEvaluation`, `DeployCandidate`.
- **Domain events** for facts: `SpecificationApproved`, `CriterionFailed`, `DeploymentVerified`.
- **Traces** for technical execution detail.
- **Artifacts** for large payloads.
- **Metrics** for aggregates.
- **A durable workflow** as the owner of an end-to-end mission.

CloudEvents provides a useful standard event envelope, while durable-execution systems demonstrate how an event history can reconstruct state and continue after a worker failure. Temporal, for example, resumes workflows by replaying recorded event history and does not re-execute already completed durable activities. ([CloudEvents](https://cloudevents.io/?utm_source=chatgpt.com))

## 4. “Store everything” needs multiple logical stores

Iceberg alone is not the answer. Nor is a graph database, trace database, or object store alone.

The logical design should be:

### Operational state

Current missions, leases, retries, gates, budgets, workflow history, and resumability state.

### Immutable artifact storage

Large raw objects:

- Prompt and response payloads.
- Streaming chunks.
- Tool inputs and results.
- Source snapshots and diffs.
- Plans and specifications.
- Test reports and logs.
- Screenshots and recordings.
- Environment manifests.
- Compiled artifacts and deployment packages.

Content-address these where practical.

### Event history

Small, typed, versioned facts containing correlation, causation, identity, timestamps, schema versions, classifications, and artifact references.

### Searchable trace projection

Fast UI and troubleshooting queries across runs, agents, model calls, tools, and services.

OpenTelemetry’s GenAI conventions are directly relevant because they provide common attributes for model identity, token usage, prompt and output content where enabled, tool calls, retrieval, and evaluation. ([OpenTelemetry](https://opentelemetry.io/blog/2026/genai-observability/?utm_source=chatgpt.com))

### Analytical lakehouse

This is where Iceberg is compelling: normalized events, model invocations, costs, outcomes, evaluations, routing decisions, and derived learning features. Iceberg’s schema evolution, partition evolution, snapshots, and time travel are suitable for long-term analysis and reproducible experiments. It is not the appropriate sole transactional workflow store. ([iceberg.apache.org](https://iceberg.apache.org/spec/?utm_source=chatgpt.com))

### Lineage graph

Represent relationships such as:

```text
request
  → clarification
  → specification
  → criterion
  → plan
  → work unit
  → agent session
  → model/tool invocation
  → artifact
  → commit
  → build
  → deployment
  → production signal
  → lesson
```

The graph should reference canonical entities and immutable artifacts rather than becoming an opaque second source of truth.

### Important qualification

“Everything” can mean **everything observable at the factory boundary**. It cannot include private model reasoning that a provider does not expose.

It also should not mean blindly duplicating raw credentials into the data lake. Record that credential access occurred, which identity and policy permitted it, and what operation resulted. Store the secret itself only where an explicit retention policy requires it, encrypted and access-restricted.

One petabyte solves capacity. It does not solve semantics, authority, privacy, lineage, or retrieval.

---

# Domain knowledge: use portable source plus derived indexes

Your graph database + vector database + RAG + MCP idea contains useful parts, but they perform different jobs.

## Recommended logical model

### Canonical knowledge source

Use versioned, human-readable documents with:

- Stable concept identifiers.
- YAML or structured metadata.
- Normal links between concepts.
- Source citations.
- Ownership.
- Authority level.
- Valid-from and valid-to dates.
- Supersession links.
- Relevant repositories and commits.
- Review and freshness status.

Google’s Open Knowledge Format is highly relevant here. It is deliberately a format rather than a platform, uses Markdown concepts linked into a graph, supports progressive indexes, and separates producers from consumers. It is suitable as a portable interchange/source layer rather than as a replacement for operational databases. ([Google Cloud](https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing))

### Derived retrieval systems

Build or rebuild several indexes from canonical knowledge and authoritative sources:

- Full-text index for exact search.
- Vector index for semantic similarity.
- Graph index for relationships and traversal.
- Relational index for ownership, status, versions, and filters.
- Code index for symbols, references, dependencies, and diffs.

A graph-vector memory system such as Cognee is worth evaluating, but it should be measured against your provenance, temporal validity, authority, rebuildability, and scale requirements before becoming foundational. Cognee currently presents an open-source memory layer combining graph, vector, and relational retrieval. ([Cognee](https://www.cognee.ai/?utm_source=chatgpt.com))

### MCP

MCP is an interface through which an agent can access knowledge or tools. It is not the knowledge store, knowledge ontology, or freshness mechanism.

A useful principle is:

> **Knowledge lives in portable authoritative sources. Indexes make it findable. MCP makes selected capabilities accessible.**

## The context compiler

Agents should not directly query arbitrary stores and assemble uncontrolled prompts. A Context Compiler should produce a versioned **Context Pack** for each step.

A Context Pack might contain:

- Mission objective and current work-unit contract.
- Exact specification and criteria relevant to the unit.
- Relevant architecture decisions.
- Selected code symbols and dependency edges.
- Applicable policies.
- Known failure patterns.
- Current plan and completed dependency outputs.
- Tool and permission manifest.
- Explicit token budget.
- Provenance for every included item.

This is how you obtain ACE-like organization-wide intelligence without loading the entire organization into every model call.

---

# There are two different “ACE” ideas

This name collision is worth making explicit.

## GitHub Next Ace

GitHub Next’s Ace is a multiplayer software-development workspace: shared conversations, shared plans, cloud microVM-backed sessions, isolated branches, live previews, collaborative prompting, and organization-level orientation. Its strongest lesson for your factory is that alignment and shared visibility need to happen before the PR review stage. ([Maggie Appleton](https://maggieappleton.com/zero-alignment))

## Agentic Context Engineering

The other ACE is Agentic Context Engineering, which treats context as an evolving playbook produced by generation, reflection, and curation. Its strongest lesson is that historical traces should be transformed into evaluated, concise operational knowledge rather than appended indefinitely to prompts. ([GitHub](https://github.com/ace-agent/ace?utm_source=chatgpt.com))

Both belong in the factory:

- GitHub Ace concepts influence the collaboration and UI plane.
- Agentic Context Engineering influences the kaizen and knowledge plane.

---

# Who defines acceptance criteria and Definition of Done?

Acceptance criteria should be created at a dedicated **Specification and Evaluation Design gate**, before implementation planning is approved.

Responsibility should be divided:

| Responsibility | Owner |
|---|---|
| Desired business outcome | Product owner or business owner |
| Domain correctness and rules | Domain owner |
| Drafting atomic criteria and finding ambiguity | Specification agent |
| Technical invariants and architectural constraints | Architect |
| Mapping criteria to executable oracles | Evaluator role |
| Security, reliability, and operational requirements | Security/SRE/platform owners |
| Approval of subjective or high-risk criteria | Accountable human or explicit policy |

The implementation agent may identify a problem with a criterion, but it must not silently redefine the target to make its implementation pass.

## Criterion-level results

Do not have one opaque evaluator answer:

> “Yes, this feature is correct.”

Instead:

```yaml
criterion_id: AC-017
statement: An authenticated user can revoke every active session.
severity: blocking
oracle_type: integration_test
pass_condition: All issued tokens are rejected within 5 seconds.
evidence:
  - test_report_ref
  - service_trace_ref
  - database_state_ref
result: pass
```

Then calculate:

```text
DONE =
  all blocking criteria pass
  AND all required policy gates pass
  AND no prohibited unresolved risk exists
```

Some criteria will remain subjective. They can still produce a governed Boolean through human approval or rubric-based independent evaluation, but the evidence and evaluator identity must remain visible.

## “Keep working until yes”

Keep the goal, but make the loop bounded:

1. Run the evaluator.
2. Classify the failure.
3. Form a targeted repair hypothesis.
4. Change the smallest relevant unit.
5. Re-run affected and regression oracles.
6. After repeated failure, change strategy, model, or plan.
7. Escalate when the specification or evaluator may be wrong.

An unlimited loop can weaken tests, reward-hack an LLM judge, consume unbounded tokens, or repeatedly apply the same incorrect strategy.

---

# Specification-driven development should be foundational—but lightweight

GitHub’s Spec Kit reflects the right direction: specifications become first-class, executable inputs usable by many coding agents. The danger is generating large quantities of prose that are neither authoritative nor evaluable. ([GitHub](https://github.com/github/spec-kit/blob/main/spec-driven.md?utm_source=chatgpt.com))

The factory should maintain layers:

1. **Business intent:** why and for whom.
2. **Behavioral specification:** observable scenarios, constraints, and exclusions.
3. **System contract:** interfaces, invariants, data and failure behavior.
4. **Acceptance model:** criteria, oracles, and evidence.
5. **Technical plan:** how this repository state will change.
6. **Work-unit contracts:** bounded implementation tasks.

The specification should describe the target. The plan should describe the proposed route. Tests and evidence should demonstrate compliance. These should not be collapsed into one giant document.

---

# TDD should be enforced as evidence, not as ceremony

I agree with your rationale: TDD matters because it forces agents to identify boundaries, contracts, dependencies, and observable behavior before implementation.

For behavior-changing units, require:

```text
Criterion selected
    ↓
Failing test/oracle written
    ↓
Failure demonstrated for expected reason
    ↓
Minimal implementation
    ↓
New test passes
    ↓
Relevant regression suite passes
    ↓
Refactor
    ↓
Evidence attached
```

The factory should retain the red-state result as evidence. Merely seeing a new test file in the final commit does not prove TDD happened.

Also consider:

- Mutation testing to detect tests that pass without protecting behavior.
- Property-based testing for broad input spaces.
- Contract testing across service boundaries.
- Characterization tests before modifying legacy behavior.
- Metamorphic tests where exact output is difficult to specify.
- Visual and accessibility checks for UI work.
- Repeated-apply and drift testing for IaC.

“TDD is mandatory by default with explicit exceptions” is safer than making it an absolute ritual. Documentation-only tasks, exploratory spikes, or legacy characterization work may require a different first step, but exceptions should be recorded.

---

# Resumability has three separate requirements

## 1. Workflow resumability

The control plane remembers which semantic steps completed, their outputs, and what remains.

## 2. Environment resumability

The workspace, branch, commit, filesystem changes, running-service state, dependency lockfiles, container image, and tool versions can be restored or reconstructed.

## 3. Cognitive resumability

A provider-independent Resume Capsule tells the next agent:

- What the mission is.
- Which spec and plan versions apply.
- What has been completed.
- Which decisions were made.
- What is currently failing.
- Which artifacts matter.
- What tools and permissions remain.
- What the next intended action is.

Provider session IDs may be stored as an optimization, but they cannot be canonical. A future model or different harness must be able to continue the work.

Checkpoint at semantic boundaries, not after arbitrary token counts. Store the raw stream, but resume from compact, evidence-linked state rather than replaying an entire conversation.

---

# Small work units: yes; deployable microservices everywhere: no

Your RISC/SRP analogy is productive when applied to **work-unit design**.

The correct unit is not “the smallest imaginable action.” It is:

> **The smallest unit with a clear contract, bounded context, independently observable output, and reliable evaluator.**

Excessive decomposition creates:

- Coordination overhead.
- Repeated context loading.
- Integration defects.
- Merge conflicts.
- Lost cross-cutting reasoning.
- More tokens spent describing work than completing it.

Use a hierarchy:

```text
Request
  → Mission
      → Plan
          → Work stream
              → Work unit
                  → Durable step
                      → Tool/model invocation
```

Parallelize work that is disjoint or separated by stable contracts. Keep tightly coupled reasoning together.

Do not let the microtask philosophy force the control plane itself into premature microservices. The product can have strict internal modules while beginning as a simpler deployable system.

---

# Multi-model operation should be selective, not ceremonial

Built-in model plurality is a core requirement. Built-in debate on every task is not.

Useful collaboration patterns include:

- One proposer and one independent critic.
- Two independent plans followed by an adjudicator.
- Cross-model architecture or security review.
- Parallel debugging hypotheses.
- A cheaper worker with a stronger escalation model.
- Independent UI/product review after deterministic checks pass.

To preserve genuine independence, critics should initially review without seeing each other’s conclusions. Otherwise, the second model may anchor on the first.

Omnigent is especially relevant as an architectural reference because it provides a common layer over different agent harnesses, stateful policies, spend and risk controls, sandboxing, shared session history, and live collaboration. Its public site describes it as alpha and Apache 2.0, making it a candidate for later evaluation rather than an assumed foundation. ([Omnigent](https://omnigent.ai/))

---

# The kaizen system must not self-modify production directly

The learning loop should be:

```text
Observe
  → cluster failures and successes
  → form improvement hypothesis
  → create candidate prompt/skill/test/policy/context change
  → replay historical tasks
  → run controlled comparison
  → inspect regressions and security impact
  → approve
  → promote gradually
  → monitor
```

This is where your one-petabyte history becomes strategically valuable.

Examples of useful offline jobs:

- Find repeated reviewer corrections.
- Convert historical bugs into regression tests.
- Identify frequently missing context.
- Compare models by task class.
- Detect prompts or skills with declining performance.
- Find stale knowledge and documentation drift.
- Discover repeated manual chores.
- Analyze whether greater reasoning effort actually improves landed outcomes.
- Generate synthetic edge cases from incident history.
- Detect architectural drift across repositories.

Tessl’s current concept closely resembles part of this loop: it describes continuously scanning PRs, session logs, and tickets, then turning recurring mistakes into context changes, PRs, or automated workflows. This should be treated as product inspiration because it does not satisfy your open-component constraint. ([Tessl](https://tessl.io/agent/))

---

# Current landscape: what to take from each system

- **Symphony:** work-item-based orchestration and always-on execution.
- **Factory.ai:** full lifecycle and feedback-loop framing.
- **Stripe Minions:** unattended, well-scoped changes supported by deterministic rails and strong internal developer tooling. ([Stripe Dev](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents?utm_source=chatgpt.com))
- **Ramp Inspect:** complete reproducible environments and closed-loop verification rather than stopping at code generation. ([Ramp Builders](https://builders.ramp.com/post/why-we-built-our-background-agent?utm_source=chatgpt.com))
- **GitHub Next Ace:** multiplayer planning, shared context, microVM-backed sessions, and live orientation.
- **Agentic Context Engineering:** execution-derived, curated playbooks.
- **Google OKF:** portable knowledge source and interchange.
- **Spec Kit:** agent-independent specification workflow.
- **Omnigent:** model/harness composition plus policy outside prompts.
- **Cognee:** graph/vector/relational memory candidate.
- **Tessl:** repeated-failure-to-improvement loop.
- **Claude Tag:** persistent shared agent identities with scoped channel memory and access boundaries. ([Anthropic](https://www.anthropic.com/news/introducing-claude-tag?utm_source=chatgpt.com))
- **Buzz:** too little public technical information currently exists to use it as an architectural reference; its public page only describes an early-stage product. ([Buzz](https://buzz.xyz/))

The future-proof part of this system is therefore not the intelligence of today’s architect agent. It is the quality of the contracts, evaluation oracles, knowledge, evidence, workflow state, execution environments, adapters, and governance surrounding whatever model is best next year.

---

# Initial disposition of your ideas

**Keep as foundational:** deterministic dispatcher, smart triage, clarification through tickets, specs, TDD, durable resumability, complete provenance, model plug-ins, multi-model review, real-time UI, idempotent IaC, and controlled kaizen.

**Keep but modify:** event-driven architecture, “store everything,” graph/vector RAG, microtasking, multi-model debate, TDD religiosity, and “work until yes.”

**Defer:** building a complete ticket system, selecting a specialized graph database, optimizing for millions of tasks, and implementing every logical boundary as a microservice.

**Reject for the first authority level:** direct unrestricted production changes, raw organizational context in every prompt, LLM-owned queue control, and autonomous promotion of self-generated policies or prompts.

---

# PRD discovery draft

The initial PRD contains the refined product definition, goals, non-goals, principles, entity vocabulary, lifecycle, functional requirements, logical data model, evaluation model, resumability requirements, context strategy, keep/modify/defer decisions, landscape notes, metrics, and interview plan.

[Download the Software Factory PRD v0.1](sandbox:/mnt/data/org-wide-software-factory-prd-v0.1.md)

It is intentionally a **discovery draft**, not a technical architecture or implementation plan.

# Interview round 1: mission and boundaries

Please answer these in order; approximate answers are sufficient at this stage.

1. **Open-source boundary:** Are proprietary paid model APIs from OpenAI, Anthropic, and Google an explicit exception to “every component must be open source or self-built,” with the surrounding control/data plane remaining open and self-hosted?

2. **First production target:** What exact system should the initial factory work on—greenfield or brownfield, number of repositories, main languages/frameworks, and deployment platform?

3. **Initial authority:** Should the first release be allowed to read only, create branches, open PRs, merge low-risk PRs, deploy to development, deploy to staging, or perform controlled production canaries?

4. **Accountability:** Who owns business intent, who can declare a request ready, and who has final authority when the product owner, architect, evaluator, and security role disagree?

5. **Existing environment:** What ticketing, source-control, CI/CD, chat, documentation, identity, secrets, artifact, and observability systems already exist?

6. **Data boundary:** What source code, customer data, credentials, production logs, or regulated information must never leave your infrastructure or enter a proprietary model provider?

7. **First supported work classes:** Which two or three should the POC master first—features, bug fixes, refactors, infrastructure, migrations, incidents, documentation, security remediation, or something else?

8. **Undeniable success:** Ninety days after starting, what observable outcome would convince you that the factory works—for example ten production-quality feature PRs, 50% lower cycle time, unattended overnight fixes, successful crash recovery, or a specific internal product delivered end to end?


---

## 👤 User

1- open source boundary does not apply to frontier model providers. we need to use them to code
2- greenfield, rust with axum and javascript vanilla with web-components and html css (no framework for js or css)
3- fully autonomous to create prod grade canaries
4- RBAC managed by the app. anyone in the team can create a ticket. collaborative effort
5-ticketing = self built laraval app, 
source = gitlab 
ci/cd = gitlab runners and jenkins 
chat=slack , want to self code custom app with ai agent first in mind
docs=md files in monorepo
id=keycloak self hosted
6- customer ID data
7- features
8- end to end feature delivery without any human involvement or minimal baby sitting 
also check tapes.dev for concept


## 🤖 Assistant

> 🔍 **Tool call → `container.exec`**

```unknown
bash -lc ls -l /mnt/data/org-wide-software-factory-prd-v0.1.md && sed -n '1,260p' /mnt/data/org-wide-software-factory-prd-v0.1.md
```

*I’ll update the discovery PRD, evaluate Tapes’ operating model, and focus the next interview on autonomy, safety, unresolved policies, and the first feature-delivery loop.*

> 💭 **Reviewed tapes.dev concept and remaining PRD sections**

> 🔍 **Tool call → `web.run`**

```json
{
  "search_query": [
    {
      "q": "site:tapes.dev software development agents concept tapes.dev"
    },
    {
      "q": "tapes.dev AI software factory agent platform"
    },
    {
      "q": "\"tapes.dev\" coding agents"
    }
  ],
  "response_length": "long"
}
```

> 💭 **Searched 12 websites**

> 💭 **Refining project requirements**
> I’m updating the requirements with the existing ticketing context, target stack, autonomous canary goal, and security concerns. I’m keeping implementation details open while clarifying infrastructure, deployment, data handling, repository structure, and agent behavior.

> 💭 **Refined project requirements**

> 🔍 **Tool call → `container.exec`**

```unknown
bash -lc grep -n '^##\|^###' /mnt/data/org-wide-software-factory-prd-v0.1.md | tail -n 80 && tail -n 260 /mnt/data/org-wide-software-factory-prd-v0.1.md
```

> 💭 **Inspected PRD structure and interview questions**

> 💭 **Evaluating Tapes’ fit**
> I’m assessing Tapes as an observability pattern rather than the whole control plane. Its append-only events and derived views could inform agent telemetry, but broader artifacts, deployments, security, licensing, and customer-data handling still need clarification.

> 💭 **Evaluated Tapes’ fit**

> 💭 **Clarifying scope and authority**
> I’m separating the existing Laravel ticketing system from the new Rust/Axum factory and treating Slack as the initial interface. I’m also defining autonomous canary creation as the highest authority, with policy-based rollback and human intervention by exception.

> 💭 **Clarified scope and authority**

> 💭 **Updating the PRD**
> I’m incorporating confirmed boundaries, implementation preferences, existing integrations, autonomous canary creation, and Tapes as a possible telemetry component. I’ll preserve open decisions around the delivered application, data controls, deployment authority, and external model usage.

> 💭 **Updated the PRD**

> 🔍 **Tool call → `container.exec`**

```unknown
bash -lc sed -n '372,435p' /mnt/data/org-wide-software-factory-prd-v0.1.md && sed -n '620,710p' /mnt/data/org-wide-software-factory-prd-v0.1.md
```

> 💭 **Updated software factory PRD scope and requirements**

> 🔍 **Tool call → `container.exec`**

```unknown
bash -lc cat > /tmp/update_prd.py <<'PY'
from pathlib import Path
import re

src = Path('/mnt/data/org-wide-software-factory-prd-v0.1.md')
out = Path('/mnt/data/org-wide-software-factory-prd-v0.2.md')
text = src.read_text()


def replace(old: str, new: str, count: int = 1):
    global text
    if old not in text:
        raise SystemExit(f'Missing expected text:\n{old[:300]}')
    text = text.replace(old, new, count)

replace('**Version:** 0.1', '**Version:** 0.2')
replace('**Status:** Not approved; intended for brainstorming and interview',
        '**Status:** Discovery draft; interview round 1 incorporated; round 2 pending')

replace(
'''The proposed product is an **open, model-agnostic software factory** that converts approved business intent into evidence-backed software changes through durable, observable, resumable workflows.''',
'''The proposed product is an **open, model-agnostic software factory** that converts policy-eligible business intent into evidence-backed software changes and autonomously deployable production canaries through durable, observable, resumable workflows.''')

replace(
'''The factory should preserve complete provenance for every run; maintain a portable, curated body of organizational knowledge; support multiple model providers and open-source models; enforce specification-driven and test-driven development; expose real-time progress to humans; and continuously improve through controlled analysis of historical traces and outcomes.''',
'''The factory should preserve complete provenance for every run; maintain a portable, curated body of organizational knowledge; support multiple frontier model providers and open-source models; enforce specification-driven and test-driven development; expose real-time progress to humans; and continuously improve through controlled analysis of historical traces and outcomes. Every non-model component of the core factory must be open source or self-built; paid frontier-model APIs are an explicit exception.''')

replace(
'''> **Approved intent in; reproducible, evidence-backed software change out; humans retain governance.**''',
'''> **Policy-governed intent in; reproducible, evidence-backed production canary out; humans intervene by exception.**''')

insert_after = '''> **Policy-governed intent in; reproducible, evidence-backed production canary out; humans intervene by exception.**\n'''
confirmed = r'''

### 1.1 Confirmed discovery decisions from interview round 1

The following decisions are now product constraints rather than open questions:

- **Open-source boundary:** proprietary frontier-model APIs from OpenAI, Anthropic, and Google are permitted. The factory control plane, data plane, orchestration, storage, observability, policy, and user-facing components must otherwise be open source or self-built.
- **Initial construction preference:** greenfield development using Rust with Axum for backend services and vanilla JavaScript Web Components with plain HTML and CSS for the browser interface. No JavaScript or CSS framework is desired. Whether this stack applies only to the factory or also to the first application delivered by it remains to be confirmed.
- **Initial authority:** the target is autonomous delivery through a production-grade canary, including build, merge, deployment, verification, and automatic rollback within policy-defined limits.
- **Human operating model:** any authenticated team member may create a ticket. Collaboration occurs through the work item, and application-managed RBAC determines who may change intent, policy, priority, authority, and production controls.
- **Existing integration environment:** a self-built Laravel ticketing application, GitLab source control, GitLab Runners and Jenkins, Slack, Markdown documentation in a monorepo, and self-hosted Keycloak identity.
- **Chat direction:** Slack is an existing integration surface, but a self-built, agent-first collaboration application is desired later so the factory is not permanently dependent on Slack.
- **Sensitive-data boundary:** “customer ID data” must not be exposed to external frontier-model providers. The exact data classification and whether this means identifiers only or broader customer PII remains unresolved.
- **Initial work class:** product features only. Bugs, incidents, infrastructure, migrations, and other classes are deferred until the feature path is reliable.
- **Prototype success:** end-to-end feature delivery with no human involvement after readiness, or only exceptional intervention when the factory detects a genuine ambiguity, policy conflict, or unsafe condition.

These decisions increase the importance of autonomous clarification, executable acceptance criteria, release safety, provider-boundary enforcement, and evidence-backed rollback.
'''
text = text.replace(insert_after, insert_after + confirmed, 1)

replace(
'''- Any approved source can submit work.''',
'''- Any authenticated team member can submit work through the existing Laravel ticketing system or another approved adapter.''')
replace(
'''- Humans can observe and steer work in real time without micromanaging each session.''',
'''- Humans can observe and steer work in real time, while the normal eligible-feature path requires no per-step supervision.''')
replace(
'''- Production authority is governed by risk policy, not by model confidence.''',
'''- Production authority is governed by deterministic RBAC and risk policy, not by model confidence; eligible features may autonomously reach a bounded production canary.''')

replace(
'''### G-09 — Open control plane

Every non-model component of the factory should be open source or self-built. The meaning of this requirement for proprietary foundation-model APIs remains an explicit interview question.''',
'''### G-09 — Open control and data plane

Every non-model component of the core factory must be open source or self-built. Proprietary frontier-model APIs are explicitly permitted as interchangeable coding/reasoning providers, but no provider may become the canonical store of mission state, evidence, knowledge, or policy.''')

replace(
'''### G-10 — Simple human interface

A requester or operator should be able to submit a task and understand current state, blockers, decisions, costs, artifacts, evidence, and next actions without reading raw logs.''',
'''### G-10 — Simple human interface

A requester or operator should be able to submit a task and understand current state, blockers, decisions, costs, artifacts, evidence, and next actions without reading raw logs.

### G-11 — Autonomous production canaries

For policy-eligible feature work, the factory should progress from a ready specification through merge, deployment, production canary verification, and rollback without human involvement.

### G-12 — Existing-system interoperability

The first useful version must integrate with the existing Laravel ticketing application, GitLab, GitLab Runners, Jenkins, Slack, Markdown documentation, and Keycloak rather than requiring a wholesale platform replacement.

### G-13 — Provider-boundary protection

Customer identity data and other prohibited classes must be prevented from entering external model prompts, tool payloads, traces exposed to providers, or provider-hosted session state.''')

replace(
'''2. Replace every existing ticketing, source-control, chat, documentation, or CI system.''',
'''2. Replace the existing Laravel ticketing application, GitLab, GitLab Runners, Jenkins, or Keycloak during the first prototype.''')
replace(
'''5. Depend on direct pushes to production as proof of autonomy.''',
'''5. Treat unrestricted full-production rollout as equivalent to a bounded production canary; canary scope, verification, and rollback are separate product requirements.''')
replace(
'''10. Force all work, including discovery spikes, into a rigid process where the process costs more than the task.''',
'''10. Force all work, including discovery spikes, into a rigid process where the process costs more than the task.
11. Support every work class in the first prototype; the initial autonomous path is for greenfield product features.
12. Build the planned Slack replacement before the feature-delivery vertical slice proves value.
13. Send prohibited customer identity data to any frontier-model provider.''')

replace(
'''### P-10 — Learning requires promotion gates

The factory may propose improvements autonomously, but improvements become active only after replay, evaluation, comparison, and approval appropriate to their risk.''',
'''### P-10 — Learning requires promotion gates

The factory may propose improvements autonomously, but improvements become active only after replay, evaluation, comparison, and approval appropriate to their risk.

### P-11 — Human intervention by exception

Eligible feature missions should not require routine human approvals after Definition of Ready. When the factory cannot prove safety or correctness, it must stop, ask, or roll back rather than silently guess.

### P-12 — Capture raw facts; derive interpretations

Raw interactions and side effects are appended immutably. Searchable traces, summaries, skills, metrics, and knowledge candidates are deterministic or versioned derivations that can be rebuilt as schemas and interpretations evolve.

### P-13 — Data-boundary enforcement before inference

Sensitive-data classification, redaction, and provider routing occur before a model request is constructed. Prompts are not an acceptable security boundary.''')

replace(
'''| Business requester | Describes the desired outcome, motivation, urgency, and business constraints. |''',
'''| Business requester | Any authenticated team member who creates a ticket and describes the desired outcome, motivation, urgency, and business constraints. |''')
replace(
'''| Product owner | Owns value, scope, user-facing acceptance, and prioritization. |''',
'''| Ticket collaborators | Team members authorized through application RBAC to clarify intent, refine scope, contribute evidence, and resolve questions. The final authority model remains to be defined. |''')
replace(
'''| Platform operator | Operates the factory, policies, models, runners, and capacity. |''',
'''| Factory operator | Operates the factory, policies, model adapters, GitLab/Jenkins execution integrations, capacity, and emergency controls. |''')

replace(
'''| Deployment | Release of a specific change set into an environment. |''',
'''| Deployment | Release of a specific change set into an environment. |
| Production Canary | Bounded production deployment with an explicit exposure limit, observation window, success signals, abort thresholds, and automatic rollback policy. |
| Autonomy Profile | Versioned policy declaring which work classes and risk levels may clarify, plan, merge, deploy, canary, roll back, or promote without human approval. |
| Raw Capture Record | Immutable record of an observed model interaction, tool action, external side effect, or environment event before interpretation or summarization. |''')

replace(
'''A request arrives from an external ticket system, native UI, API, chat integration, production signal, or recurring goal.''',
'''A request initially arrives from the existing self-built Laravel ticketing application. Future adapters may include a native UI, API, Slack, a self-built agent-first chat application, production signals, or recurring goals.''')
replace(
'''A specification or architect agent asks focused questions through the originating interface. The mission cannot enter implementation while blocking ambiguity remains. Answers become versioned inputs, not untracked chat.''',
'''A specification or architect agent asks focused questions as comments in the originating ticket and optionally mirrors notifications to Slack. The mission cannot enter implementation while blocking ambiguity remains. Answers from authorized collaborators become versioned inputs, not untracked chat.''')
replace(
'''Each acceptance criterion is assigned an oracle, pass condition, evidence requirement, severity, and owner. This is the principal Definition-of-Ready gate.''',
'''Each acceptance criterion is assigned an oracle, pass condition, evidence requirement, severity, and owner. For eligible standard features, a deterministic readiness policy may open execution automatically once blocking ambiguity is resolved and all required oracles exist; human approval is not intrinsically required.''')
replace(
'''Authority is risk-based. The initial product may be production-deployed while retaining PR-only or non-production rights. Higher autonomy is earned per work class through measured reliability.''',
'''Authority is risk-based and encoded in an Autonomy Profile. The initial product target is autonomous merge and bounded production-canary deployment for eligible feature work, with strict exposure limits, health gates, automatic rollback, and emergency stop. Full production promotion remains a separate policy decision.''')
replace(
'''The system validates runtime health, acceptance signals, telemetry, and regressions. Failed verification triggers rollback or a new repair mission according to policy.''',
'''The system validates runtime health, acceptance signals, telemetry, and regressions throughout the canary observation window. Failed verification triggers automatic rollback and a targeted repair mission according to policy; passing verification closes the canary stage or requests a separately authorized promotion.''')

replace(
'''- **FR-008:** Represent all lifecycle transitions as durable, versioned facts.''',
'''- **FR-008:** Represent all lifecycle transitions as durable, versioned facts.
- **FR-009:** Integrate identity and authorization with self-hosted Keycloak while preserving the factory’s own auditable RBAC and workload identities.''')
replace(
'''- **FR-015:** Require accountable approval of the clarified intent before high-cost implementation for configured risk classes.''',
'''- **FR-015:** Require accountable approval of the clarified intent only for configured risk classes; eligible standard features may pass readiness automatically through deterministic policy.
- **FR-016:** Post blocking questions, answer status, and readiness transitions back to the Laravel ticket so collaborators can resolve ambiguity without entering a separate operator console.''')
replace(
'''- **FR-078:** Make replay and audit possible without depending on a vendor dashboard.''',
'''- **FR-078:** Make replay and audit possible without depending on a vendor dashboard.
- **FR-079:** Separate append-only raw capture from derived sessions, traces, spans, summaries, search indexes, and skills. Derivations must be versioned and safely rebuildable from retained source records.''')
replace(
'''- **FR-102:** Allow authorized humans to answer questions, edit specs or plans, approve gates, pause, cancel, and steer future steps.''',
'''- **FR-102:** Allow authorized humans to answer questions, edit specs or plans, change policy-controlled gates, pause, cancel, and steer future steps without making routine intervention a requirement for eligible features.''')
replace(
'''- **FR-107:** Preserve links back to external tickets, code reviews, deployments, and incidents.''',
'''- **FR-107:** Preserve links back to the Laravel ticket, GitLab changes, GitLab Runner/Jenkins jobs, deployments, and incidents.
- **FR-108:** Use Keycloak-backed identity and application RBAC to distinguish ticket creation, collaboration, readiness-policy administration, merge authority, deployment authority, emergency stop, and audit access.
- **FR-109:** Treat Slack as an integration surface rather than a canonical state store, allowing later replacement by a self-built agent-first collaboration application.''')
replace(
'''- **FR-127:** Make policy decisions deterministic, testable, versioned, and auditable.''',
'''- **FR-127:** Make policy decisions deterministic, testable, versioned, and auditable.
- **FR-128:** Prevent prohibited customer identity data from entering external model requests, provider-side session continuation, externally hosted embeddings, or provider-visible tool payloads.
- **FR-129:** Record the data-classification decision and transformation manifest for every model request so audits can prove what was included, excluded, tokenized, redacted, or replaced with synthetic references.

### 10.14 Autonomous production-canary delivery

- **FR-130:** For an eligible feature mission whose required gates pass, autonomously merge or create the release change set according to GitLab policy and initiate a production canary without per-ticket human approval.
- **FR-131:** Define canary exposure by an explicit, machine-readable blast-radius budget such as tenant allow-list, request percentage, instance subset, region, duration, and maximum affected customer count.
- **FR-132:** Require pre-deployment baselines, success metrics, abort thresholds, minimum observation windows, and rollback procedures before canary initiation.
- **FR-133:** Continuously evaluate functional, reliability, performance, security, and business signals during the canary and attach evidence to the originating acceptance criteria.
- **FR-134:** Automatically halt or roll back when any blocking threshold is crossed, telemetry becomes unavailable, required evidence is missing, or the control plane loses confidence in current deployment state.
- **FR-135:** Make deploy, observe, halt, rollback, and retry actions idempotent or compensatable and safe across worker or control-plane restarts.
- **FR-136:** Prohibit an implementation agent or LLM judge from expanding canary exposure, overriding an abort threshold, or disabling a required monitor.
- **FR-137:** Keep full-production promotion separate from canary success until an explicit promotion policy is defined and approved.
- **FR-138:** Support emergency global pause and rollback through authenticated operator controls independent of all model providers.
- **FR-139:** Produce a complete release evidence bundle linking ticket, specification, criteria, plan, commits, CI jobs, artifacts, deployment manifest, canary signals, decisions, and rollback outcome.''')

replace(
'''The requirement to “store everything” should be implemented as several cooperating logical stores rather than one database.''',
'''The requirement to “store everything” should be implemented as several cooperating logical stores rather than one database. A cross-cutting invariant is **capture first, derive later**: immutable boundary observations are retained independently from the projections, summaries, embeddings, skills, and analytics built from them.''')
replace(
'''Provides fast timeline, trace, log, full-text, and operational queries. OpenTelemetry-compatible traces are a useful interoperability layer; long-term raw retention may live in the artifact/lakehouse planes.''',
'''Provides fast timeline, trace, log, full-text, and operational queries. OpenTelemetry-compatible traces are a useful interoperability layer; long-term raw retention may live in the artifact/lakehouse planes. Tapes.dev is a strong candidate or reference implementation for the model-interaction portion of this plane because it separates append-only capture from deterministic session/trace/span derivation, but it must not become the canonical workflow engine or sole evidence store.''')
replace(
'''A graph index may be useful, but the underlying IDs and relationships must remain exportable and reconstructable.''',
'''A graph index may be useful, but the underlying IDs and relationships must remain exportable and reconstructable. The factory should also evaluate Agent Trace-compatible attribution records that link repository revisions and changed line ranges to the conversations and models that produced them.''')

replace(
'''| Open source or self-built only | **Keep; clarify** | Apply to the control plane and infrastructure. Clarify whether proprietary paid model APIs are an intentional exception. |''',
'''| Open source or self-built only | **Keep; resolved** | All core non-model components must be open source or self-built. Proprietary OpenAI, Anthropic, and Google frontier-model APIs are the explicit exception. |''')
replace(
'''| Build a new ticket system | **Defer** | Build only the factory-specific UI and canonical work model first; integrate existing open trackers through adapters. |''',
'''| Build a new ticket system | **Drop for the prototype** | Integrate the existing self-built Laravel ticket application and preserve a canonical factory Work Item model. Revisit replacement only if agent-first collaboration requirements cannot be met through integration. |''')
replace(
'''| Direct autonomous production from day one | **Drop as initial authority** | Deploy the factory in production on day one, but begin with bounded rights such as branch/PR creation and non-production deployment. Expand authority by measured class. |''',
'''| Direct autonomous production from day one | **Keep, constrain to canaries** | Eligible feature work should autonomously reach a production-grade canary. Blast radius, observation, abort thresholds, automatic rollback, and emergency stop are deterministic. Unrestricted full rollout remains separate. |''')
replace(
'''| Million-way execution from day one | **Defer implementation** | Preserve horizontal and partitionable semantics, but validate correctness and recovery at smaller scale first. |''',
'''| Million-way execution from day one | **Defer implementation** | Preserve horizontal and partitionable semantics, but validate correctness and recovery at smaller scale first. |
| Tapes.dev / transparent agent telemetry | **Keep as candidate and pattern** | Adopt append-only capture, pure/idempotent derivation, content addressing, searchable session traces, and trace-derived skills. Do not use it as mission orchestration, policy, or canonical knowledge. |
| Agent Trace code attribution | **Keep as interoperability candidate** | Link repository revisions and line ranges to contributing conversations/models where useful; extend it with factory-specific lineage rather than treating it as complete provenance. |
| Slack replacement | **Defer** | Integrate Slack initially, keep it non-canonical, and build the agent-first collaboration application after the delivery vertical slice is proven. |''')

marker = '''### Buzz\n\nPublic information is currently too limited to derive concrete architecture. Treat it as an emerging collaborative-agent product to monitor, not a design dependency.\n'''
tapes_section = r'''### Tapes.dev and Agent Trace

Useful lesson: intercept model traffic or accept sidecar ingestion into an append-only raw-turn log, then use a pure, idempotent deriver to produce query-oriented sessions, traces, spans, links, embeddings, and aggregates. Content-addressed deduplication and deterministic derived identifiers make reprocessing and schema evolution safer. Tapes also demonstrates semantic search, MCP access, and generation of reusable agent skills from historical sessions.

The factory should treat Tapes as a candidate implementation or pattern for **model-interaction telemetry**, not as the mission workflow engine, event backbone, artifact lake, release controller, or curated knowledge store. The broader factory must additionally capture source-control operations, shell/tool side effects, CI execution, environment state, deployments, runtime evidence, and policy decisions. Tapes is AGPL-3.0, which is compatible with the open-source requirement but requires a deliberate license and modification/deployment review.

Agent Trace adds another useful interoperability idea: attach repository revision and line-range attribution to the conversations and models that contributed code. This is valuable for provenance and debugging, but it is narrower than the factory’s complete lineage model.

'''
if marker not in text:
    raise SystemExit('Buzz marker missing')
text = text.replace(marker, tapes_section + marker, 1)

replace(
'''- independent review passes;
- reproducible evidence bundle exists;
- post-deployment verification passes before final closure.''',
'''- independent review passes;
- reproducible evidence bundle exists;
- production-canary blast radius, baseline, success signals, abort thresholds, observation window, and rollback are defined;
- autonomous canary deployment is idempotent and customer-data boundary checks pass;
- post-deployment verification passes before final closure or a deterministic rollback completes.''')

replace(
'''- percentage of work completed with no intervention after Definition of Ready;
- human minutes per landed change;''',
'''- percentage of feature missions completed through verified production canary with no intervention after Definition of Ready;
- human minutes per verified production canary;''')

start = text.index('## 21. Proposed prototype boundary — hypothesis only')
end = text.index('\n---\n\n## 22. Open product decisions', start)
new_21 = r'''## 21. Proposed prototype boundary — revised hypothesis

This boundary incorporates interview round 1 but is not yet approved:

- one organization and one greenfield feature-delivery target;
- preferred implementation stack of Rust/Axum plus vanilla JavaScript Web Components and plain HTML/CSS, pending confirmation of whether this applies to the factory, target application, or both;
- existing Laravel ticketing application as the initial intake and collaboration surface;
- GitLab as source-control and merge surface;
- GitLab Runners and Jenkins as existing execution systems to integrate rather than immediately replace;
- Slack notifications/integration, with no canonical state stored only in Slack;
- Markdown documentation and knowledge sources in a monorepo;
- Keycloak-backed human identity plus separate workload identities;
- product-feature work only;
- OpenAI/Codex, Claude, Gemini, and at least one open-source model adapter;
- deterministic dispatcher and durable mission state;
- clarification, specification, criteria, plan, work-unit DAG, TDD execution, evaluation, merge, production-canary deployment, automated verification, and rollback;
- no routine human approval after an eligible feature reaches Definition of Ready;
- complete model/tool/CI/deployment trace and artifact capture for the selected target;
- a capture/derive telemetry pattern, with Tapes.dev evaluated as a candidate for model-interaction telemetry;
- provider-boundary enforcement preventing prohibited customer identity data from leaving controlled infrastructure;
- a small curated knowledge bundle and derived retrieval indexes;
- real-time mission UI and ticket synchronization;
- no autonomous unrestricted full-production promotion until a separate promotion policy is defined;
- no autonomous modification of active production policies.

The POC is successful only when it repeatedly takes an eligible feature from a collaborative ticket to a verified production canary or safe automatic rollback without human babysitting.
'''
text = text[:start] + new_21 + text[end:]

start = text.index('## 22. Open product decisions')
end = text.index('\n---\n\n## 23. Interview plan', start)
new_22 = r'''## 22. Open product decisions after interview round 1

1. What is the actual greenfield product or service whose features the factory will deliver? Is the factory expected to build itself first, build a separate reference application, or both?
2. Does the Rust/Axum plus Web Components constraint apply to the factory control plane, the first target application, or every application the factory may touch?
3. What production platform will host the target: Kubernetes, Nomad, bare metal, VMs, a public cloud, or another environment?
4. What precisely counts as “customer ID data”: opaque account identifiers only, names/email/phone/address, authentication data, behavioral data, support content, or all customer-linked information?
5. May customer-derived data be transformed locally into synthetic fixtures, aggregates, hashes, or opaque references before a frontier model sees it?
6. Who or what may declare a ticket Definition of Ready? Can policy do so automatically after collaborators answer all blocking questions, or must a named role approve the intent?
7. When collaborators disagree, which RBAC role or policy has final authority over business intent, architecture, acceptance criteria, security, and release?
8. What exactly is a production canary in your environment: traffic percentage, tenant allow-list, instance pool, region, duration, and maximum blast radius?
9. Which signals prove canary success, and which signals force immediate rollback? Is full production promotion in scope or deliberately excluded from the POC?
10. What GitLab merge strategy and branch protections must the autonomous path obey, and which system—GitLab Runner or Jenkins—is authoritative for each CI/CD stage?
11. Are Slack and any paid/self-hosted GitLab capabilities acceptable as temporary external integrations despite the open-core/open-source principle, provided the factory does not depend on proprietary control-plane state?
12. What availability, latency, security, performance, audit, and recovery objectives must every generated feature satisfy from the first canary?
13. May the factory modify its own repository and deploy its own canaries, or is recursive self-modification initially prohibited?
14. What numeric threshold defines “minimal babysitting”: zero intervention for 80%, 95%, or another percentage of eligible feature missions?
15. How many concurrent feature missions and canaries should the first version support, and what conflict policy applies when two tickets touch the same component?
'''
text = text[:start] + new_22 + text[end:]

start = text.index('## 23. Interview plan')
end = text.index('\n---\n\n## 24. Referenced inspirations', start)
new_23 = r'''## 23. Interview plan

### Round 1 — Mission and boundaries — completed

Confirmed the open-source exception for frontier models, greenfield stack preference, autonomous canary ambition, RBAC-based collaboration, existing integration environment, sensitive-data boundary, feature-only initial class, and no-babysitting success criterion.

### Round 2 — Target product, authority, and canary contract — current

Clarify the greenfield target, whether the factory dogfoods itself, Definition-of-Ready authority, disagreement resolution, production platform, exact canary scope, success/rollback signals, GitLab/Jenkins responsibilities, and the meaning of customer identity data.

### Round 3 — Correctness

Clarify specification depth, test philosophy, acceptance oracle types, non-functional requirements, risk profiles, and Definition-of-Done profiles for the selected feature domain.

### Round 4 — Knowledge and learning

Clarify authoritative sources, knowledge ownership, retention, privacy, curation, organizational context, trace-to-skill generation, and kaizen promotion rules.

### Round 5 — Scale and experience

Clarify concurrency, latency, UI, notifications, collaboration, cost expectations, availability, operational ownership, and the transition from canary to broader rollout.

After these decisions, this PRD can be promoted from discovery draft to an approved product contract. Only then should a separate technical architecture and phased implementation plan be created.
'''
text = text[:start] + new_23 + text[end:]

replace(
'''- Temporal durable workflow execution — https://docs.temporal.io/workflow-execution''',
'''- Temporal durable workflow execution — https://docs.temporal.io/workflow-execution
- Tapes.dev — https://tapes.dev/
- Tapes architecture — https://tapes.dev/architecture/
- Tapes source repository — https://github.com/papercomputeco/tapes
- Agent Trace specification — https://agent-trace.dev/''')

out.write_text(text)
print(out)
print(f'bytes={out.stat().st_size}')
PY
python /tmp/update_prd.py

```

*Tapes fits as the provenance substrate, not the workflow authority. The key open policies are customer-data isolation and autonomous canary promotion, abort, and rollback.*

> 💭 **Updated and verified PRD structure, terminology, and readiness wording**

*Worked for 7m 47s*

# What your answers now lock in

The factory’s first product contract is substantially clearer:

| Area | Refined decision |
|---|---|
| Component policy | The control plane, data plane, runners, gateways, UI, and infrastructure must be open source or self-built. Proprietary frontier-model APIs are explicitly allowed. |
| Initial workload | Greenfield product development, initially limited to **features**. |
| Application stack | Rust with Axum; vanilla JavaScript Web Components; plain HTML and CSS; no JavaScript or CSS framework. |
| Existing systems | Laravel ticketing application, GitLab, GitLab Runners, Jenkins, Slack, Markdown documentation in the monorepo, and Keycloak. |
| Governance | Any authenticated team member can create a ticket. Collaboration and authority are controlled by application-managed RBAC. |
| Initial autonomy | The factory should autonomously deliver a verified change through a **real production canary**, including deployment, observation, and rollback. |
| Data boundary | Customer-identifying data must not be sent to proprietary frontier-model providers. |
| Success condition | A feature proceeds end to end with no human activity after readiness, except possibly a narrowly defined blocking clarification. |

The clearest operating boundary is therefore:

```text
Collaborative readiness zone
────────────────────────────
Request
  → ambiguity detection
  → clarification
  → specification
  → acceptance criteria
  → evaluation design
  → READY

Autonomous delivery zone
────────────────────────
Architecture
  → plan
  → TDD implementation
  → independent evaluation
  → GitLab merge
  → release artifact
  → production canary
  → live verification
  → rollback or success
  → knowledge update
```

This makes **Definition of Ready** arguably more important than code review. Once a mission is marked ready, the factory should possess everything necessary to operate without asking a human to supervise implementation.

## One important interpretation

I interpreted “create prod-grade canaries” as:

> The factory may build, merge, deploy, observe, and automatically roll back an actual bounded production canary—not merely generate deployment configuration.

Whether it may automatically promote a healthy canary to 100% production remains undecided. For the initial PRD, I stopped autonomous authority at a successfully verified canary.

# How Tapes fits

Tapes is highly relevant, but it solves one bounded part of the factory rather than being the factory itself.

Its strongest architectural idea is the separation of:

```text
Immutable raw capture
        ↓
Deterministic, idempotent derivation
        ↓
Sessions → traces → spans → search projections
```

Tapes can proxy or ingest model traffic, append the completed native requests and responses to an immutable `raw_turns` log, and deterministically derive queryable sessions, traces, spans, span links, usage, and embeddings. Its documented deriver is intended to be safely re-runnable after schema or parser changes. ([tapes](https://tapes.dev/architecture))

That is exactly the pattern we should adopt for the factory’s model-observability plane:

1. Preserve the original event or interaction.
2. Never make a searchable projection the only copy.
3. Derive normalized representations through versioned projection jobs.
4. Allow all historical projections to be regenerated.
5. Treat summaries, embeddings, skills, and analytics as disposable derived products.

Tapes also exposes semantic search over previous interactions through PostgreSQL and `pgvector`, supports local MCP access, and can generate reusable agent skills from selected session history. That aligns with episodic memory and the future kaizen loop. Generated skills must enter our quarantine-and-evaluation process rather than being activated automatically. ([tapes](https://tapes.dev/agents/))

## Where I would place it

Conceptually:

```text
Agent or coding harness
        ↓
Factory model gateway
  - workload identity
  - model routing
  - budget
  - egress policy
  - customer-data detection
  - redaction/tokenization
        ↓
Tapes-like provider-edge capture
        ↓
OpenAI / Anthropic / Gemini / local model
```

The factory model gateway must come first logically because the factory—not the telemetry collector—must decide whether content is permitted to leave the organization.

There may actually be two records:

```text
Restricted internal request
  └─ stored only in an encrypted restricted vault, if policy permits

Sanitized provider request
  └─ exact request that crossed the provider boundary
```

The transformation between them must itself be recorded as a policy decision, including what was removed or tokenized, without leaking the removed value into the normal searchable trace.

## Where Tapes is not enough

Based on its documented scope, Tapes is a telemetry system composed of a proxy or ingest endpoint, deriver, API, CLI, and trace/search interface. It is not the durable owner of a feature mission, deployment transaction, workspace checkpoint, acceptance-criterion state, release gate, or rollback operation. That distinction is an architectural inference from the components it documents. ([tapes](https://tapes.dev/architecture))

It also currently uses PostgreSQL for the raw log, derived traces, and vectors. That can be useful for an initial operational projection, but it should not be the only petabyte-scale archive. Long-term raw payloads should be exportable into the immutable artifact and lakehouse planes, with PostgreSQL retaining operational indexes and selected projections. ([tapes](https://tapes.dev/reference))

Other adoption qualifications:

- The repository is AGPL-3.0, so license compatibility should be reviewed before embedding or modifying it as part of a networked factory service. ([GitHub](https://github.com/papercomputeco/tapes))
- Its official provider reference explicitly shows parsers for OpenAI, Anthropic, and Ollama. Although the documentation describes the architecture as provider-flexible, Gemini compatibility should be verified in a dedicated integration experiment rather than assumed. ([tapes](https://tapes.dev/reference))
- Tapes captures model-boundary activity. Our factory must additionally capture deterministic workflow transitions, tool side effects, source changes, workspace snapshots, tests, CI, deployment evidence, production signals, and governance decisions.
- Tapes search is episodic memory. It must not be confused with authoritative organizational knowledge.
- The proposed Agent Trace format may complement it by preserving vendor-neutral AI contribution attribution down to files and lines in source control. ([GitHub](https://github.com/cursor/agent-trace))

My disposition is therefore:

> **Adopt the Tapes capture-and-derive pattern as a core requirement. Evaluate the existing Tapes project as a model-edge collector, but do not make it the mission system of record, security gateway, or sole historical store.**

# Consequences of your existing systems

## Laravel ticketing

Do not rebuild the ticketing product first.

The Laravel application should remain the initial **system of engagement**:

- Ticket creation.
- Human comments.
- Agent clarification questions.
- Authoritative answers.
- Links to live factory missions.
- High-level result and status.

The factory should maintain its own canonical Work Item and Mission state. A Laravel ticket state such as “in progress” is not rich enough to represent hundreds of durable steps, evaluation results, retries, checkpoints, and canary activity.

## GitLab

GitLab should own:

- Repository and commit identity.
- Branches and merge requests.
- Protected branches.
- Code-review artifacts.
- Release commit references.

The factory owns the reason a change exists, its specification, agent execution, acceptance evidence, and release decision.

## GitLab Runners and Jenkins

Having both creates an unresolved source-of-truth issue. We need to decide whether:

- GitLab is canonical and Jenkins provides specialized jobs.
- Jenkins is canonical and GitLab only launches it.
- Different job classes are assigned to each.
- Both must independently agree for selected high-risk gates.

We should not allow two systems to produce contradictory final states without an explicit adjudication policy.

## Slack and the custom application

Slack should initially be an adapter for:

- Notifications.
- Questions.
- Answers.
- Mentions.
- Emergency operations.

The custom interface should not begin as a general Slack replacement. It should be a **mission-centric collaboration environment** optimized for agents:

- One live mission timeline.
- Specification and acceptance criteria.
- Agent questions and stakeholder answers.
- Work-unit dependency graph.
- Active agents and current actions.
- Test and evaluation evidence.
- Canary state.
- Replay and raw trace access.
- Pause, cancel, and rollback controls.

That focused application can later evolve into the broader AI-first communication product you envision.

## Keycloak and RBAC

“Collaborative” cannot mean “authority is ambiguous.”

Any team member may create a request, but the system still needs deterministic answers to:

- Who may answer a domain question authoritatively?
- Who may modify an approved specification?
- Who may change a production policy?
- Who may view restricted traces?
- Who may stop or rollback a mission?
- Whose answer wins when collaborators disagree?

The clean model is capability-based RBAC combined with mission-specific ownership and domain mappings—not one global “admin versus user” distinction.

# The new critical product requirement: the model gateway

Because frontier APIs are allowed but customer-identifying data is not, a governed model gateway becomes mandatory.

At the requirements level, it must:

- Be the only permitted outbound route to proprietary models.
- Authenticate every mission and invocation.
- Apply provider and model policy.
- Inspect context packs and tool outputs for restricted data.
- Reject, redact, tokenize, or redirect unsafe requests.
- Route restricted work to deterministic tools or approved local models.
- Preserve the exact sanitized request sent externally.
- Record model, parameters, effort, tokens, cost, latency, and response.
- Prevent agents from obtaining raw provider API keys.
- Support immediate provider or model disablement.

This is not merely an observability proxy. It is the enforcement boundary between organizational data and model providers.

# Production canary changes the evaluation model

For an autonomous production canary, acceptance criteria need three layers.

### Pre-implementation criteria

These define the expected business behavior and architecture:

```text
Given an authenticated user,
when the user performs X,
the system produces Y,
subject to constraints Z.
```

### Pre-deployment criteria

These establish that the candidate is safe to release:

```text
Compilation, tests, mutation score, security checks,
migration checks, reproducible build, provenance,
rollback package, and canary policy all pass.
```

### Live canary criteria

These determine whether the implementation works in production:

```text
Functional probe passes.
Error rate remains below threshold.
Latency remains inside its bound.
No prohibited log or security event occurs.
Required business event is observed.
Rollback remains available.
```

A feature is not fully done merely because CI is green. It is done only after its canary evidence is collected and retained.

# PRD update

I incorporated your answers and the Tapes assessment into version 0.2. The revision includes:

- The frontier-model exception.
- The greenfield Rust/Axum and Web Components boundary.
- Existing integrations.
- Keycloak-backed application RBAC.
- Autonomous production-canary requirements.
- Automatic verification and rollback.
- Customer-identifying-data controls.
- The model-boundary raw-capture and deterministic-derivation pattern.
- Tapes and Agent Trace landscape notes.
- A refined prototype boundary.
- The remaining decisions for the next interview round.

[Download the updated Software Factory PRD v0.2](sandbox:/mnt/data/org-wide-software-factory-prd-v0.2.md)

# Interview round 2: autonomy and governance

Please answer these in order.

1. **Stack boundary:** Is Rust/Axum plus vanilla Web Components the required stack for the factory itself, the first product the factory will build, or both?

2. **Deployment substrate:** Where will the production canary run—Kubernetes, Nomad, virtual machines, bare metal, serverless infrastructure, or something else?

3. **Canary authority:** Did I interpret your goal correctly that the factory may deploy and roll back a real production canary? After a successful observation window, may it also promote the canary automatically to 100%, or must it stop there?

4. **Initial risk envelope:** Which feature areas should be prohibited from autonomous canaries initially? Consider authentication, authorization, billing, database-schema changes, destructive operations, infrastructure, secrets, and customer-data processing.

5. **Collaborative authority:** When two team members give contradictory answers on a ticket, who or what determines the authoritative answer—request creator, assigned owner, domain owner, majority, RBAC priority, repository ownership file, or an adjudication role?

6. **Customer data:** By “customer ID data,” do you mean only direct identifiers such as names and account IDs, or all data that can identify or be linked to a customer, including pseudonymous IDs, request bodies, logs, screenshots, support messages, database samples, and embeddings?

7. **Restricted trace retention:** May restricted raw data be retained internally in a separately encrypted, tightly controlled trace vault, or must it be redacted/tokenized before the factory stores any trace at all? May locally hosted models process it?

8. **CI authority:** What are the intended roles of GitLab Runners and Jenkins? Which one determines the final pass/fail result when their results conflict?

9. **Collaboration surfaces:** Should the Laravel ticket application remain the permanent human request system, with the new factory UI handling execution detail, or do you ultimately intend the new application to replace Laravel ticketing as well as Slack?

10. **Minimal babysitting:** Which outcome should become the formal target: zero intervention after Definition of Ready; clarification-only intervention; fewer than a stated number of interventions per feature; or a maximum number of human minutes per completed feature?

