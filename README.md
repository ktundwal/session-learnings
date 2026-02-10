# session-learnings

A [Claude Code skill](https://docs.anthropic.com/en/docs/claude-code) that captures knowledge from AI coding sessions as portable, searchable artifacts.

## Why

AI chat sessions are write-only storage. The debugging strategies, failed approaches, and breakthroughs from a productive session disappear when the window closes. This skill extracts that knowledge into durable artifacts before it's lost.

Inspired by [Stop Losing Memory from Your AI Coding Sessions](https://www.linkedin.com/pulse/stop-losing-memory-from-your-ai-coding-sessions-simple-tundwal-ikflc/) and battle-tested on a [multi-agent memory leak investigation](https://github.com/ktundwal/session-learnings#example) across two Microsoft repos.

## What It Produces

| Artifact | Purpose |
|----------|---------|
| `README.md` | Quick reference: date, tags, status, summary |
| `investigation-log.md` | Step-by-step decisions, dead ends, what worked/didn't |
| `chat-transcript.md` | Session conversation as readable narrative |
| `deck.md` + `deck.pptx` + `deck.html` | Presentation deck for sharing with your team |
| `MEMORY.md` update | Learnings fed back into Claude Code's auto-memory |

All artifacts are **plain markdown** — portable across tools, machines, and AI assistants.

## Install

### Per-project (shared with team via version control)

```bash
mkdir -p .claude/skills
git clone https://github.com/ktundwal/session-learnings .claude/skills/session-learnings
```

### Personal (available in all projects)

```bash
git clone https://github.com/ktundwal/session-learnings ~/.claude/skills/session-learnings
```

## Usage

At the end of a productive AI session in Claude Code:

```
/session-learnings mem-leak-fix
```

The skill will:
1. Scan the session for findings, decisions, and dead ends
2. Ask where to save artifacts (default: `~/ai-session-learnings/2026-02-09-mem-leak-fix/`)
3. Generate README, investigation log, and chat transcript
4. Offer cross-model review via [`/crossmodel-review`](https://github.com/ktundwal/crossmodel-review) (optional, recommended)
5. Generate a Marp presentation deck using [`presentation-skills`](https://github.com/ktundwal/presentation-skills) templates
6. Export deck to PPTX + HTML
7. Update your project's MEMORY.md with new learnings

## Dependencies

| Dependency | Required? | Auto-handled? |
|-----------|-----------|---------------|
| [Marp CLI](https://github.com/marp-team/marp-cli) | Yes (for deck) | Auto-installs via npm |
| [presentation-skills](https://github.com/ktundwal/presentation-skills) | Yes (for deck templates) | Auto-clones if missing |
| [crossmodel-review](https://github.com/ktundwal/crossmodel-review) | No (optional) | Nudges user if available |

## Templates

The `templates/` directory contains blank templates for manual use outside the skill:

- `context-template.md` — Brief for starting an AI investigation session
- `investigation-log-template.md` — Structure for documenting investigations
- `hypothesis-template.md` — Formal hypothesis document for cross-model review

## Philosophy

- **Dead ends are valuable** — What didn't work saves future time
- **Plain markdown is portable** — No lock-in to any tool or platform
- **Every session is an asset** — Learnings compound across sessions via MEMORY.md
- **Decks spread knowledge** — A presentation-ready summary makes it easy to share with your team

## Related Skills

- [`crossmodel-review`](https://github.com/ktundwal/crossmodel-review) — Get independent review from GPT and Gemini
- [`presentation-skills`](https://github.com/ktundwal/presentation-skills) — Marp deck creation with visual QA
- `ai-investigate` (coming soon) — Multi-agent debugging playbook

## License

MIT
