# Instructions for AI agents

This repository is a vendor-neutral design skill. It is plain Markdown and works with any model, agent or IDE.

When asked to generate, review or fix a user interface:

1. Read `SKILL.md` and follow its 20 rules.
2. For a fast review, use `CHEATSHEET.md`.
3. For rationale, examples and edge cases, read `references/rules.md` and `examples/before-after.md`.

Non-negotiable guardrails:

- Accessibility is a floor, not a trade-off: contrast, focus states, hit targets and reduced motion.
- Preserve brand identity; unslop means removing noise, not personality.
- Never invent product facts, metrics or testimonials to make copy specific.
- Fix hierarchy and contrast before decoration.
- Prefer the smallest change that passes the rule.

Output contract for reviews: score out of 20, verdict, then violations ordered by impact with a one-line fix each.
