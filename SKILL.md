---
name: unslop-design
description: Remove "AI slop" from UI designs with 20 fast, concrete rules. Use when generating or reviewing a web or app interface, or when a design looks generic, over-decorated, or template-like.
---

# Unslop Design

A followable procedure for making AI-generated interfaces look intentional. It works on screenshots, live pages, components or code. It does not require a specific tool, framework or model.

## When to use

- Generating any UI: landing page, dashboard, settings screen, empty state, form, modal.
- Reviewing a design that feels generic, busy, over-decorated or "AI-made".
- Fixing typography, spacing, hierarchy, colour, icons, states or motion.
- A user says "make it less generic", "this looks like AI", "polish this", or "unslop it".

## When not to use

- The user explicitly wants a deliberately playful, maximalist or branded kitsch style. Apply the structural rules, skip the restraint rules.
- You are being asked about backend behaviour, data model or copy strategy only.

## Core principle

Every element must earn its place.

Ask of each badge, label, icon, divider, gradient and animation: *if I delete this, does the user lose information or a possible action?* If no, delete it.

## The 40-second pass

Do not redesign everything. Scan in four phases and fix in order of impact.

| Phase | Rules | Look for |
|---|---|---|
| Structure (10s) | 1–4 | Meaningless badges, duplicated labels, decorative italics, wrong font family |
| Hierarchy (10s) | 6–11 | No product shown, no dominant element, weak grouping, vague headline, competing CTAs, grey-on-grey palette |
| Craft (10s) | 12–17 | Mixed icon styles, decoration, pinched nested corners, low contrast, bad line breaks, optical misalignment |
| Behaviour (10s) | 18–20 | Jittering numbers, silent waits, decoration-only motion |

## The 20 rules

Each rule has an acceptance test. A check either passes or fails; "mostly" is a fail.

### 1. Delete filler badges

Keep badges only when they change a decision or convey real state: `Beta`, `Deprecated`, `Required`, `Failed`, `3 unread`, `Pro`. Delete `New`, `Fast`, `Secure`, `AI-powered`, `Smart`, `Modern` and every pill used as decoration.

**Test:** remove the badge. Does any decision change? If not, delete it.

### 2. Drop redundant labels

One label per control, one heading per section. Do not stack an icon, a label, a placeholder and helper text that all say the same thing. Do not label the obvious (`Email` above an email field is fine; `Email` inside the field and again below adds no information).

**Test:** does the user need the second label to complete the action? If not, cut it.

### 3. Unitalicize random words

Italics are for titles of works, genuine emphasis and foreign terms. AI-generated copy often italicizes one word per sentence as a style crutch. Build hierarchy with size, weight and colour instead.

**Test:** remove the italic. If the meaning is unchanged, leave it removed.

### 4. Mono only where needed

Monospace belongs to code, identifiers, keys, tokens, logs, keyboard shortcuts and tabular data. It does not belong in headlines, body copy or buttons.

**Test:** is this text exact or machine-readable? If not, use the UI font.

### 5. Use a design system

Define tokens once: colour roles (surface, text, muted, border, accent, danger), a type scale, a spacing scale, radii, shadows and motion durations. Use tokens everywhere. A new value is a new token, not a one-off `#hex` or `13px`.

**Test:** every raw colour, size, radius and shadow resolves to a token.

### 6. Show the actual product

Replace abstract 3D blobs, generic illustrations, stock offices and floating orbs with the real thing: a screenshot, an embedded preview, a live demo or a short loop of the product doing its job.

**Test:** can a new visitor tell what they get within three seconds?

### 7. Enlarge the main feature

Every view has one primary job. Give it two to three times the visual weight of anything secondary. Make the product, the price, the article or the action dominant — not the background art.

**Test:** squint until the screen blurs. Is the first thing you notice the thing that matters?

### 8. Group with spacing

Proximity is stronger than borders. Space inside a group must be smaller than space between groups (for example 8px versus 24px). Use a consistent scale rather than arbitrary gaps.

**Test:** hide all borders and dividers. Are the groups still obvious? If not, spacing is wrong.

### 9. Make headlines specific

Use concrete nouns, numbers and outcomes. "Ship your first pipeline in 10 minutes" beats "Empower your workflow". "Invoices that reconcile themselves" beats "The future of finance".

**Test:** put a competitor's logo on the page. Does the headline still fit? Then it is too generic — rewrite.

### 10. Emphasize the CTA

Exactly one primary action per screen. Primary: solid fill, high contrast, larger. Secondary: outline or tinted. Tertiary: text link. Never give three buttons equal weight.

