# Codex CLI headless mode — ChatGPT session transcript

**Source:** https://chatgpt.com/share/6a660498-80ac-83e8-b7b6-8340779bd427  
**Model:** gpt-5-6-pro · **Shared:** 2026-07-26 12:59 UTC · **User prompts:** 1

> Full dump of the shared ChatGPT session. Assistant reasoning summaries are kept as blockquotes; `web.run` blocks are the assistant's web-search/browse tool calls. Tool outputs are redacted by ChatGPT's share mechanism and omitted. Citation markers are converted to inline links.


---

## 👤 User

with claude code cli I can run it in param mode headless like claude -p "prompt"
can I do the same thing with codex cli ?


## 🤖 Assistant

> 🔍 **Tool call → `web.run`**

```json
{
  "search_query": [
    {
      "q": "site:developers.openai.com codex cli headless non-interactive exec prompt"
    },
    {
      "q": "site:openai.com codex cli exec non-interactive"
    },
    {
      "q": "site:help.openai.com Codex CLI non-interactive exec"
    }
  ],
  "response_length": "long"
}
```

> 💭 **Searched 7 websites**

*Yes—the equivalent exists. I’m checking the current flags and automation behavior to provide exact command patterns for scripts and CI runners.*

> 💭 **Explaining Codex CLI**
> Yes, I’m mapping the automation pattern to Codex CLI: use `codex exec "prompt"` for noninteractive runs, optionally pipe input, choose an appropriate sandbox, and use JSON output for machine-readable results. Authentication still needs configuring for CI.

> 💭 **Explained Codex CLI**

*Worked for 3m 32s*

Yes. The Codex CLI equivalent of Claude Code’s:

```bash
claude -p "prompt"
```

is:

```bash
codex exec "prompt"
```

There is also a shorter alias:

```bash
codex e "prompt"
```

`codex exec` is Codex’s non-interactive/headless mode, intended for scripts, workers, and CI jobs. It exits when the task finishes. ([ChatGPT Learn](https://learn.chatgpt.com/codex/developer-commands?surface=cli))

### Basic examples

Read/analyze the repository:

```bash
codex exec "Inspect this repository and identify the five highest-risk areas."
```

Allow Codex to edit files inside the workspace:

```bash
codex exec \
  --sandbox workspace-write \
  "Implement the requested feature, run the tests, and fix any failures."
```

Run against a specific checkout:

```bash
codex exec \
  --cd /srv/factory/worktrees/TICKET-123 \
  --sandbox workspace-write \
  "Implement ticket TICKET-123 according to the specification in ticket.md."
```

For unattended local work, OpenAI recommends `workspace-write`; unrestricted access should be reserved for an externally isolated runner or VM. ([ChatGPT Learn](https://learn.chatgpt.com/codex/non-interactive-mode))

### Capture the answer

Codex sends progress information to `stderr` and the final agent response to `stdout`, so ordinary shell capture works:

```bash
result="$(codex exec "Review the current changes and summarize them.")"
echo "$result"
```

Or write the final response to a file:

```bash
codex exec \
  --output-last-message result.md \
  "Implement the feature and summarize what changed."
```

The final message is still printed to `stdout` when `--output-last-message` is used. ([ChatGPT Learn](https://learn.chatgpt.com/codex/non-interactive-mode))

### Machine-readable event stream

For your factory dispatcher/worker, JSONL output will probably be more useful:

```bash
codex exec \
  --cd "$WORKTREE" \
  --sandbox workspace-write \
  --json \
  --output-last-message "$JOB_DIR/final-message.md" \
  "$PROMPT" \
  > "$JOB_DIR/events.jsonl" \
  2> "$JOB_DIR/stderr.log"
```

`--json` emits events such as thread start, command execution, file changes, agent messages, completion, failure, token usage, and errors. ([ChatGPT Learn](https://learn.chatgpt.com/codex/non-interactive-mode))

You could monitor it like:

```bash
codex exec --json "Run all tests and diagnose failures." |
  jq -c 'select(
    .type == "item.completed" or
    .type == "turn.completed" or
    .type == "turn.failed" or
    .type == "error"
  )'
```

### Long prompts through stdin

Codex accepts `-` to read the prompt from stdin:

```bash
cat prompt.md | codex exec -
```

Or:

```bash
codex exec --sandbox workspace-write - <<'PROMPT'
Implement ticket TICKET-123.

Requirements:
- Add the endpoint.
- Add unit and integration tests.
- Run the complete test suite.
- Do not modify unrelated files.
- Finish with a concise implementation summary.
PROMPT
```

You can also supply an instruction argument while piping additional context:

```bash
cat ticket.json |
  codex exec --sandbox workspace-write \
  "Implement the ticket described in the input JSON."
```

When both are provided, the argument is treated as the instruction and stdin as additional context. ([ChatGPT Learn](https://learn.chatgpt.com/codex/developer-commands?surface=cli))

### Useful for disposable workers

```bash
codex exec \
  --ephemeral \
  --cd "$WORKTREE" \
  --sandbox workspace-write \
  --json \
  "$PROMPT"
```

`--ephemeral` prevents Codex from persisting session rollout files. Without it, you can resume a previous headless run:

```bash
codex exec "Review the implementation for race conditions."

codex exec resume --last \
  "Fix the race conditions you identified and rerun the tests."
```

([ChatGPT Learn](https://learn.chatgpt.com/codex/developer-commands?surface=cli))

One important difference: **do not use `codex -p "prompt"`**. In Codex, `-p` means **profile**, not headless prompt mode. Use `codex exec` instead. ([ChatGPT Learn](https://learn.chatgpt.com/codex/developer-commands?surface=cli))

