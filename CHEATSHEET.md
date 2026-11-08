# Unslop Cheatsheet

Twenty pass/fail checks. Ten seconds per phase. Score one point per rule.

## Phase 1: Structure (10s)

- [ ] **1. Filler badges:** only badges that change a decision survive.
- [ ] **2. Redundant labels:** one label per control, one heading per section.
- [ ] **3. Random italics:** italics removed unless they carry emphasis.
- [ ] **4. Mono misuse:** monospace only on code, IDs, keys and data.

## Phase 2: Hierarchy (10s)

- [ ] **5. Design system:** every value resolves to a token.
- [ ] **6. Real product:** actual UI shown, no abstract filler art.
- [ ] **7. Main feature:** one element clearly dominant at a squint.
- [ ] **8. Grouping:** inside-space smaller than between-space.
- [ ] **9. Headline:** specific outcome, not a slogan a rival could reuse.
- [ ] **10. CTA:** exactly one primary action.
- [ ] **11. Accent:** one accent, used for action and state.

## Phase 3: Craft (10s)

- [ ] **12. Icons:** one family, weight and optical size.
- [ ] **13. Embellishments:** nothing decorative left.
- [ ] **14. Nested radius:** inner = outer − padding.
- [ ] **15. Contrast:** body ≥ 4.5:1, large text ≥ 3:1.
- [ ] **16. Headline wrap:** no orphans, at most three lines.
- [ ] **17. Optical alignment:** looks centered, not merely measured.

## Phase 4: Behaviour (10s)

- [ ] **18. Tabular nums:** digits do not change width.
- [ ] **19. Loading states:** no silent waits over 300ms.
- [ ] **20. Useful motion:** animation explains change; reduced motion respected.

## Verdict

| Score | Verdict | Action |
|---|---|---|
| 0–9 | Slopped | Rework hierarchy before polish |
| 10–13 | Generic | Fix structure and CTA first |
| 14–17 | Almost | Close the craft and state gaps |
| 18–20 | Clean | Ship |

**Minimum to ship: 18/20. Hero and public surfaces: 20/20.**

## Three questions that catch most slop

1. If I delete this element, what information is lost?
2. Squinting, what do I see first, and is it the product or the decoration?
3. Does the interface tell the truth about waiting, errors and state?