**Test:** blur the screen. Is there one obvious button? If you see three, fix the hierarchy.

### 11. Add an accent colour

Use one accent for action and state. Keep structure neutral so the accent means "interact here". Aim for less than roughly 10% of pixels. Five colours at equal strength is not a palette, it is noise.

**Test:** does your eye land on the action, or on decoration?

### 12. Keep icons consistent

Choose one icon family and keep its stroke width, fill style, corner treatment and optical size. Do not mix emoji, filled icons, outline icons, 3D icons and logos in the same row.

**Test:** remove colour. Do the icons look like siblings? If one has a different stroke or weight, replace it.

### 13. Remove embellishments

Delete decorative gradients, blobs, grid overlays, glass panels, sparkle icons, fake charts, floating shapes and glows. Keep texture only when it carries information or brand meaning.

**Test:** does this element explain, guide or identify? If it only decorates, remove it.

### 14. Inner radius = outer − padding

Nested rounded corners must be concentric:

```text
inner-radius = outer-radius − gap
```

If a card has radius 16 and 8px padding, the item inside gets radius 8. Do not nest a fully rounded image inside a rounded card without adjusting the corners.

**Test:** corners look parallel. No pinched, mismatched or double-rounded edges.

### 15. Improve text contrast

Meet WCAG AA as a floor: body text 4.5:1, large text 3:1, UI boundaries 3:1. Never use light grey on white for body copy. Muted text is for metadata, not paragraphs.

**Test:** desaturate the screen and squint. If you cannot read the body, raise the contrast.

### 16. Wrap headlines properly

Constrain display text to about 20–28 characters per line. Use `text-wrap: balance` on short headlines and `text-wrap: pretty` on body copy. Avoid an orphan — a single word stranded on the last line. Keep headlines to two or three lines maximum.

**Test:** resize the container. No single-word last lines, no four-line headlines.

### 17. Align by eye, not pixels

Optical alignment beats mathematical centering. Icons need slight offset because of their internal padding; text has side bearings; circles look smaller than squares. Nudge until it looks centered.

**Test:** zoom out. Do the elements look aligned? If a value is mathematically centered but visually off, trust your eye.

### 18. Use tabular nums

Use `font-variant-numeric: tabular-nums` wherever numbers change or are compared: tables, dashboards, timers, prices, counters, scores.

**Test:** change a value from `1` to `8`. Does the layout shift? If yes, enable tabular numerals.

### 19. Add loading states

Any action that can take longer than about 300ms needs feedback. Use skeletons for layout, spinners for short waits, progress for long or measurable work, optimistic updates for safe actions, and a disabled button with a pending label on submit.

**Test:** throttle the network. Is the interface honest about what is happening? Never leave a click silent.

### 20. Animate useful feedback

Animate cause and effect: where a panel came from, what changed, what is now active. Use 120–240ms, ease-out for entrances and ease-in for exits. Animate transform and opacity, not layout properties. Respect `prefers-reduced-motion`.

**Test:** remove the animation. Is anything harder to understand? If not, it was decoration.

## Audit output format

When reviewing an existing screen, respond in this shape:

```text
Unslop score: 14/20 — Almost

1. Rule 10 — three CTAs have equal weight.
   Fix: make "Start free" solid, demote the other two to text links.
2. Rule 15 — body copy is #9A9A9A on white (2.8:1).
   Fix: use #4A4A4A (9.1:1).
...
```

- Lead with the score and verdict: `Slopped` (0–9), `Generic` (10–13), `Almost` (14–17), `Clean` (18–20).
- List violations highest impact first. One line of diagnosis, one line of fix.
- Fix accessibility and hierarchy before craft details.
- Do not rewrite the entire design unless asked; make the smallest change that passes the rule.

When generating a new screen, apply the rules silently, then add a short note:

```text
Unslop pass: 20/20. Removed 4 filler badges, set one primary CTA, used tabular numerals, added loading + empty states.
```

## Guardrails

- Preserve brand identity. Unslop means removing noise, not erasing personality.
- Never trade accessibility for aesthetics. Contrast, focus states, hit targets and reduced motion are non-negotiable.
- Do not invent product facts, metrics or testimonials to make a headline specific.
- Do not animate everything. Motion is a feedback channel, not a style.
- Do not turn every screen into the same minimal template. Consistency comes from tokens and rules, not from deleting all character.
- When a rule conflicts with a deliberate art direction, say so and apply the structural rules only.

## Deep reference

`references/rules.md` expands each rule with rationale, examples and acceptance tests. `examples/before-after.md` shows concrete fixes. `CHEATSHEET.md` is the one-screen version for a fast pass.
