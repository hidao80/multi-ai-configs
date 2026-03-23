# multi-ai-configs

This repository centralizes configuration files and project guidance shared across multiple AI coding agents.

It currently targets `Claude`, `Codex`, and `Gemini`, with a minimal structure designed to reuse the same instructions whenever possible.

## :dart: Purpose

- Centralize project instructions that would otherwise be scattered across agents
- Update shared rules in one place and reduce the cost of propagating changes to each tool
- Serve as a template when adding support for new AI tools

## :building_construction: Structure

```text
.
├─ .claude/
│  └─ CLAUDE.md
├─ .codex/
│  └─ config.toml
├─ .gemini/
│  └─ GEMINI.md
└─ README.md
```

## :busts_in_silhouette: File Roles

### `.claude/CLAUDE.md`

This is the shared project guide.  
In this repository, it is treated as the primary source of truth.

### `.gemini/GEMINI.md`

This is a thin wrapper that only references `@.claude/CLAUDE.md`.  
It allows Gemini to reuse the same guidance written for Claude.

### `.codex/config.toml`

This file points Codex to `.claude/CLAUDE.md` as its fallback project document.  
If you need more Codex-specific settings later, this file can be extended.

## :green_book: Usage

1. Write shared rules in `.claude/CLAUDE.md`.
2. Reference or reuse those rules from each agent-specific configuration file.
3. Add tool-specific differences only when they are actually needed.

## :judge: Maintenance Policy

- Prefer expanding shared rules first to avoid duplicated guidance
- Keep tool-specific configuration to a minimum
- If files are moved, update all references together so the linkage does not break
- If operational rules or templates grow larger, move them into something like `docs/`

## :handshake: Contributing

Bug reports and pull requests are welcome.

## :page_facing_up: License

MIT
