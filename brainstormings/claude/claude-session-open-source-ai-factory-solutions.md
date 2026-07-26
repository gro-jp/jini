# Open source AI factory solutions for production code — Claude session transcript

**Source:** https://claude.ai/share/7147da9f-6fe4-4248-91a1-24886afcc1d7  
**Shared by:** bodla · **Snapshot:** 2026-07-26 15:14 UTC · **Messages:** 3 user / 3 assistant

> Full dump of the shared claude.ai session, captured 2026-07-27 from the share-page API (`/api/chat_snapshots/…?rendering_mode=messages&render_all_tools=true`). All content blocks are preserved in original order: user and assistant text verbatim, tool calls with their JSON inputs, and tool results collapsed in `<details>` blocks. Web-search results in share data carry title/URL only (no page text). The share mechanism strips the inputs of `web_fetch`, `view`, and `str_replace` calls (and their outputs); those are marked *(tool input not included in claude.ai share data)*.

---

## 👤 User  *(11:37 UTC)*

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

---

## 🤖 Assistant  *(11:41 UTC)*

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "fabro.sh AI coding factory"
}
```

<details>
<summary>🧰 Result ← `web_search` (9 items)</summary>

- [Fabro · GitHub](https://github.com/fabro-sh) — github.com
- [Bryan Helmkamp on X: "Today I'm thrilled to open source what I've been working on... Meet Fabro (https://t.co/9iJbhJbMiw), the dark software factory for small teams of expert engineers. Fabro gets you out of the REPL (read-eval-prompt-loop) by layering deterministic workflow graphs over agent" / X](https://x.com/brynary/status/2033901199603241012) — x.com
- [GitHub - fabro-sh/fabro: ⚒️ The open source dark software factory for expert engineers.](https://github.com/fabro-sh/fabro) — github.com
- [Why Fabro? - Fabro](https://docs.fabro.sh/getting-started/why-fabro) — fabro.sh
- [fabro/README.md at main · fabro-sh/fabro](https://github.com/fabro-sh/fabro/blob/main/README.md) — github.com
- [Open Sourced Fabro: Deterministic AI Coding Agent ...](https://www.linkedin.com/posts/bhelmkamp_fabro-the-dark-software-factory-activity-7439659294515507200-Blwt) — linkedin.com
- [Fabro — The Dark Software Factory](https://fabro.sh/) — fabro.sh
- [Fabro Workflow Factory | Claude Code Skills](https://claudemarketplaces.com/skills/aradotso/trending-skills/fabro-workflow-factory) — claudemarketplaces.com
- [Blog — Fabro](https://fabro.sh/blog) — fabro.sh

</details>

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "gethuman.sh"
}
```

<details>
<summary>🧰 Result ← `web_search` (7 items)</summary>

