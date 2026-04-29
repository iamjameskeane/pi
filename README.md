# Pi Coding Agent Config

Personal configuration backup for [Pi Coding Agent](https://github.com/mariozechner/pi-coding-agent).

## What's backed up

- **Agent settings** — default model, provider, thinking level, installed packages, theme
- **Taskplane preferences** — default agent thinking levels for workers/reviewers/mergers
- **Supervisor template** — project-specific supervisor rules (currently empty)

## What's NOT backed up (and why)

| Ignored           | Reason                                            |
| ----------------- | ------------------------------------------------- |
| `agent/auth.json` | **Contains API keys** — you must add your own     |
| `agent/sessions/` | Chat history — personal, regenerable              |
| `agent/bin/`      | Downloaded binaries (`fd`, `rg`) — auto-installed |
| `.pi-lens/`       | Transient LLM cache — auto-populated              |

## Usage

1. Clone this repo to `~/.pi` (or your `PI_CODING_AGENT_DIR`):

   ```bash
   git clone <this-repo> ~/.pi
   ```

2. Add your API key(s):

   ```bash
   pi agent auth add openrouter <your-key>
   # or manually create ~/.pi/agent/auth.json
   ```

3. Install pi packages (if on a fresh machine):
   ```bash
   pi install pi-subagents taskplane pi-lens pi-mcp-adapter
   ```

## Current defaults

- **Provider:** OpenRouter
- **Model:** `moonshotai/kimi-k2.6`
- **Thinking:** Medium (interactive), High (taskplane agents)
- **Theme:** Default
- **Packages:** `pi-subagents`, `taskplane`, `pi-lens`, `pi-mcp-adapter`
