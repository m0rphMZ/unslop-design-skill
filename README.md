# Unslop Design

A vendor-neutral skill that teaches AI models to remove "AI slop" from interface designs. 20 rules, one 40-second pass, plain Markdown.

## Structure

```text
.
├── README.md
├── LICENSE
└── unslop-design/
    ├── SKILL.md
    ├── checklist.md
    ├── rules.md
    └── examples.md
```

`SKILL.md` is the entry point. The other three are references it points to: a fast checklist, the expanded rules, and before/after examples.

## Use it

Copy the `unslop-design` folder into your skills directory:

```text
~/.claude/skills/unslop-design/
~/.config/opencode/skills/unslop-design/
.opencode/skills/unslop-design/
```

For models without skill support, paste `unslop-design/SKILL.md` into the system prompt or the start of a conversation.

## The 20 rules

1. Delete filler badges
2. Drop redundant labels
3. Unitalicize random words
4. Mono only where needed
5. Use a design system
6. Show the actual product
7. Enlarge the main feature
8. Group with spacing
9. Make headlines specific
10. Emphasize the CTA
11. Add an accent colour
12. Keep icons consistent
13. Remove embellishments
14. Inner radius = outer − padding
15. Improve text contrast
16. Wrap headlines properly
17. Align by eye, not pixels
18. Use tabular nums
19. Add loading states
20. Animate useful feedback

## License

MIT