- [GetHuman Customer Service Phone Number 1-617-651-0250, Email, Help Center](https://gethuman.pissedconsumer.com/customer-service.html) — pissedconsumer.com
- [GetHuman - Apps on Google Play](https://play.google.com/store/apps/details?id=com.gethuman.android&hl=en_US) — google.com
- [GetHuman (@gethumancom) on X](https://x.com/gethumancom?lang=en) — x.com
- [GetHuman - YouTube](https://www.youtube.com/channel/UCYqWKL06KKPonY_UiY0UFpw) — youtube.com
- [human - The AI dev rig for AI coding agents](https://gethuman.sh/) — gethuman.sh
- [SH](https://en.wikipedia.org/wiki/SH) — wikipedia.org
- [MakeHuman](https://en.wikipedia.org/wiki/MakeHuman) — wikipedia.org

</details>

> 🔧 **Tool call → `web_fetch`**

> *(tool input not included in claude.ai share data)*

> 🧰 Result ← `web_fetch` (0 items) — *empty*

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "coleam00 archon github 2026"
}
```

<details>
<summary>🧰 Result ← `web_search` (10 items)</summary>

- [coleam00 (Cole Medin) / Repositories · GitHub](https://github.com/coleam00?tab=repositories) — github.com
- [Issues · coleam00/Archon](https://github.com/coleam00/Archon/issues) — github.com
- [Pull requests · coleam00/Archon](https://github.com/coleam00/Archon/pulls) — github.com
- [Open source Archon: migrate new codebase to coleam00/Archon · Issue #952 · coleam00/Archon](https://github.com/coleam00/Archon/issues/952) — github.com
- [coleam00/Archon · Discussions](https://github.com/coleam00/Archon/discussions) — github.com
- [Archon: Complete Rewrite - AI Workflow Engine for Coding Agents · Issue #957 · coleam00/Archon](https://github.com/coleam00/Archon/issues/957) — github.com
- [coleam00 (Cole Medin) · GitHub](https://github.com/coleam00) — github.com
- [GitHub - coleam00/Archon: The first open-source harness builder for AI coding. Make AI coding deterministic and repeatable. · GitHub](https://github.com/coleam00/Archon) — github.com
- [Releases · coleam00/Archon](https://github.com/coleam00/Archon/releases) — github.com
- [https://raw.githubusercontent.com/coleam00/Archon/...](https://raw.githubusercontent.com/coleam00/Archon/main/README.md) — githubusercontent.com

</details>

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "swamp-club swamp github agent orchestration"
}
```

<details>
<summary>🧰 Result ← `web_search` (7 items)</summary>

- [Swamp Club · GitHub](https://github.com/swamp-club) — github.com
- [GitHub - swamp-club/swamp: Stinemates, Watson, Adam, Mahir, Paul · GitHub](https://github.com/systeminit/swamp) — github.com
- [Native OpenTelemetry tracing for swamp CLI internals · Issue #677 · swamp-club/swamp](https://github.com/swamp-club/swamp/issues/677) — github.com
- [Swamp Club — Deterministic automation for AI agents](https://systeminit.com/) — systeminit.com
- [Swamp Club — Deterministic automation for AI agents](https://swamp-club.com/) — swamp-club.com
- [Manual - Swamp Club](https://swamp-club.com/manual) — swamp-club.com
- [The Lifecycle of a Swamp Issue](https://stack72.dev/the-lifecycle-of-a-swamp-issue/) — stack72.dev

</details>

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "owainlewis factory github AI agents"
}
```

<details>
<summary>🧰 Result ← `web_search` (7 items)</summary>

- [GitHub - owainlewis/owainlewis: A static document to store profile information for Github. · GitHub](https://github.com/owainlewis/owainlewis) — github.com
- [owainlewis (Owain Lewis) / Repositories · GitHub](https://github.com/owainlewis?tab=repositories&type=) — github.com
- [GitHub - owainlewis/awesome-artificial-intelligence: A curated list of Artificial Intelligence (AI) courses, books, video lectures and papers. · GitHub](https://github.com/owainlewis/awesome-artificial-intelligence) — github.com
- [owainlewis (Owain Lewis) · GitHub](https://github.com/owainlewis) — github.com
- [GitHub - owainlewis/agent-skills: My personal agent skills · GitHub](https://github.com/owainlewis/agent-skills) — github.com
- [GitHub - owainlewis/agent-worker: Secure and scalable way to delegate work to AI agents from anywhere. Build a team of agents that work for you. · GitHub](https://github.com/owainlewis/agent-worker) — github.com
- [agent-worker/src at main · owainlewis/agent-worker](https://github.com/owainlewis/agent-worker/tree/main/src) — github.com

</details>

> 🔧 **Tool call → `web_fetch`**

> *(tool input not included in claude.ai share data)*

> 🧰 Result ← `web_fetch` (0 items) — *empty*

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "orchestrate Claude Code Codex CLI Gemini CLI open source multi-agent kanban worktrees"
}
```

<details>
<summary>🧰 Result ← `web_search` (6 items)</summary>

- [GitHub - andyrewlee/awesome-agent-orchestrators: List of agent orchestrators · GitHub](https://github.com/andyrewlee/awesome-agent-orchestrators) — github.com
- [GitHub - bradAGI/awesome-cli-coding-agents: Curated directory of terminal-native AI coding agents and the harnesses that orchestrate them. Covers open-source tools (Pi, OpenCode, Aider, Goose), platform agents (Claude Code, Codex, Gemini CLI), parallel runners, autonomous loops, and agent infrastructure. · GitHub](https://github.com/bradAGI/awesome-cli-coding-agents) — github.com
- [AddyOsmani.com - The Code Agent Orchestra - what makes multi-agent coding work](https://addyosmani.com/blog/code-agent-orchestra/) — addyosmani.com
- [Agent Kanban — Orchestrate AI Coding Agents on a Kanban Board](https://agent-kanban.dev/) — agent-kanban.dev
- [9 Open-Source Agent Orchestrators for AI Coding (2026) | Augment Code](https://www.augmentcode.com/tools/open-source-agent-orchestrators) — augmentcode.com
- [Agentmaxxing: Parallel Multi-CLI Orchestration with Codex CLI, Claude Code and Gemini CLI | Codex Knowledge Base](https://codex.danielvaughan.com/2026/04/11/agentmaxxing-parallel-multi-cli-orchestration/) — danielvaughan.com

</details>

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "fabro agents claude code codex gemini subscription auth providers"
}
```

<details>
<summary>🧰 Result ← `web_search` (9 items)</summary>

- [External Agents | External Agents - Zed](https://zed.dev/docs/ai/external-agents) — zed.dev
- [5 Claude Code Alternatives in 2026](https://www.builder.io/blog/claude-code-alternatives) — builder.io
- [Developer's Guide to Claude Code vs. Gemini Code Assist](https://www.descope.com/blog/post/claude-code-vs-gemini-code-assist) — descope.com
- [Claude Code Orchestrator Setup Guide - Multi-agent workflow with Codex (writer), Gemini (auditor), and Nanobanana (image generation) · GitHub](https://gist.github.com/bjornmage/ddd6dc7f4d5e074af1db44964d377427) — github.com
- [VS Code ACP Client extension: conect to Claude, Gemini, Codex, OpenCode, Qwen Code and so on - DEV Community](https://dev.to/formulahendry/vs-code-acp-client-extension-conect-to-claude-gemini-codex-opencode-qwen-code-and-so-on-3552) — dev.to
- [CLI Coding Agents Comparison - Claude Code, Codex CLI, Gemini CLI, and More | hidekazu-konishi.com](https://hidekazu-konishi.com/entry/cli_coding_agents_comparison.html) — hidekazu-konishi.com
- [github.com](https://github.com/QuiteBitter/CLIProxyAPI) — github.com
- [github.com](https://github.com/gd4Ark/CLIProxyAPI) — github.com
- [github.com](https://github.com/hkfires/CLIProxyAPI) — github.com

</details>

> 🔧 **Tool call → `web_fetch`**

> *(tool input not included in claude.ai share data)*

> 🧰 Result ← `web_fetch` (0 items) — *empty*

> 🔧 **Tool call → `web_fetch`**

> *(tool input not included in claude.ai share data)*

> 🧰 Result ← `web_fetch` (0 items) — *empty*

> 🔧 **Tool call → `web_fetch`**

> *(tool input not included in claude.ai share data)*

> 🧰 Result ← `web_fetch` (0 items) — *empty*

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "archon.diy supported agents claude code codex gemini cli"
}
```

<details>
<summary>🧰 Result ← `web_search` (8 items)</summary>

- [feat: Pi coding-agent as third AI assistant provider · Issue #965 · coleam00/Archon](https://github.com/coleam00/Archon/issues/965) — github.com
- [Wrap Claude Code and Codex With Archon for Determinism | MindStudio](https://www.mindstudio.ai/blog/what-is-archon-harness-builder-ai-coding) — mindstudio.ai
- [Archon/CLAUDE.md at dev · coleam00/Archon](https://github.com/coleam00/Archon/blob/dev/CLAUDE.md) — github.com
- [How to Script AI Agent Tasks With Codex, Gemini & Claude](https://www.systweak.com/blogs/script-ai-agent-tasks-with-codex-gemini-claude/) — systweak.com
- [CLI Coding Agents Comparison - Claude Code, Codex CLI, Gemini CLI, and More | hidekazu-konishi.com](https://hidekazu-konishi.com/entry/cli_coding_agents_comparison.html) — hidekazu-konishi.com
- [AI CLI Agent Swarm: Run Claude Code, Codex and Gemini Together (2026)](https://www.codeagentswarm.com/en/guides/ai-cli-agent-swarm) — codeagentswarm.com
- [Roadmap — Archon](https://archon.diy/roadmap/) — archon.diy
- [AI Assistants | Archon](https://archon.diy/getting-started/ai-assistants/) — archon.diy

</details>

> 🔧 **Tool call → `web_fetch`**

> *(tool input not included in claude.ai share data)*

> 🧰 Result ← `web_fetch` (0 items) — *empty*

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "vibe-kanban Bloop shutdown maintenance 2026"
}
```

<details>
<summary>🧰 Result ← `web_search` (8 items)</summary>

- [Sudden unintended shutdown after a few seconds/minutes of usage · Issue #3231 · BloopAI/vibe-kanban](https://github.com/BloopAI/vibe-kanban/issues/3231) — github.com
- [Vibe Kanban - Orchestrate AI Coding Agents](https://www.vibekanban.com/release-notes) — vibekanban.com
- [VibeKanban - Shutdown](https://www.vibekanban.com/blog/shutdown) — vibekanban.com
- [MCP Project Management: Vibe Kanban Proved the... | Agiflow](https://agiflow.io/blog/building-before-the-market-is-ready) — agiflow.io
- [Best Vibe Kanban Alternative for Multi-Agent Coding (2026) | Nimbalyst](https://nimbalyst.com/compare/vibe-kanban/) — nimbalyst.com
- [Vibe Kanban After Bloop: What Happens to Users, and Where to Go | Nimbalyst](https://nimbalyst.com/blog/vibe-kanban-after-bloop-whats-next/) — nimbalyst.com
- [Parallel Code vs Vibe Kanban: Native App Alternative (2026)](https://parallelcode.app/compare/parallel-code-vs-vibe-kanban/) — parallelcode.app
- [Best Vibe Kanban Alternatives in 2026 | Nimbalyst](https://nimbalyst.com/blog/best-vibe-kanban-alternatives-2026/) — nimbalyst.com

</details>

Short version: the "dark factory" category is real but very young — everything on your list is under a year old, so "mature" is relative. Two of your five are serious candidates (Fabro, Archon), one is credible but aimed at a different problem (Swamp), one is a complement rather than a factory (human), and one you should skip. Here's the rundown:

**Fabro** — the strongest engineering on your list. Built by Bryan Helmkamp (Code Climate founder, now Qlty), open-sourced in March 2026 as "the dark software factory for small teams of expert engineers". You define workflow graphs in Graphviz DOT — agents, shell commands, human gates — and Fabro handles orchestration, parallelism, model routing via CSS-like stylesheets, verification, and observability. It's a single compiled Rust binary, runs agents in isolated sandboxes, layers deterministic verifications (tests, linters, LLM-as-judge) as gates, and checkpoints every stage to Git branches. Model catalog covers Anthropic, OpenAI, and Gemini natively plus OpenRouter/LiteLLM/Bedrock/Ollama. Shipping velocity is remarkable (near-daily changelog since February). Caveats: the default runtime is Fabro's own agent loop calling provider APIs, so credentials are API keys or provider logins, and it uses an issue-only contribution model — no outside PRs.

**Archon** — biggest community, but freshest code. Be aware it's not what most older blog posts describe: in April 2026 Cole Medin replaced the old Python MCP/RAG task tool with an entirely new TypeScript workflow engine, keeping the repo and its 13.8k+ star community. You encode dev processes as YAML workflows — planning, implementation, validation gates, code review, PR creation — and it runs them in isolated worktrees, iterating until tests pass. It mixes deterministic steps with AI agents via the Claude Agent SDK and Codex SDK, with human approval gates and audit trails, drivable from Slack, Telegram, GitHub, Discord, web UI, or CLI. Gemini isn't first-class; it's reachable through community providers like Pi and OpenCode. Very active but expect churn — the rewrite is only ~3 months old.

**Swamp** — credible team (Adam Jacob of Chef/System Initiative), but a different animal. It's deterministic automation *operated by* AI agents: typed models of external systems, YAML DAG workflows, vaults, versioned data, and it works with Claude Code, Cursor, OpenCode, and Codex. They genuinely dogfood a gated dev lifecycle on it — issues move through a state machine with versioned plans, adversarial reviews, and checks that block skipping steps. But it's oriented at general automation/ops more than a code-shipping pipeline, it's AGPL-3.0 with exceptions, and only Swamp Club employees contribute code. Watch it; probably not your factory core.

**human (gethuman.sh)** — not a factory, a rig around one. It's a CLI + secured devcontainer setup (daemon, Chrome proxy, firewall, Claude Code integration) that connects Jira, Linear, GitHub and other sources, with lifecycle skills (/human-plan, /human-execute, /human-autofix) and credential isolation so the agent never sees tokens. Useful *alongside* Fabro/Archon, especially for the devcontainer security posture, but it's tiny (~33 stars), single-maintainer, and Claude Code-centric.

**owainlewis/factory** — skip for prod. It's an early personal V1: 10 commits, zero stars, Claude Code as the only agent adapter, and the README itself scopes it as a local runner spine, not a hosted or complete system.

One architectural point that matters more than any feature list, given your multi-subscription plan: there are two auth models in this space. Orchestrators that **shell out to the official CLIs/SDKs** (Claude Code, Codex, Gemini CLI) inherit subscription OAuth — Codex signs in with ChatGPT and Gemini CLI with Google, so runs bill against subscriptions, not API credits — which is how you actually amortize multiple $200 plans. Orchestrators with their **own API-calling runtime** (Fabro's default backend) need per-token API keys. Fabro's escape hatch is its ACP backend, where the agent process owns its own login and credentials — so you can run subscription-authed CLIs inside Fabro workflows, at the cost of Fabro-managed failover and sub-agents on those nodes. Archon's SDK approach (Claude Agent SDK + Codex SDK) piggybacks subscription auth more naturally for the Anthropic/OpenAI legs. Avoid the proxy projects that wrap subscription OAuth into an API endpoint for load-balancing accounts — they exist, but they run against provider terms and are a bad foundation for a prod pipeline.

My practical recommendation: prototype the same workflow on both **Fabro** (if you value the deterministic graph + sandbox + verification story and can fund API keys or use ACP nodes) and **Archon** (if your team already lives in Claude Code/Codex on Max/Pro subscriptions and wants the community momentum). Also worth knowing as context: the simpler multi-CLI orchestrators are the most battle-tested things that run all three subscriptions today — vibe-kanban (~27.5k stars) and cmux (~24.8k) lead that category — but note Bloop, the company behind Vibe Kanban, shut down in April 2026 and the project is now community-maintained. Those give you parallel worktree sessions rather than gated factory pipelines, so they're a fallback if the factories feel too bleeding-edge.

Whichever you pick: pin versions, keep human approval gates on merge, and run agents sandboxed — nothing here has the operational track record you'd normally demand for prod infrastructure. A deeper investigation could map the full orchestrator ecosystem (50+ projects) against maintenance health, license, sandboxing, and subscription-auth support to de-risk the choice further.

> **Citations:**
> - [Bryan Helmkamp on X: "Today I'm thrilled to open source what I've been working on... Meet Fabro (https://t.co/9iJbhJbMiw), the dark software factory for small teams of expert engineers. Fabro gets you out of the REPL (read-eval-prompt-loop) by layering deterministic workflow graphs over agent" / X](https://x.com/brynary/status/2033901199603241012)
> - [Why Fabro? - Fabro](https://docs.fabro.sh/getting-started/why-fabro)
> - [GitHub - fabro-sh/fabro: ⚒️ The open source dark software factory for expert engineers.](https://github.com/fabro-sh/fabro)
> - [fabro/README.md at main · fabro-sh/fabro](https://github.com/fabro-sh/fabro/blob/main/README.md)
> - [Open source Archon: migrate new codebase to coleam00/Archon · Issue #952 · coleam00/Archon](https://github.com/coleam00/Archon/issues/952)
> - [GitHub - coleam00/Archon: The first open-source harness builder for AI coding. Make AI coding deterministic and repeatable. · GitHub](https://github.com/coleam00/Archon)
> - [Archon/CLAUDE.md at dev · coleam00/Archon](https://github.com/coleam00/Archon/blob/dev/CLAUDE.md)
> - [AI Assistants | Archon](https://archon.diy/getting-started/ai-assistants/)
> - [Swamp Club · GitHub](https://github.com/swamp-club)
> - [The Lifecycle of a Swamp Issue](https://stack72.dev/the-lifecycle-of-a-swamp-issue/)
> - [Swamp Club · GitHub](https://github.com/swamp-club)
> - [human - The AI dev rig for AI coding agents](https://gethuman.sh/)
> - [Claude Code Orchestrator Setup Guide - Multi-agent workflow with Codex (writer), Gemini (auditor), and Nanobanana (image generation) · GitHub](https://gist.github.com/bjornmage/ddd6dc7f4d5e074af1db44964d377427)
> - [GitHub - bradAGI/awesome-cli-coding-agents: Curated directory of terminal-native AI coding agents and the harnesses that orchestrate them. Covers open-source tools (Pi, OpenCode, Aider, Goose), platform agents (Claude Code, Codex, Gemini CLI), parallel runners, autonomous loops, and agent infrastructure. · GitHub](https://github.com/bradAGI/awesome-cli-coding-agents)
> - [VibeKanban - Shutdown](https://www.vibekanban.com/blog/shutdown)

> 🔧 **Tool call → `suggest_research`** — Considering Research

```json
{
  "rationale": "Comparative analysis of open-source AI coding factories/orchestrators: maturity, licenses, multi-model and subscription-auth support"
}
```

<details>
<summary>🧰 Result ← `suggest_research` (1 item)</summary>

```json
{
  "suggest": true,
  "rationale": "Comparative analysis of open-source AI coding factories/orchestrators: maturity, licenses, multi-model and subscription-auth support"
}
```

</details>

---

## 👤 User  *(11:59 UTC)*

gimme the links for the additional tools you mentioned

---

## 🤖 Assistant  *(12:01 UTC)*

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "cmux github open-source parallel coding agents"
}
```

<details>
<summary>🧰 Result ← `web_search` (8 items)</summary>

- [GitHub Apps - cmux-agent · GitHub](https://github.com/apps/cmux-agent) — github.com
- [GitHub - TeamADAPT/cmux: cmux lets you run Claude Code, Codex CLI, Amp, Gemini CLI, Cursor CLI, Opencode, and other coding agent CLIs in parallel across multiple tasks · GitHub](https://github.com/TeamADAPT/cmux) — github.com
- [GitHub - andyrewlee/awesome-agent-orchestrators: List of agent orchestrators · GitHub](https://github.com/andyrewlee/awesome-agent-orchestrators) — github.com
- [cmux: The open-source terminal built for coding agents | Product Hunt](https://www.producthunt.com/products/cmux) — producthunt.com
- [GitHub - manaflow-ai/cmux: Open source Ghostty-based macOS terminal with vertical tabs and notifications for AI coding agents. Built for multitasking, organization, and programmability. · GitHub](https://github.com/manaflow-ai/cmux) — github.com
- [cmux Review 2026: Native macOS Terminal for Parallel AI Coding Agents](https://vibecodinghub.org/tools/cmux) — vibecodinghub.org
- [cmux: The Native macOS Terminal Built for Running AI Coding Agents in Parallel - DEV Community](https://dev.to/arshtechpro/cmux-the-native-macos-terminal-built-for-running-ai-coding-agents-in-parallel-52il) — dev.to
- [cmux: a purpose-built terminal for the parallel agent workflow - ddewhurst](https://ddewhurst.com/blog/cmux-purpose-built-terminal-for-parallel-agent-workflow/) — ddewhurst.com

</details>

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "pi coding agent mariozechner github repo"
}
```

<details>
<summary>🧰 Result ← `web_search` (8 items)</summary>

- [oh-my-pi/README.md at main · can1357/oh-my-pi](https://github.com/can1357/oh-my-pi/blob/main/README.md) — github.com
- [badlogic (Mario Zechner) · GitHub](https://github.com/badlogic) — github.com
- [GitHub - badlogic/pi-skills: Skills for pi coding agent (compatible with Claude Code and Codex CLI) · GitHub](https://github.com/badlogic/pi-skills) — github.com
- [GitHub - alexennube/pi-agent: AI agent toolkit: coding agent CLI, unified LLM API, TUI & web UI libraries, Slack bot, vLLM pods · GitHub](https://github.com/alexennube/pi-agent) — github.com
- [GitHub - can1357/oh-my-pi: ⌥ AI Coding agent for the terminal — hash-anchored edits, optimized tool harness, LSP, Python, browser, subagents, and more](https://github.com/can1357/oh-my-pi) — github.com
- [How to Build a Custom Agent Framework with PI: The Agent Stack Powering OpenClaw · GitHub](https://gist.github.com/dabit3/e97dbfe71298b1df4d36542aceb5f158) — github.com
- [mariozechner/pi-coding-agent](https://www.npmjs.com/package/@mariozechner/pi-coding-agent) — npmjs.com
- [Pi Coding Agent -- Sandbox Analysis Report | Agent Safehouse](https://agent-safehouse.dev/docs/agent-investigations/pi) — agent-safehouse.dev

</details>

> 🔧 **Tool call → `link_preview_display_v0`** — Links to the orchestrators, agents, and directories mentioned earlier.

```json
{
  "links": [
    {
      "url": "https://github.com/BloopAI/vibe-kanban",
      "title": "Vibe Kanban — kanban board for orchestrating coding agents",
      "domain": "GitHub",
      "snippet": "Runs Claude Code, Codex, Gemini CLI, Cursor, and more in parallel worktrees. Apache-2.0, community-maintained since Bloop shut down in April 2026."
    },
    {
      "url": "https://github.com/manaflow-ai/cmux",
      "title": "cmux — terminal built for running agents in parallel",
      "domain": "GitHub",
      "snippet": "Native macOS app on libghostty with vertical tabs, agent notifications, worktree/SSH workspaces, and a scriptable CLI. AGPL-3.0."
    },
    {
      "url": "https://github.com/sst/opencode",
      "title": "OpenCode — open-source multi-provider coding agent",
      "domain": "GitHub",
      "snippet": "Terminal agent supporting Anthropic, OpenAI, Google and 75+ providers, including signing in with existing subscriptions. Also at opencode.ai."
    },
    {
      "url": "https://github.com/earendil-works/pi",
      "title": "Pi — AI agent toolkit and coding agent CLI",
      "domain": "GitHub",
      "snippet": "Mario Zechner's TypeScript monorepo: unified LLM API, agent loop, TUI, and the pi coding agent (npm: @mariozechner/pi-coding-agent). This is Archon's route to Gemini and other providers."
    },
    {
      "url": "https://github.com/andyrewlee/awesome-agent-orchestrators",
      "title": "awesome-agent-orchestrators — curated list of orchestrators",
      "domain": "GitHub",
      "snippet": "The most complete directory of multi-agent coding orchestrators (50+ projects), updated frequently."
    },
    {
      "url": "https://github.com/bradAGI/awesome-cli-coding-agents",
      "title": "awesome-cli-coding-agents — CLI agents and harnesses",
      "domain": "GitHub",
      "snippet": "Directory of terminal coding agents, parallel runners, autonomous loops, and agent infrastructure, with star counts to gauge traction."
    }
  ],
  "summary": "Links to the orchestrators, agents, and directories mentioned earlier."
}
```

<details>
<summary>🧰 Result ← `link_preview_display_v0` (1 item)</summary>

```json
{
  "links": [
    {
      "url": "https://github.com/BloopAI/vibe-kanban",
      "title": "Vibe Kanban — kanban board for orchestrating coding agents",
      "domain": "GitHub",
      "snippet": "Runs Claude Code, Codex, Gemini CLI, Cursor, and more in parallel worktrees. Apache-2.0, community-maintained since Bloop shut down in April 2026."
    },
    {
      "url": "https://github.com/manaflow-ai/cmux",
      "title": "cmux — terminal built for running agents in parallel",
      "domain": "GitHub",
      "snippet": "Native macOS app on libghostty with vertical tabs, agent notifications, worktree/SSH workspaces, and a scriptable CLI. AGPL-3.0."
    },
    {
      "url": "https://github.com/sst/opencode",
      "title": "OpenCode — open-source multi-provider coding agent",
      "domain": "GitHub",
      "snippet": "Terminal agent supporting Anthropic, OpenAI, Google and 75+ providers, including signing in with existing subscriptions. Also at opencode.ai."
    },
    {
      "url": "https://github.com/earendil-works/pi",
      "title": "Pi — AI agent toolkit and coding agent CLI",
      "domain": "GitHub",
      "snippet": "Mario Zechner's TypeScript monorepo: unified LLM API, agent loop, TUI, and the pi coding agent (npm: @mariozechner/pi-coding-agent). This is Archon's route to Gemini and other providers."
    },
    {
      "url": "https://github.com/andyrewlee/awesome-agent-orchestrators",
      "title": "awesome-agent-orchestrators — curated list of orchestrators",
      "domain": "GitHub",
      "snippet": "The most complete directory of multi-agent coding orchestrators (50+ projects), updated frequently."
    },
    {
      "url": "https://github.com/bradAGI/awesome-cli-coding-agents",
      "title": "awesome-cli-coding-agents — CLI agents and harnesses",
      "domain": "GitHub",
      "snippet": "Directory of terminal coding agents, parallel runners, autonomous loops, and agent infrastructure, with star counts to gauge traction."
    }
  ],
  "summary": "Links to the orchestrators, agents, and directories mentioned earlier."
}
```

</details>

A couple of notes on those: cmux started as a Docker-based orchestrator platform but has since been rebuilt as a native Swift/AppKit terminal on libghostty, so older writeups describe a different shape than what you'll install today. And Pi's repo recently moved to the earendil-works org (formerly badlogic/pi-mono), so both paths redirect to the same place.

For the SDK auth route I mentioned for Archon: the Claude Agent SDK docs are at https://docs.claude.com/en/api/agent-sdk/overview and the Codex SDK docs at https://developers.openai.com/codex/sdk. And the subscription-to-API proxy I warned about is CLIProxyAPI (upstream at https://github.com/router-for-me/CLIProxyAPI, with many forks floating around) — linking it for completeness, but same caveat as before: it sits against provider terms, so I wouldn't build a production pipeline on it.

> **Citations:**
> - [GitHub - manaflow-ai/cmux: Open source Ghostty-based macOS terminal with vertical tabs and notifications for AI coding agents. Built for multitasking, organization, and programmability. · GitHub](https://github.com/manaflow-ai/cmux)

---

## 👤 User  *(13:43 UTC)*

gimme Comparative analysis of open-source AI coding factories/orchestrators: maturity, licenses, multi-model and subscription-auth support that you mentioned previously above

---

## 🤖 Assistant  *(13:48 UTC)*

> 🔧 **Tool call → `view`**

> *(tool input not included in claude.ai share data)*

> 🧰 Result ← `view` (0 items) — *empty*

> 🔧 **Tool call → `web_search`** — Searching the web

```json
{
  "query": "Claude Agent SDK authentication Claude Code subscription Max"
}
```

<details>
<summary>🧰 Result ← `web_search` (8 items)</summary>

- [Agent SDK should support Max plan billing, not just API keys · Issue #559 · anthropics/claude-agent-sdk-python](https://github.com/anthropics/claude-agent-sdk-python/issues/559) — github.com
- [Community Providers: Claude Code](https://ai-sdk.dev/providers/community-providers/claude-code) — ai-sdk.dev
- [How I Built claude_max to unlock Claude Code's Full Power with Anthropic's Max Subscription](https://substack.com/home/post/p-166025131) — substack.com
- [How to use your Claude Pro/Max subscription with the Agent SDK (Python + TypeScript) - DEV Community](https://dev.to/aviv_shaked/how-to-use-your-claude-promax-subscription-with-the-agent-sdk-python-typescript-4emi) — dev.to
- [Use Claude Code with your Pro or Max plan | Claude Help Center](https://support.claude.com/en/articles/11145838-use-claude-code-with-your-pro-or-max-plan) — claude.com
- [Is This Allowed? Claude Code Terms of Service Explained – autonomee.ai](https://autonomee.ai/blog/claude-code-terms-of-service-explained/) — autonomee.ai
- [Anthropic officially bans using subscription authentication for third-party Claude use](https://alternativeto.net/news/2026/2/anthropic-officially-bans-using-subscription-authentication-for-third-party-claude-use) — alternativeto.net
- [How I Built claude_max to unlock Claude Code's Full Power with Anthropic's Max Subscription](https://idsc2025.substack.com/p/how-i-built-claude_max-to-unlock) — substack.com

</details>

> 🔧 **Tool call → `visualize:read_me`** — Read me

```json
{
  "modules": [
    "mockup"
  ],
  "platform": "mobile"
}
```

<details>
<summary>🧰 Result ← `visualize:read_me` (1 item)</summary>

````
# Imagine — Visual Creation Suite

## Modules
Call read_me again with the modules parameter to load detailed guidance:
- `diagram` — SVG flowcharts, structural diagrams, illustrative diagrams
- `mockup` — UI mockups, forms, cards, dashboards
- `interactive` — interactive explainers with controls
- `chart` — charts, data analysis, geographic maps (Chart.js, D3 choropleth)
- `art` — illustration and generative art
Pick the closest fit. The module includes all relevant design guidance.

**Complexity budget — hard limits:**
- Box subtitles: ≤5 words. Detail goes in click-through (`sendPrompt`) or the prose below — not the box.
- Colors: ≤2 ramps per diagram. If colors encode meaning (states, tiers), add a 1-line legend. Otherwise use one neutral ramp.
- Horizontal tier: ≤4 boxes at full width (~140px each). 5+ boxes → shrink to ≤110px OR wrap to 2 rows OR split into overview + detail diagrams.

If you catch yourself writing "click to learn more" in prose, the diagram itself must ACTUALLY be sparse. Don't promise brevity then front-load everything.

**Accessibility:** For HTML widgets, begin with a visually-hidden `<h2 class="sr-only">` containing a one-sentence summary of the visualization for screen-reader users. (SVG widgets use `role="img"` with `<title>` and `<desc>` instead — see SVG setup.)

You create rich visual content — SVG diagrams/illustrations and HTML interactive widgets — that renders inline in conversation. The best output feels like a natural extension of the chat.

## Core Design System

These rules apply to ALL use cases.

### Philosophy
- **Seamless**: Users shouldn't notice where claude.ai ends and your widget begins.
- **Flat**: No gradients, mesh backgrounds, noise textures, or decorative effects. Clean flat surfaces.
- **Compact**: Show the essential inline. Explain the rest in text.
- **Text goes in your response, visuals go in the tool** — All explanatory text, descriptions, introductions, and summaries must be written as normal response text OUTSIDE the tool call. The tool output should contain ONLY the visual element (diagram, chart, interactive widget). Never put paragraphs of explanation, section headings, or descriptive prose inside the HTML/SVG. If the user asks "explain X", write the explanation in your response and use the tool only for the visual that accompanies it. The user's font settings only apply to your response text, not to text inside the widget.

### Streaming
Output streams token-by-token. Structure code so useful content appears early.
- **HTML**: `<style>` (short) → content HTML → `<script>` last.
- **SVG**: `<defs>` (markers) → visual elements immediately.
- Prefer inline `style="..."` over `<style>` blocks — inputs/controls must look correct mid-stream.
- Keep `<style>` under ~15 lines. Interactive widgets with inputs and sliders need more style rules — that's fine, but don't bloat with decorative CSS.
- Gradients, shadows, and blur flash during streaming DOM diffs. Use solid flat fills instead.

### Rules
- No `<!-- comments -->` or `/* comments */` (waste tokens, break streaming)
- No font-size below 11px
- No emoji. Icons = Tabler **outline** webfont (5800+, already loaded): `<i class="ti ti-home"></i>`. Outline only — never use `-filled` suffixes (`ti-heart-filled` etc. are not loaded and will render blank). Inherits color + font-size from parent. Decorative icons get `aria-hidden="true"`; icon-only buttons get `aria-label`. Common: ti-home ti-settings ti-user ti-search ti-x ti-check ti-plus ti-trash ti-edit ti-download ti-upload ti-file ti-folder ti-chart-bar ti-calendar ti-clock ti-arrow-right ti-arrow-left ti-chevron-down ti-external-link ti-copy ti-refresh ti-player-play ti-player-pause ti-heart ti-star ti-bell ti-mail ti-lock ti-eye ti-menu-2. Don't hand-draw icon SVG paths.
- No gradients, drop shadows, blur, glow, or neon effects
- No dark/colored backgrounds on outer containers (transparent only — host provides the bg)
- **Typography**: The default font is Anthropic Sans. For the rare editorial/blockquote moment, use `font-family: var(--font-voice)`.
- **Headings**: h1 = 22px, h2 = 18px, h3 = 16px — all `font-weight: 500`. Heading color is pre-set to `var(--text-primary)` — don't override it. Body text = 16px, weight 400, `line-height: 1.7`. **Two weights only: 400 regular, 500 bold.** Never use 600 or 700 — they look heavy against the host UI.
- **Sentence case** always. Never Title Case, never ALL CAPS. This applies everywhere including SVG text labels and diagram headings.
- **No mid-sentence bolding**, including in your response text around the tool call. Entity names, class names, function names go in `code style` not **bold**. Bold is for headings and labels only.
- The widget container is `display: block; width: 100%`. Your HTML fills it naturally — no wrapper div needed. Just start with your content directly. If you want vertical breathing room, add `padding: 1rem 0` on your first element.
- Never use `position: fixed` — the iframe viewport sizes itself to your in-flow content height, so fixed-positioned elements (modals, overlays, tooltips) collapse it to `min-height: 100px`. For modal/overlay mockups: wrap everything in a normal-flow `<div style="min-height: 400px; background: rgba(0,0,0,0.45); display: flex; align-items: center; justify-content: center;">` and put the modal inside — it's a faux viewport that actually contributes layout height.
- No DOCTYPE, `<html>`, `<head>`, or `<body>` — just content fragments.
- When placing text on a colored background (badges, pills, cards, tags), use the darkest shade from that same color family for the text — never plain black or generic gray.
- **Corners**: use `border-radius: var(--radius)` for controls, `12px` for cards. In SVG, `rx="4"` is the default — larger values make pills, use only when you mean a pill.
- **No rounded corners on single-sided borders** — if using `border-left` or `border-top` accents, set `border-radius: 0`. Rounded corners only work with full borders on all sides.
- **No titles or prose inside the tool output** — see Philosophy above.
- **Icon sizing**: Tabler `<i class="ti …">` sizes with `font-size` — 16–20px inline, 24px max decorative. For one-off inline SVG icons, set `width`/`height` explicitly (same limits).
- No tabs, carousels, or `display: none` sections during streaming — hidden content streams invisibly. Show all content stacked vertically. (Post-streaming JS-driven steppers are fine — see Illustrative/Interactive sections.)
- No nested scrolling — auto-fit height.
- Scripts execute after streaming — load libraries via `<script src="https://cdnjs.cloudflare.com/ajax/libs/...">` (UMD globals), then use the global in a plain `<script>` that follows. The library `<script src>` tag must come BEFORE any inline script that uses its global — never call a library from code that appears above its `<script src>` tag.
- **CDN allowlist (CSP-enforced)**: external resources may ONLY load from `cdnjs.cloudflare.com`, `esm.sh`, `cdn.jsdelivr.net`, `unpkg.com`, `fonts.googleapis.com`, `fonts.gstatic.com`. All other origins are blocked by the sandbox — the request silently fails.

### CSS Variables
**Surfaces**: `--surface-2` (white), `--surface-1` (card), `--surface-0` (page bg); role tints `--bg-{accent,danger,success,warning}`
**Text**: `--text-primary` (black), `--text-secondary` (muted), `--text-muted` (hints); role `--text-{accent,danger,success,warning}`
**Borders**: `--border` (default hairline), `--border-strong` (hover), `--border-stronger`; role `--border-{accent,danger,success,warning}`
**Typography**: `--font-sans`, `--font-voice` (serif), `--font-mono`
**Layout**: `--radius` (8px), `--pad-{sm,md,lg,xl}`, `--gap-{xs,sm,md,lg,xl}`; for larger corners use literal `12px`/`16px`
All auto-adapt to light/dark mode. For custom colors in HTML, use CSS variables.

**Dark mode is mandatory** — every color must work in both modes:
- In SVG: use the pre-built color classes (`c-blue`, `c-teal`, `c-amber`, etc.) for colored nodes — they handle light/dark mode automatically. Never write `<style>` blocks for colors.
- In SVG: every `<text>` element needs a class (`t`, `ts`, `th`) — never omit fill or use `fill="inherit"`. Inside a `c-{color}` parent, text classes auto-adjust to the ramp.
- In HTML: always use CSS variables (--text-primary, --text-secondary) for text. Never hardcode colors like color: #333 — invisible in dark mode.
- Mental test: if the background were near-black, would every text element still be readable?

### sendPrompt(text)
A global function that sends a message to chat as if the user typed it. Use it when the user's next step benefits from Claude thinking. Handle filtering, sorting, toggling, and calculations in JS instead.

### Links
`<a href="https://...">` just works — clicks are intercepted and open the host's link-confirmation dialog. Or call `openLink(url)` directly.

## When nothing fits
Pick the closest use case below and adapt. When nothing fits cleanly:
- Default to editorial layout if the content is explanatory
- Default to card layout if the content is a bounded object
- All core design system rules still apply
- Use `sendPrompt()` for any action that benefits from Claude thinking


## UI components

### Layout width
The widget container is 380px wide. **Mobile column cap.** The widget container is ~380px wide — never lay out more than TWO columns of cards, stats, controls, or option grids. Three-up at this width is unreadable: card content wraps to 3-4 lines and tap targets fall below 44px. Use `repeat(auto-fit, minmax(160px, 1fr))` (which naturally tops out at 2 here) or `repeat(2, minmax(0, 1fr))` explicitly. If you have 3+ items, stack them in 2-col rows or go single-column; do not write `repeat(3, …)` or `repeat(4, …)`.

### Aesthetic
Flat, clean, white surfaces. Minimal 0.5px borders. Generous whitespace. No gradients, no shadows (except functional focus rings). Everything should feel native to claude.ai — like it belongs on the page, not embedded from somewhere else.

### Tokens
- Borders: always `0.5px solid var(--border)` (or `--border-strong` for emphasis)
- Corner radius: `var(--radius)` for most elements, `12px` for cards
- Cards: white bg (`var(--surface-2)`), 0.5px border, 12px radius, padding 1rem 1.25rem
- Form elements (input, select, textarea, button, range slider) are pre-styled — write bare tags. Text inputs are 36px with hover/focus built in; range sliders have 4px track + 18px thumb; buttons have outline style with hover/active. Only add inline styles to override (e.g., different width).
- Buttons: pre-styled with transparent bg, 0.5px `--border-strong` border, hover `--surface-1`, active scale(0.98). If it triggers sendPrompt, append a ↗ arrow.
- **Round every displayed number.** JS float math leaks artifacts — `0.1 + 0.2` gives `0.30000000000000004`, `7 * 1.1` gives `7.700000000000001`. Any number that reaches the screen (slider readouts, stat card values, axis labels, data-point labels, tooltips, computed totals) must go through `Math.round()`, `.toFixed(n)`, or `Intl.NumberFormat`. Pick the precision that makes sense for the context — integers for counts, 1–2 decimals for percentages, `toLocaleString()` for currency. For range sliders, also set `step="1"` (or step="0.1" etc.) so the input itself emits round values.
- Spacing: use rem for vertical rhythm (1rem, 1.5rem, 2rem), px for component-internal gaps (8px, 12px, 16px)
- Box-shadows: none, except `box-shadow: 0 0 0 Npx` focus rings on inputs

### Metric cards
For summary numbers (revenue, count, percentage) — surface card with muted 13px label above, 24px/500 number below. `background: var(--surface-1)`, no border, `border-radius: var(--radius)`, padding 1rem. Use in grids of 2-4 with `gap: 12px`. Distinct from raised cards (which have white bg + border).

### Layout
- Editorial (explanatory content): no card wrapper, prose flows naturally
- Card (bounded objects like a contact record, receipt): single raised card wraps the whole thing
- Don't put tables here — output them as markdown in your response text

**Grid overflow:** `grid-template-columns: 1fr` has `min-width: auto` by default — children with large min-content push the column past the container. Use `minmax(0, 1fr)` to clamp.

**Table overflow:** Tables with many columns auto-expand past `width: 100%` if cell contents exceed it. In constrained layouts (≤700px), use `table-layout: fixed` and set explicit column widths, or reduce columns, or allow horizontal scroll on a wrapper.

### Mockup presentation
Contained mockups — mobile screens, chat threads, single cards, modals, small UI components — should sit on a background surface (`var(--surface-1)` container with `border-radius: 12px` and padding, or a device frame) so they don't float naked on the widget canvas. Full-width mockups like dashboards, settings pages, or data tables that naturally fill the viewport do not need an extra wrapper.

### 1. Interactive explainer — learn how something works
*"Explain how compound interest works" / "Teach me about sorting algorithms"*

Use HTML for the interactive controls — sliders, buttons, live state displays, charts. Keep prose explanations in your normal response text (outside the tool call), not embedded in the HTML. No card wrapper. Whitespace is the container.

```html
<div style="display: flex; align-items: center; gap: 12px; margin: 0 0 1.5rem;">
  <label style="font-size: 14px; color: var(--text-secondary);">Years</label>
  <input type="range" min="1" max="40" value="20" id="years" style="flex: 1;" />
  <span style="font-size: 14px; font-weight: 500; min-width: 24px;" id="years-out">20</span>
</div>

<div style="display: flex; align-items: baseline; gap: 8px; margin: 0 0 1.5rem;">
  <span style="font-size: 14px; color: var(--text-secondary);">£1,000 →</span>
  <span style="font-size: 24px; font-weight: 500;" id="result">£3,870</span>
</div>

<div style="margin: 2rem 0; position: relative; height: 240px;">
  <canvas id="chart"></canvas>
</div>
```

Use `sendPrompt()` to let users ask follow-ups: `sendPrompt('What if I increase the rate to 10%?')`

### 2. Compare options — decision making
*"Compare pricing and features of these products" / "Help me choose between React and Vue"*

Use HTML. Side-by-side card grid for options. Highlight differences with semantic colors. Interactive elements for filtering or weighting.

- Each option in a card. Use badges for key differentiators. A leading Tabler icon (`<i class="ti ti-NAME">` at 20px, `aria-hidden`) anchors each option visually — pick the most apt name per option.
- Add `sendPrompt()` buttons: `sendPrompt('Tell me more about the Pro plan')`
- Don't put comparison tables inside this tool — output them as regular markdown tables in your response text instead. The tool is for the visual card grid only.
- When one option is recommended or "most popular", accent its card with `border: 2px solid var(--border-accent)` only (2px is deliberate — the only exception to the 0.5px rule, used to accent featured items) — keep the same background and border as the other cards. Add a small badge (e.g. "Most popular") above or inside the card header using `background: var(--bg-accent); color: var(--text-accent); font-size: 12px; padding: 4px 12px; border-radius: var(--radius)`.

### 3. Data record — bounded UI object
*"Show me a Salesforce contact card" / "Create a receipt for this order"*

Use HTML. Wrap the entire thing in a single raised card. All content is sans-serif since it's pure UI. Use an avatar/initials circle for people (see example below).

```html
<div style="background: var(--surface-2); border-radius: 12px; border: 0.5px solid var(--border); padding: 1rem 1.25rem;">
  <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 16px;">
    <div style="width: 44px; height: 44px; border-radius: 50%; background: var(--bg-accent); display: flex; align-items: center; justify-content: center; font-weight: 500; font-size: 14px; color: var(--text-accent);">MR</div>
    <div>
      <p style="font-weight: 500; font-size: 15px; margin: 0;">Maya Rodriguez</p>
      <p style="font-size: 13px; color: var(--text-secondary); margin: 0;">VP of Engineering</p>
    </div>
  </div>
  <div style="border-top: 0.5px solid var(--border); padding-top: 12px;">
    <table style="width: 100%; font-size: 13px;">
      <tr><td style="color: var(--text-secondary); padding: 4px 0;"><i class="ti ti-mail" style="font-size:16px; vertical-align:-2px; margin-right:6px" aria-hidden="true"></i>Email</td><td style="text-align: right; padding: 4px 0; color: var(--text-accent);">m.rodriguez@acme.com</td></tr>
      <tr><td style="color: var(--text-secondary); padding: 4px 0;"><i class="ti ti-phone" style="font-size:16px; vertical-align:-2px; margin-right:6px" aria-hidden="true"></i>Phone</td><td style="text-align: right; padding: 4px 0;">+1 (415) 555-0172</td></tr>
    </table>
  </div>
</div>
```


## Color palette

9 color ramps, each with 7 stops from lightest to darkest. 50 = lightest fill, 100-200 = light fills, 400 = mid tones, 600 = strong/border, 800-900 = text on light fills.

| Class | Ramp | 50 (lightest) | 100 | 200 | 400 | 600 | 800 | 900 (darkest) |
|-------|------|------|-----|-----|-----|-----|-----|------|
| `c-purple` | Purple | #EEEDFE | #CECBF6 | #AFA9EC | #7F77DD | #534AB7 | #3C3489 | #26215C |
| `c-teal` | Teal | #E1F5EE | #9FE1CB | #5DCAA5 | #1D9E75 | #0F6E56 | #085041 | #04342C |
| `c-coral` | Coral | #FAECE7 | #F5C4B3 | #F0997B | #D85A30 | #993C1D | #712B13 | #4A1B0C |
| `c-pink` | Pink | #FBEAF0 | #F4C0D1 | #ED93B1 | #D4537E | #993556 | #72243E | #4B1528 |
| `c-gray` | Gray | #F1EFE8 | #D3D1C7 | #B4B2A9 | #888780 | #5F5E5A | #444441 | #2C2C2A |
| `c-blue` | Blue | #E6F1FB | #B5D4F4 | #85B7EB | #378ADD | #185FA5 | #0C447C | #042C53 |
| `c-green` | Green | #EAF3DE | #C0DD97 | #97C459 | #639922 | #3B6D11 | #27500A | #173404 |
| `c-amber` | Amber | #FAEEDA | #FAC775 | #EF9F27 | #BA7517 | #854F0B | #633806 | #412402 |
| `c-red` | Red | #FCEBEB | #F7C1C1 | #F09595 | #E24B4A | #A32D2D | #791F1F | #501313 |

**How to assign colors**: Color should encode meaning, not sequence. Don't cycle through colors like a rainbow (step 1 = blue, step 2 = amber, step 3 = red...). Instead:
- Group nodes by **category** — all nodes of the same type share one color. E.g. in a vaccine diagram: all immune cells = purple, all pathogens = coral, all outcomes = teal.
- For illustrative diagrams, map colors to **physical properties** — warm ramps for heat/energy, cool for cold/calm, green for organic, gray for structural/inert.
- Use **gray for neutral/structural** nodes (start, end, generic steps).
- Use **2-3 colors per diagram**, not 6+. More colors = more visual noise. A diagram with gray + purple + teal is cleaner than one using every ramp.
- **Prefer purple, teal, coral, pink** for general diagram categories. Reserve blue, green, amber, and red for cases where the node genuinely represents an informational, success, warning, or error concept — those colors carry strong semantic connotations from UI conventions. (Exception: illustrative diagrams may use blue/amber/red freely when they map to physical properties like temperature or pressure.)

**Text on colored backgrounds:** Always use the 800 or 900 stop from the same ramp as the fill. Never use black, gray, or --text-primary on colored fills. **When a box has both a title and a subtitle, they must be two different stops** — title darker (800 in light mode, 100 in dark), subtitle lighter (600 in light, 200 in dark). Same stop for both reads flat; the weight difference alone isn't enough. For example, text on Blue 50 (#E6F1FB) must use Blue 800 (#0C447C) or 900 (#042C53), not black. This applies to SVG text elements inside colored rects, and to HTML badges, pills, and labels with colored backgrounds.

**Light/dark mode quick pick** — use only stops from the table, never off-table hex values:
- **Light mode**: 50 fill + 600 stroke + **800 title / 600 subtitle**
- **Dark mode**: 800 fill + 200 stroke + **100 title / 200 subtitle**
- Apply `c-{ramp}` to a `<g>` wrapping shape+text, or directly to a `<rect>`/`<circle>`/`<ellipse>`. Never to `<path>` — paths don't get ramp fill. For colored connector strokes use inline `stroke="#..."` (any mid-ramp hex works in both modes). Dark mode is automatic for ramp classes. Available: c-gray, c-blue, c-red, c-amber, c-green, c-teal, c-purple, c-coral, c-pink.

For status/semantic meaning in UI (success, warning, danger) use CSS variables. For categorical coloring in both diagrams and UI, use these ramps.


<!-- @generated by apps/cds-docs/scripts/gen-cds-skill.mjs from packages/cds/{CLAUDE.md,docs/**}. Do not edit by hand — edit the source docs and re-run `yarn workspace @ant/cds-docs gen:cds-skill`. -->

# CDS tokens — vanilla

The Claude Design System token vocabulary for plain HTML/CSS/SVG
surfaces without React or Tailwind. Tokens are unprefixed CSS custom
properties (`--text-primary`, `--surface-1`, `--border`) declared on
`:root` by `@ant/cds/tokens.vanilla.css`, with dark-mode overrides under
`[data-mode="dark"]` and `@media (prefers-color-scheme: dark)`.

References below to `CdsRoot`, `Button`, or Tailwind utilities belong to
the React build; in vanilla, read a utility like `bg-surface-1` as the
underlying `var(--surface-1)`.

## Rules

### Token rule

Reference purpose-layer tokens as CSS custom properties:

```css
/* GOOD */
background: var(--surface-1);
color: var(--text-secondary);
border: 0.5px solid var(--border);

/* BAD — raw hex, invisible in dark mode */
color: #3d3d3a;
```

| Property   | Tokens |
| ---------- | ------ |
| Background | `--surface-{0..3,popover,panel}` · `--bg-{accent,danger,success,warning,pro,neutral}` · `--fill-{role}` |
| Text       | `--text-{primary,secondary,muted,disabled}` · `--text-{accent,danger,success,warning,pro}` · `--on-{role}` |
| Border     | `--border` (default hairline) · `--border-{strong,stronger}` · `--border-{role}` |
| Sizing     | `--h-control` · `--pad-{sm,md,lg,xl}` · `--gap-{xs,sm,md,lg,xl}` · `--radius` |
| Typography | `--font-{sans,mono,voice}` · `--font-size-{caption,footnote,body,code,heading,title}` |
| Shadow     | `--shadow-{sm,md,lg,popover}` |
| Motion     | `--dur-{fast,snap,base,slow}` · `--ease-{out,snap,overshoot}` |

### Dark mode rule

Dark mode is `[data-mode="dark"]` on `:root` (or `prefers-color-scheme: dark` with no explicit `data-mode`). All tokens flip automatically — never hardcode a dark-mode override.

### Muted text rule

Supporting copy uses `color: var(--text-secondary)`; reserve `var(--text-muted)` for placeholders, captions, and metadata. **Never** `opacity` on text — opacity multiplies against the background and drifts per-surface.

### Accent rule

At most **one** accent-filled (`variant="primary"`) Button per view; siblings use `secondary` or `ghost`. The `brand` (clay) role is reserved for Claude-initiated actions — send, generate — never ordinary user CTAs.

### Restraint rule

Default to the quieter, lighter option — "too cluttered" is the most common design note.

- `secondary` is the default Button; `primary` / `brand` read as aggressive — don't reach for them in popovers, banners, or dense tool/canvas surfaces.
- Avoid disabled buttons. Keep them enabled and respond on use (disabled controls are low-contrast and show no tooltip on touch); use `disabledReason` only when you genuinely must disable.
- Dense lists: bordered rows, not rounded-rect cards.

### Elevation rule

`surface-0` is the page canvas (via `--page-bg`); `1`/`2`/`3` step above it. At most **two** floating elevations (`panel` / `popover`) on screen at once. A third floating layer means `Dialog`, not popover-on-popover. Flat in-flow tiles (`rounded-card bg-surface-1 shadow-card-ring`) have no depth and don't count toward this limit.

---

## CDS principles

How something feels like Claude — the philosophy behind the tokens. Tokens tell you _what_ you can use; the [Rules](../CLAUDE.md#rules) tell you _how_ to apply them. These principles tell you _why_.

## Claude-native

cds is designed to be authored _by_ Claude as much as _for_ Claude's products. The `CLAUDE.md` you're reading is the system prompt; component docs are structured for retrieval; utilities are named so a model can guess them; the GenerateDemo page proves the loop works. A design system an LLM can use fluently is one humans can use fluently too.

## Clay is Claude's color

`brand` (clay) is reserved for what Claude does — send, generate, the spark mark. User-driven primary actions take the neutral `accent` blue; everything else stays gray. Holding clay back to a single role is what lets it carry meaning instead of becoming wallpaper.

## Serif is Claude's voice

Claude's responses render in serif; the surrounding chrome stays sans. Typography signals who's speaking before a word is read. cds ships `--font-voice` (the `font-voice` utility) for response surfaces.

## Density adapts to the surface

Console, claude.ai and antfarm share the same components — `compact` for dev tools and power users, `comfortable` for consumer apps. Density is one switch on `CdsRoot`, not a per-component prop, so a product can change its feel without forking a single component.

## Built to be extended

Every component takes `className`, every token is a public CSS var, and compound parts (`.Root`, `.Item`, `.Trigger`) sit under the porcelain helpers. The system expects you to compose past it — wrap, restyle, slot arbitrary children — not fork it.

## Restraint over options

One accent per view, one elevation step, t-shirt sizes instead of 0–12 scales. Fewer decisions at the call site means fewer ways for two screens to drift apart — consistency comes from removing knobs, not policing them.

## CDS tokens

Every visual decision in `@ant/cds` resolves to a `--*` CSS custom property. The TypeScript source of truth lives under `packages/cds/tokens/`; `yarn gen:tokens` emits the shipped CSS at [`src/generated/tokens.css`](../src/generated/tokens.css). Tokens are layered so that a single edit at the bottom (a hex value) propagates through ramps, roles, and purposes without touching component code.

## The layer model

```
1. Base palette   --{hue}-{stop}      literal hex, mode-stable (gray, red, orange,
                                          yellow, green, aqua, blue, violet, magenta)
2. Theme ramps    --neutral-N         gray-N in light, gray-(900-N) in dark
                  --alpha-N           neutral-900 @ fixed opacity (so it flips too)
3. Elevation      --surface-{0..3}    0 = darkest, 3 = lightest, in BOTH modes
4. Purpose        --surface-{popover, what components actually consume; includes the
                   panel}, --text-*,  role mappings ({fill|bg|border|text}-{role})
                   --fill-*, --on-*
—  page-bg        --page-bg           hook the host app sets to its canvas color
5. Density        --h-control*,       px values; remapped by [data-density]
                   --pad-*, --gap-*,
                   --radius, --font-size-*,
                   --leading-*
6. Motion         --dur-*,            durations + easing curves (mode/density-invariant)
                   --ease-*
```

**Components only read layer 4 (and 5 for sizing).** Layers 1–3 are wiring.

---

## 1. Base palette

Literal hex values, mode-stable — `gray-500` is the same pixel in light and dark. Nine hues share one 36-stop grid (0, 10–100 by 10, 150–800 by 50, 810–900 by 10); every hue anchors 0 = `#ffffff` and 900 = `#0b0b0b`. Rarely referenced directly — reach for layers 2–4 and let them resolve here.

---

## 2. Theme ramps

`--neutral-N` is `gray-N` in light and `gray-(900-N)` in dark, so `neutral-0` is always the near-background end and `neutral-900` the near-foreground end. Use it for "contrast against the page" (text, borders, fills); use `gray-*` when you mean a specific pixel value regardless of mode. `--alpha-N` is `neutral-900` at fixed opacity — a black wash in light, a white wash in dark, without per-mode overrides.

---

## 3. Elevation

| Token             | Light     | Dark       | Use case     |
| ----------------- | --------- | ---------- | ------------ |
| `--surface-0` | `gray-20` | `gray-890` | Page         |
| `--surface-1` | `gray-10` | `gray-830` | In-flow card |
| `--surface-2` | `gray-0`  | `gray-750` | Panel        |
| `--surface-3` | `gray-0`  | `gray-700` | Popover      |

The ordinal is absolute lightness in both modes: 0 is the darkest, 3 the lightest. `--surface-panel` and `--surface-popover` alias levels 2 and 3. The page canvas is the app's own choice — set `--page-bg` so knockout hairlines (focus ring inset, Pulse halo) blend into it; it defaults to `surface-0`.

---

## 4. Purpose

**This is the layer components consume.**

### Roles

Each role maps a semantic meaning to a hue. Property-first pattern: `--fill-{role}` (solid hue-450), `--fill-{role}-hover` (hue-400), `--bg-{role}` (hue-100 / dark hue-800), `--border-{role}` (solid hue-250 in light / hue-700 in dark), `--text-{role}` (600 fg). Warning's fill diverges: yellow-200 / hover yellow-250. Brand uses named `clay-emphasized` / hover `clay` (not hue stops).

| Role      | Hue    | Tokens                                                                                          |
| --------- | ------ | ----------------------------------------------------------------------------------------------- |
| `accent`  | blue   | `--fill-accent{,-hover}`, `--bg-accent`, `--border-accent`, `--text-accent`     |
| `brand`   | clay   | `--fill-brand{,-hover}`, `--on-brand` (fill-only — no text/bg/border)                   |
| `danger`  | red    | `--fill-danger{,-hover}`, `--bg-danger`, `--border-danger`, `--text-danger`     |
| `success` | green  | `--fill-success{,-hover}`, `--bg-success`, `--border-success`, `--text-success` |
| `warning` | yellow | `--fill-warning{,-hover}`, `--bg-warning`, `--border-warning`, `--text-warning` |
| `pro`     | purple | `--fill-pro{,-hover}`, `--bg-pro`, `--border-pro`, `--text-pro`                 |

#### `git-*` roles

Diff and PR/CR-state colors — `added`, `removed`, `modified`, `conflicting`, `merged`, `closed`, `draft`, plus `opened`/`queued` as aliases of `added`/`modified`. Each carries the full `text` / `fill{,-hover}` / `bg` / `border` / `on` suite. Values come from `@ant/epitaxy`'s `--extended-*` palette (not CDS ramp stops), so migrating claude.ai's diff UI onto these tokens is a rename; `fill` light is the Epitaxy hue darkened just enough for white `on-git-*` to pass AA.

### Background vs. fill

Both are backgrounds; the split is saturation, and therefore which foreground token pairs on top.

`bg-{role}` is the pale tint (hue-100 light / hue-800 dark) for passive status surfaces — Banner, Badge, chip. Light enough that `text-{role}` (hue-600) reads against it: a danger banner is `bg-danger` + `text-danger`. `fill-{role}` is the saturated solid (hue-450) for interactive controls — button, checkbox, toggle. Too dark for `text-{role}`, so it pairs with `on-{role}` (gray-0 / gray-900) instead; the 450 stop is chosen for WCAG contrast against `on-*`.

|       | Background    | Foreground    | Example       |
| ----- | ------------- | ------------- | ------------- |
| Tint  | `bg-{role}`   | `text-{role}` | Banner, Badge |
| Solid | `fill-{role}` | `on-{role}`   | Button        |

The token name encodes the pairing: use `bg-*` when the hue is ambient context behind body text; `fill-*` when the hue _is_ the control surface.

### Purpose tokens

| Token                        | Value (light)                                     | Use case                                         |
| ---------------------------- | ------------------------------------------------- | ------------------------------------------------ |
| `--text-primary`         | `neutral-900`                                     | Body text                                        |
| `--text-secondary`       | `neutral-600`                                     | Supporting text                                  |
| `--text-muted`           | `neutral-400`                                     | Placeholder, captions                            |
| `--text-disabled`        | `alpha-4`                                         | Disabled labels                                  |
| `--border`               | `alpha-2`                                         | Default 1px hairline                             |
| `--border-strong`        | `alpha-3`                                         | Emphasized divider                               |
| `--border-stronger`      | `neutral-900 / 40%`                               | Heavy divider                                    |
| `--fill-primary`         | `neutral-900`                                     | Primary button bg                                |
| `--fill-primary-hover`   | `neutral-750`                                     |                                                  |
| `--fill-secondary`       | `hsl(0 0% 100% / 0.1)`                            | Secondary button bg                              |
| `--fill-secondary-hover` | `alpha-1`                                         |                                                  |
| `--fill-secondary-ring`  | `border` (light) / transparent (dark)             | Secondary button ring                            |
| `--fill-field`           | `hsl(0 0% 100% / 0.5)` (light) / `alpha-1` (dark) | Field control bg (TextInput, TextArea, Combobox) |
| `--fill-field-ring`      | `border` (light + dark)                           | Field control resting ring                       |
| `--fill-ghost-hover`     | `alpha-1`                                         | Ghost button hover bg                            |
| `--fill-control`         | `alpha-2`                                         | Avatar fallback bg                               |
| `--fill-control-hover`   | `alpha-3`                                         |                                                  |
| `--fill-disabled`        | `alpha-1`                                         | Disabled control bg                              |
| `--on-primary`           | `neutral-0`                                       | Text on `fill-primary`                           |
| `--on-accent`            | `gray-0`                                          | Text on `accent`                                 |
| `--on-brand`             | `gray-0`                                          | Text on `brand`                                  |
| `--on-danger`            | `gray-0`                                          | Text on `danger`                                 |
| `--on-success`           | `gray-900`                                        | Text on `success`                                |
| `--on-warning`           | `gray-900`                                        | Text on `warning`                                |
| `--on-pro`               | `gray-0`                                          | Text on `pro`                                    |
| `--focus-shadow`         | `0 0 0 1px accent, 0 0 6px 1px bg-accent`         | `focus-visible` ring                             |
| `--shadow-sm`            | two-layer via `--shadow-color`                | Low elevation                                    |
| `--shadow-md`            | two-layer via `--shadow-color`                | Card / panel                                     |
| `--shadow-lg`            | two-layer via `--shadow-color`                | Dialog / sheet                                   |
| `--shadow-popover`       | `0 8px 24px /12%, 0 2px 6px /8%`                  | Menu, dropdown popups                            |
| `--surface-popover`      | `surface-3`                                       | Named alias                                      |
| `--surface-panel`        | `surface-2`                                       | Named alias                                      |

`--shadow-sm/md/lg` are two-layer composites (contact + diffused drop) driven by `--shadow-color`, which deepens to `black/24%` in dark mode (epitaxy parity). `--shadow-popover` is a fixed two-layer literal tuned for floating menus.

---

## CDS content

How to write the words that go inside cds components. Tokens decide how the UI _looks_; this decides how it _sounds_.

The voice is **intelligent, warm, unvarnished, and collaborative** — your smartest friend explaining something in plain terms. Friendly lives in the copy, not in extra chrome.

## Mechanics

- **Sentence case everywhere.** Buttons, headings, tabs, labels, menu items. "Save changes", not "Save Changes". Title Case is for proper nouns only (Claude, Opus, Anthropic Console).
- **No terminal punctuation on labels and headings.** Helper text, descriptions, and empty-state body copy _do_ end with a period.
- **Use contractions.** "Can't", "you'll", "it's". Conversational, not stiff.
- **Active voice, verb first.** "Delete project", not "Project deletion".
- **Ellipsis = in progress only.** "Claude is thinking…". Not for trailing off, not for menu suffixes.
- **No ampersands.** Spell out "and".
- **Serial comma.** "Chats, projects, and artifacts."

## Pronouns

UI speaks as the product, not as Claude and not as the user.

| Context          | Use               | Example                                                 |
| ---------------- | ----------------- | ------------------------------------------------------- |
| User's things    | **your**          | "Your projects" — never "My projects"                   |
| Confirmations    | none / past tense | "Saved", "Got it" — never "I saved it"                  |
| Errors           | **you / your**    | "Your session expired" — never "I couldn't…"            |
| Claude (in chat) | **I**             | Reserved for the chat surface; system UI never says "I" |

## Words to avoid

| Skip                                        | Why                                   | Instead          |
| ------------------------------------------- | ------------------------------------- | ---------------- |
| "successfully"                              | The success toast _is_ the success    | "File uploaded"  |
| "please"                                    | UI isn't asking a favor               | "Enter a name"   |
| "Click here" / "Tap to…"                    | Link text should name the destination | "Read the docs"  |
| "!" on system copy                          | Reads as shouty                       | "Settings saved" |
| "leverage", "seamless", "unlock", "empower" | Corporate filler                      | Say what it does |
| "simply", "just", "easy"                    | Presumes — and condescends            | Cut it           |

## Patterns

**Buttons / CTAs** — verb first, 1–3 words, sentence case, no punctuation. "Create project", "Upgrade to Pro". Not "OK", "Submit", or "Click to continue".

**Errors** — say what happened, then what to do. One sentence, no "Error:" prefix, no first person. "That name's already taken. Try another." Never surface raw exception strings.

**Empty states** — an invitation, not an apology. Headline names the space ("Start your first project"), one-line body explains it, CTA is a verb ("Create project"). Skip "Nothing here yet."

**Placeholders** — a real example of valid input ("name@company.com", "Summarize this document"). No "e.g." prefix, don't repeat the field label.

**Links** — describe where they go ("Learn more", "View pricing"). Keep them at the end of the sentence; punctuation sits outside the link.

## Do / Don't

| Do                                 | Don't                                  |
| ---------------------------------- | -------------------------------------- |
| "File uploaded"                    | "Your file was uploaded successfully!" |
| "Enter a workspace name"           | "Please enter a workspace name."       |
| "Couldn't connect to Slack. Retry" | "Error: I was unable to connect."      |
| "Your projects"                    | "My projects"                          |
| "Create project"                   | "Click Here To Get Started"            |
| "Connect Slack"                    | "Add the Slack Connector"              |


Do not overthink. Try to keep thinking below 500 tokens. If the visual is complex and requires more reasoning effort, consider creating an artifact instead.
````

</details>

Here's the full comparative rundown — first the at-a-glance cards, then the analysis underneath, including one important correction to what I said earlier about subscription auth.

> 🔧 **Tool call → `visualize:show_widget`** — Show widget

```json
{
  "loading_messages": [
    "Lining up the contenders",
    "Reading license fine print",
    "Auditing subscription loopholes"
  ],
  "title": "ai_factory_orchestrator_comparison",
  "widget_code": "<h2 class=\"sr-only\" style=\"position:absolute;width:1px;height:1px;overflow:hidden;clip:rect(0 0 0 0)\">Comparison of seven open-source AI coding factories and orchestrators by maturity, license, model support, and subscription-auth compatibility.</h2>\n<style>\n.grp{display:flex;align-items:center;gap:8px;margin:1.25rem 0 .5rem;font-size:13px;color:var(--text-secondary)}\n.grp i{font-size:18px}\n.card{background:var(--surface-2);border:0.5px solid var(--border);border-radius:12px;padding:.9rem 1rem;margin:0 0 10px}\n.hd{display:flex;align-items:baseline;justify-content:space-between;gap:8px;margin:0 0 2px}\n.nm{font-size:15px;font-weight:500;margin:0}\n.lic{font-family:var(--font-mono);font-size:11px;color:var(--text-secondary);background:var(--surface-1);border-radius:6px;padding:2px 7px;white-space:nowrap}\n.tag{font-size:13px;color:var(--text-secondary);margin:0 0 10px}\n.rw{display:flex;gap:10px;font-size:13px;padding:3px 0}\n.rl{color:var(--text-muted);font-size:12px;min-width:62px;padding-top:1px}\n.rv{color:var(--text-primary)}\n.pill{display:inline-block;font-size:12px;border-radius:6px;padding:3px 8px}\n.ok{background:var(--bg-success);color:var(--text-success)}\n.mx{background:var(--bg-warning);color:var(--text-warning)}\n.na{background:var(--surface-1);color:var(--text-secondary)}\n</style>\n<div class=\"grp\"><i class=\"ti ti-sitemap\" aria-hidden=\"true\"></i>Workflow factories — gated pipelines</div>\n<div class=\"card\">\n  <div class=\"hd\"><p class=\"nm\">Fabro</p><span class=\"lic\">MIT</span></div>\n  <p class=\"tag\">Graph-defined pipelines with sandboxes, human gates, verification</p>\n  <div class=\"rw\"><span class=\"rl\">Maturity</span><span class=\"rv\">Public Mar '26 · near-daily releases · single vendor (Qlty)</span></div>\n  <div class=\"rw\"><span class=\"rl\">Models</span><span class=\"rv\">Anthropic, OpenAI, Gemini native + OpenRouter, LiteLLM, Bedrock, Ollama; per-node routing and failover</span></div>\n  <div class=\"rw\"><span class=\"rl\">Subs</span><span><span class=\"pill mx\">API keys native · subscriptions via ACP nodes</span></span></div>\n</div>\n<div class=\"card\">\n  <div class=\"hd\"><p class=\"nm\">Archon</p><span class=\"lic\">MIT</span></div>\n  <p class=\"tag\">YAML dev workflows over agent SDKs, driven from Slack, web, or CLI</p>\n  <div class=\"rw\"><span class=\"rl\">Maturity</span><span class=\"rv\">Full rewrite Apr '26 · 13.8k★ community · fast-moving, high churn</span></div>\n  <div class=\"rw\"><span class=\"rl\">Models</span><span class=\"rv\">Claude Agent SDK + Codex SDK built in; Gemini and others via Pi, OpenCode, Copilot providers</span></div>\n  <div class=\"rw\"><span class=\"rl\">Subs</span><span><span class=\"pill mx\">Codex on ChatGPT plan OK · Claude leg needs API key</span></span></div>\n</div>\n<div class=\"card\">\n  <div class=\"hd\"><p class=\"nm\">Swamp</p><span class=\"lic\">AGPL-3.0 + exc.</span></div>\n  <p class=\"tag\">Deterministic automation framework that your coding agent operates</p>\n  <div class=\"rw\"><span class=\"rl\">Maturity</span><span class=\"rv\">Launched early '26 · heavily dogfooded · employee-only development</span></div>\n  <div class=\"rw\"><span class=\"rl\">Models</span><span class=\"rv\">Agent-agnostic: Claude Code, Codex, Cursor, OpenCode drive it; no LLM calls of its own</span></div>\n  <div class=\"rw\"><span class=\"rl\">Subs</span><span><span class=\"pill ok\">Inherits your CLI's login — subscriptions fine</span></span></div>\n</div>\n<div class=\"grp\"><i class=\"ti ti-terminal-2\" aria-hidden=\"true\"></i>Session orchestrators — parallel CLIs</div>\n<div class=\"card\">\n  <div class=\"hd\"><p class=\"nm\">Vibe Kanban</p><span class=\"lic\">Apache-2.0</span></div>\n  <p class=\"tag\">Kanban board over parallel agent CLIs, one worktree per task</p>\n  <div class=\"rw\"><span class=\"rl\">Maturity</span><span class=\"rv\">27.5k★ · community-run since Bloop shut down Apr '26 · going fully local</span></div>\n  <div class=\"rw\"><span class=\"rl\">Models</span><span class=\"rv\">10+ agents: Claude Code, Codex, Gemini CLI, Amp, Cursor, OpenCode…</span></div>\n  <div class=\"rw\"><span class=\"rl\">Subs</span><span><span class=\"pill ok\">Spawns official CLIs — subscription-native</span></span></div>\n</div>\n<div class=\"card\">\n  <div class=\"hd\"><p class=\"nm\">cmux</p><span class=\"lic\">AGPL-3.0</span></div>\n  <p class=\"tag\">Native macOS terminal built for running agents in parallel</p>\n  <div class=\"rw\"><span class=\"rl\">Maturity</span><span class=\"rv\">Jan '26 launch · rapid growth · active vendor (Manaflow) · macOS only</span></div>\n  <div class=\"rw\"><span class=\"rl\">Models</span><span class=\"rv\">Any CLI: Claude Code, Codex, Gemini, OpenCode, Pi, Amp, Copilot…</span></div>\n  <div class=\"rw\"><span class=\"rl\">Subs</span><span><span class=\"pill ok\">CLIs own their auth — subscription-native</span></span></div>\n</div>\n<div class=\"grp\"><i class=\"ti ti-puzzle\" aria-hidden=\"true\"></i>Adjacent</div>\n<div class=\"card\">\n  <div class=\"hd\"><p class=\"nm\">human (gethuman.sh)</p><span class=\"lic\">MIT</span></div>\n  <p class=\"tag\">Connector CLI + devcontainer security rig around Claude Code</p>\n  <div class=\"rw\"><span class=\"rl\">Maturity</span><span class=\"rv\">~33★ · single maintainer · very early</span></div>\n  <div class=\"rw\"><span class=\"rl\">Models</span><span class=\"rv\">Claude Code-centric; works alongside any agent as a plain CLI</span></div>\n  <div class=\"rw\"><span class=\"rl\">Subs</span><span><span class=\"pill ok\">Rides Claude Code's own login</span></span></div>\n</div>\n<div class=\"card\">\n  <div class=\"hd\"><p class=\"nm\">owainlewis/factory</p><span class=\"lic\">MIT</span></div>\n  <p class=\"tag\">V1 local runner spine for repo-owned agent goals</p>\n  <div class=\"rw\"><span class=\"rl\">Maturity</span><span class=\"rv\">0★ · 10 commits · explicit v1 experiment</span></div>\n  <div class=\"rw\"><span class=\"rl\">Models</span><span class=\"rv\">Claude Code as the only adapter</span></div>\n  <div class=\"rw\"><span class=\"rl\">Subs</span><span><span class=\"pill na\">Skip for prod</span></span></div>\n</div>"
}
```

<details>
<summary>🧰 Result ← `visualize:show_widget` (2 items)</summary>

```
Content rendered and shown to the user. Please do not duplicate the shown content in text because it's already visually represented.
```

```
[This tool call rendered an interactive widget in the chat. The user can already see the result — do not repeat it in text or with another visualization tool.]
```

</details>

Start with the finding that reframes everything, and a correction to my first answer: I said Archon's SDK approach "piggybacks subscription auth naturally" — that's now only half true. In February 2026 Anthropic updated its legal and compliance docs to state that the Agent SDK requires API-key authentication, and that OAuth tokens from Free/Pro/Max subscriptions may not be used outside Claude Code and Claude.ai — third parties can no longer offer Claude.ai login or route requests on user subscription credentials. There's an open issue on the Agent SDK repo asking Anthropic to support Max-plan billing precisely because of this barrier. Meanwhile, running Claude Code itself on a Pro/Max plan remains fully supported (just make sure no ANTHROPIC_API_KEY is set, or it silently bills the API instead). OpenAI and Google are looser: Codex-style subscription piggybacking via ChatGPT login is an established pattern, and Codex and Gemini CLI both sign in against their respective subscriptions rather than API credits. So the real dividing line in this whole category is architectural: tools that *spawn the official CLIs* inherit subscription billing legitimately; tools with *their own LLM runtime* put at least the Claude leg on API keys.

Among the factories, that logic plays out like this. Fabro has the strongest engineering — Rust single binary, sandboxed agents, deterministic verification gates, Git-checkpointed stages, model routing with automatic failover — but its default runtime calls provider APIs with per-provider keys, so the Claude leg of a Fabro pipeline is API-billed. Its escape hatch is real, though: ACP-backend nodes run an external agent process inside Fabro's sandbox where the command owns its own login and credentials, at the cost of Fabro-managed failover and sub-agents on those nodes. That means you can put `claude`, `codex`, and `gemini` on subscription auth inside an otherwise deterministic Fabro graph. Maturity-wise it's four months old in public but shipping at a pace almost nothing else matches, from a founder with a long infrastructure track record; the tradeoff is a single vendor and an issue-only contribution model.

Archon is the community bet. The April 2026 rewrite kept the 13.8k-star community while replacing the codebase entirely, and its most mature surface today is agentic coding — Claude Code SDK and Codex SDK steps with approval gates and audit trails, drivable from Slack, Telegram, GitHub, Discord, web, or CLI. Post-policy, the honest read on subscriptions: the Codex leg rides your ChatGPT Pro plan cleanly; the Claude leg, going through the Agent SDK, officially needs an API key; and Gemini arrives only via the Pi provider on the roadmap-to-multi-model path, which is an API-key harness. Swamp inverts the whole model — your agent (Claude Code, Cursor, OpenCode, Codex) operates Swamp rather than Swamp calling models, which makes it the cleanest subscription story of the factories, and their dogfooded issue lifecycle (state machine, versioned plans, adversarial reviews, gated transitions) is genuinely the "dark factory" discipline in practice. But it's general automation more than a code-shipping pipeline, it's AGPL-3.0 with a custom exception, and only employees write the code.

The session orchestrators are the most battle-tested way to burn three $200 plans in parallel, because they do nothing clever with auth at all — the CLIs keep their own logins. Vibe Kanban and its peers explicitly run on your API keys or agent subscriptions, and it supports ten-plus agents with worktree-per-task isolation and in-board diff review. The risk is stewardship: Bloop shut down in April 2026, remote services were removed, and the project is now community-maintained on a fully local architecture — fine for a tool this simple, but nobody's on the hook for it. cmux is the actively-developed alternative with a vendor behind it: a native Swift/AppKit terminal on libghostty that launched in January 2026 and grew fast, agent-agnostic, scriptable — but macOS-only and, like Swamp, AGPL, which is irrelevant for internal use but matters if you'd ever modify and redistribute or offer it as a service. Neither gives you gates, verification, or workflow determinism; they give you throughput and visibility.

The adjacent pair: human is best understood as hardening and connectors you bolt onto whichever factory you pick — credential isolation so the agent never sees tokens, an outbound firewall/proxy in the devcontainer, and lifecycle skills including an autonomous bug-fix pipeline — valuable ideas, but at ~33 stars with one maintainer, vendor it in with eyes open. owainlewis/factory is a public learning artifact, not a product.

If I compress all of that into a decision: for a production factory that maximizes your subscriptions, the strongest current combination is Fabro's workflow engine with ACP nodes running the three official CLIs — you keep deterministic gates, sandboxes, and verification while billing lands on the plans; accept that those nodes lose Fabro's failover. If your team is Claude/Codex-centric and wants community velocity over polish, Archon works with Codex on ChatGPT auth plus an Anthropic API-key budget for the Claude steps. If your ambition is broader automation with the agent in the driver's seat and AGPL is acceptable, Swamp is the most architecturally honest subscription play. And if "mature and usable" outweighs "factory" this quarter, cmux (or community Vibe Kanban) plus disciplined AGENTS.md conventions and CI gates is the boring option that works today. Whatever you choose, the category-wide caveats stand: everything here is under a year old, so pin versions, keep human approval on merges, sandbox execution, and re-check the auth terms periodically — the Anthropic policy change in February is proof that the subscription ground can shift under a running pipeline.

> **Citations:**
> - [Is This Allowed? Claude Code Terms of Service Explained – autonomee.ai](https://autonomee.ai/blog/claude-code-terms-of-service-explained/)
> - [Anthropic officially bans using subscription authentication for third-party Claude use](https://alternativeto.net/news/2026/2/anthropic-officially-bans-using-subscription-authentication-for-third-party-claude-use)
> - [Agent SDK should support Max plan billing, not just API keys · Issue #559 · anthropics/claude-agent-sdk-python](https://github.com/anthropics/claude-agent-sdk-python/issues/559)
> - [Use Claude Code with your Pro or Max plan | Claude Help Center](https://support.claude.com/en/articles/11145838-use-claude-code-with-your-pro-or-max-plan)
> - [5 Claude Code Alternatives in 2026](https://www.builder.io/blog/claude-code-alternatives)
> - [Claude Code Orchestrator Setup Guide - Multi-agent workflow with Codex (writer), Gemini (auditor), and Nanobanana (image generation) · GitHub](https://gist.github.com/bjornmage/ddd6dc7f4d5e074af1db44964d377427)
> - [GitHub - fabro-sh/fabro: ⚒️ The open source dark software factory for expert engineers.](https://github.com/fabro-sh/fabro)
> - [Fabro — The Dark Software Factory](https://fabro.sh/)
> - [fabro/README.md at main · fabro-sh/fabro](https://github.com/fabro-sh/fabro/blob/main/README.md)
> - [Open source Archon: migrate new codebase to coleam00/Archon · Issue #952 · coleam00/Archon](https://github.com/coleam00/Archon/issues/952)
> - [Archon/CLAUDE.md at dev · coleam00/Archon](https://github.com/coleam00/Archon/blob/dev/CLAUDE.md)
> - [Roadmap — Archon](https://archon.diy/roadmap/)
> - [Swamp Club · GitHub](https://github.com/swamp-club)
> - [The Lifecycle of a Swamp Issue](https://stack72.dev/the-lifecycle-of-a-swamp-issue/)
> - [Swamp Club · GitHub](https://github.com/swamp-club)
> - [Parallel Code vs Vibe Kanban: Native App Alternative (2026)](https://parallelcode.app/compare/parallel-code-vs-vibe-kanban/)
> - [9 Open-Source Agent Orchestrators for AI Coding (2026) | Augment Code](https://www.augmentcode.com/tools/open-source-agent-orchestrators)
> - [VibeKanban - Shutdown](https://www.vibekanban.com/blog/shutdown)
> - [GitHub - manaflow-ai/cmux: Open source Ghostty-based macOS terminal with vertical tabs and notifications for AI coding agents. Built for multitasking, organization, and programmability. · GitHub](https://github.com/manaflow-ai/cmux)
> - [cmux: a purpose-built terminal for the parallel agent workflow - ddewhurst](https://ddewhurst.com/blog/cmux-purpose-built-terminal-for-parallel-agent-workflow/)
> - [human - The AI dev rig for AI coding agents](https://gethuman.sh/)

---
