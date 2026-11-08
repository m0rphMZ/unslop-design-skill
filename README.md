# Unslop Design Skill

Make AI-generated interfaces look designed, not generated.

A vendor-neutral skill that teaches any AI model to remove the filler badges, vague headlines, decorative gradients, inconsistent icons and template sameness that make UI look like "AI slop".

Plain Markdown. No SDK, no dependencies, no vendor lock-in. If a model can read instructions, it can use this.

> **20 ways to unslop AI designs. In under 40 seconds.**

## The 20 rules

| # | Rule | One-line fix |
|---|---|---|
| 1 | Delete filler badges | Keep only badges that change a decision |
| 2 | Drop redundant labels | One label per control, one heading per section |
| 3 | Unitalicize random words | Italics for emphasis, not decoration |
| 4 | Mono only where needed | Code, IDs and data — never headlines |
| 5 | Use a design system | Every value comes from a token |
| 6 | Show the actual product | Real UI, not abstract illustration |
| 7 | Enlarge the main feature | One dominant element per view |
| 8 | Group with spacing | Proximity before borders |
| 9 | Make headlines specific | Concrete outcome, not vague promise |
| 10 | Emphasize the CTA | Exactly one primary action |
| 11 | Add an accent colour | One accent for action and state |
| 12 | Keep icons consistent | One family, one weight, one size |
| 13 | Remove embellishments | If it doesn't inform, delete it |
| 14 | Inner radius = outer − padding | Nested corners stay concentric |
| 15 | Improve text contrast | Body text at least 4.5:1 |
| 16 | Wrap headlines properly | No orphans, no single-word last lines |
| 17 | Align by eye, not pixels | Optical centering beats math |
| 18 | Use tabular nums | Numbers must not jitter |
| 19 | Add loading states | Never leave a slow action silent |
| 20 | Animate useful feedback | Motion explains cause and effect |

## Use it with any model

### Skill / agent runtimes

Copy this folder into the runtime's skills directory, named `unslop-design`:

```text
# Claude Code / Claude apps
~/.claude/skills/unslop-design/

# OpenCode (global or project)
~/.config/opencode/skills/unslop-design/
.opencode/skills/unslop-design/
```

The frontmatter in `SKILL.md` (`name`, `description`) is compatible with the Agent Skills convention used by Claude, OpenCode and other skill-aware runtimes.

### Coding agents without a skill loader

Keep `AGENTS.md` in the project root, or append its contents to the agent's rules file. Codex, Cursor, Windsurf, Copilot and similar agents read it automatically or on request.

### Chat models (ChatGPT, Gemini, Copilot, local models)

Paste `prompts/system-prompt.md` into custom instructions, a project, or the start of a conversation. Then share the UI, screenshot or code you want reviewed.

### Any API

Send `prompts/system-prompt.md` as the system message. Add `references/rules.md` when you want the model to reason about edge cases.

### Fastest possible use

Paste this before your design prompt:

```text
Read CHEATSHEET.md and apply all 20 checks to the UI you are about to generate.
```

## The 40-second pass

| Phase | Time | Rules | Question |
|---|---|---|---|
| Structure | 10s | 1–4 | Is every element carrying information? |
| Hierarchy | 10s | 6–11 | Can I tell what matters in one glance? |
| Craft | 10s | 12–17 | Does it look made by a careful human? |
| Behaviour | 10s | 18–20 | Is it honest about state and feedback? |

Score one point per rule. Ship at **18/20**; public or hero surfaces should reach **20/20**.

## What's inside

```text
.
├── SKILL.md                  # The skill: frontmatter + 20 rules + audit workflow
├── CHEATSHEET.md             # One-screen checklist for the 40-second pass
├── AGENTS.md                 # Drop-in instructions for coding agents
├── prompts/
│   └── system-prompt.md      # Paste-anywhere prompt for any chat model
├── references/
│   └── rules.md              # Expanded rationale, examples and acceptance tests
├── examples/
│   └── before-after.md       # Concrete before/after fixes
└── LICENSE                   # MIT
```

## Design stance

- Specific beats decorative.
- Hierarchy beats variety.
- Real product beats abstract art.
- Feedback beats flourish.
- Restraint is a style.

If removing an element loses no information and changes no decision, remove it.

## License

MIT. Use it, fork it, ship it, teach it.
