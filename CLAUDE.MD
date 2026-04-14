# Claude Code — Project Instructions

This repository is a personal reference and config collection for **Claude Code** — Anthropic's agentic CLI coding tool.

## Project Overview

- Slash commands, hooks, and `CLAUDE.md` templates
- `settings.json` examples with permission configs
- Custom skill templates for reusable workflows

## Key Commands

```bash
# Start a session
claude

# Non-interactive one-shot
claude -p "your prompt here"

# Use a specific model
claude --model claude-opus-4-20250514

# Auto-accept all edits
claude --permission-mode acceptEdits
```

## Slash Commands in This Repo

| Command       | File                          | Purpose                        |
|---------------|-------------------------------|--------------------------------|
| `/review`     | `.claude/commands/review.md`  | Code review before PR          |
| `/explain`    | `.claude/commands/explain.md` | Explain selected code          |
| `/commit`     | `.claude/commands/commit.md`  | Generate a git commit message  |

## Hooks

Hooks live in `.claude/settings.json` under the `hooks` key.

- `PostToolUse` → runs after Claude writes a file (e.g. auto-format with Prettier)
- `PreToolUse` → runs before Claude makes an edit (e.g. lint check)

## Notes

- Keep `.env` files in `permissions.deny` — never let Claude read secrets
- `CLAUDE.md` at root = global instructions; nested `CLAUDE.md` = folder-scoped
- Skills (`.claude/skills/`) are the modern replacement for `.claude/commands/`
