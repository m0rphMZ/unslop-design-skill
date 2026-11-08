# The 20 rules — expanded reference

Use this file when a quick pass is not enough: edge cases, rationale, implementation notes and acceptance tests.

---

## 1. Delete filler badges

**Why.** A badge is a signal with weight. Using badges for adjectives trains users to ignore badges, including the ones that matter (`Failed`, `Deprecated`, `Required`).

**Keep**
- State that changes behaviour: `Beta`, `Deprecated`, `Required`, `Failed`, `Archived`.
- Counts: `3 unread`, `12 issues`.
- Plan or environment: `Pro`, `Staging`.
- Real, verifiable claims with a source.

**Delete**
- `New`, `Fast`, `Secure`, `AI-powered`, `Smart`, `Modern`, `Next-gen`.
- Pills used as bullets, decoration or section markers.
- Multiple badges stacked to fill space.

**Implementation.** One `Badge` component with semantic variants. No freeform badge text in feature cards.

**Test.** Remove the badge. If no decision changes, it was decoration.

---

## 2. Drop redundant labels

**Why.** Repeating the same word in a label, placeholder, helper and icon wastes space and signals that the interface does not trust its own hierarchy.

**Do**
- One visible label per control.
- Placeholder shows an example, never the label.
- Helper text explains a constraint or consequence, not the obvious.
- One heading per section; do not repeat the page title in the first card.

**Don't**
- `Email` as icon, label, placeholder and helper simultaneously.
- Section headings that restate the navigation item word for word.
- Captions that describe what the image obviously shows.

**Test.** Remove the second occurrence. Is the action still unambiguous? Then it was redundant.

---

## 3. Unitalicize random words

**Why.** Decorative italics break scanning rhythm and are a common tell of generated copy. Real emphasis is rare and intentional.

**Do**
- `<em>` for genuine emphasis, titles of works and foreign terms.
- Use weight, size or colour for hierarchy.
- Use quotation marks for quotes, not italics everywhere.

**Don't**
- Italicize one word per sentence for "tone".
- Italicize entire paragraphs.
- Use italics to make a weak headline feel designed.

**Test.** Strip all italics. If nothing is lost, keep them stripped.

---

## 4. Mono only where needed

**Why.** Monospace means "exact, machine-readable text". Using it for style muddies that signal and usually hurts readability.

**Use mono for**
- Code, commands, file paths.
- IDs, hashes, tokens, API keys, versions.
- Logs and stack traces.
- Keyboard shortcuts.
- Tabular data where alignment matters.

**Never use mono for**
- Headlines, body copy, buttons, navigation.
- Decorative "developer" styling.

**Test.** Is the text exact or machine-readable? If not, use the UI font.

---

## 5. Use a design system

**Why.** Tokens create consistency, make redesigns cheap and prevent the slow drift of near-duplicate greys and 13px gaps.

**Define once**
- Colour roles: `surface`, `surface-raised`, `text`, `text-muted`, `border`, `accent`, `danger`, `success`, `warning`.
- Spacing scale: `4, 8, 12, 16, 24, 32, 48, 64`.
- Type scale: display, title, body, caption, mono.
- Radii: `sm, md, lg, pill`.
- Shadows: one or two elevation levels.
- Motion: `fast 120ms`, `base 180ms`, `slow 240ms` plus easings.

**Implementation.** CSS custom properties or framework tokens. Prefer semantic names (`--color-text-muted`) over literal ones (`--grey-400`).

**Test.** Every raw colour, size, radius and shadow resolves to a token. A new value requires a new token.

---

## 6. Show the actual product

**Why.** People need to see what they get. Abstract art fills space without answering the only question that matters: "what does this do?"

**Do**
- A real screenshot or a cropped, high-signal piece of UI.
- An embedded preview or live demo.
- A short loop showing the core action.
- An annotated close-up of the hard part.

**Don't**
- 3D blobs, floating orbs, generic vector people.
- Stock offices and handshakes.
- Fake dashboards with meaningless charts.

**Test.** Can a visitor tell what the product does within three seconds without reading the paragraph?

---

## 7. Enlarge the main feature

**Why.** Hierarchy is the design. If everything is the same size, the user has to think to find the point.

**Do**
- Identify the one job of the view.
- Give it two to three times the visual weight of secondary elements.
- Shrink or remove anything competing: secondary cards, badges, illustrations, navigation.

**Don't**
- Build a grid of six equal-weight cards when one thing is the point.
- Let background art outweigh the product.

**Test.** Squint until the screen blurs. The first thing you notice should be the thing that matters.

---

## 8. Group with spacing

**Why.** Proximity is the strongest grouping cue — stronger than borders, backgrounds and dividers. Correct spacing removes the need for boxes.

**Do**
- Inside-group spacing smaller than between-group spacing: `8` vs `24`, `12` vs `32`.
- Use the spacing scale, not arbitrary values.
- Prefer whitespace before adding a border.

**Don't**
- Use uniform gaps everywhere, then add borders to compensate.
- Wrap every section in a card.
- Let a label sit closer to the next field than to its own.

**Test.** Hide all borders and dividers. Are the groups still obvious? If not, fix spacing.

---

## 9. Make headlines specific

**Why.** Specific claims are credible and memorable. Generic promises are interchangeable, and users have learned to skip them.

**Do**
- Concrete nouns: invoices, pipelines, deployments, rooms.
- Numbers and timeframes when true: "in 10 minutes", "3 clicks", "99.9%".
- Outcomes: "Reconcile invoices automatically".
- A named audience when relevant: "For solo founders".

**Don't**
- `Empower`, `Unlock`, `Supercharge`, `Seamless`, `Next-generation`.
- "The future of X".
- Invented metrics or testimonials to sound specific.

**Test.** Put a competitor's logo on the page. If the headline still fits, rewrite it.

---

## 10. Emphasize the CTA

**Why.** Every additional equal-weight action slows the decision. One primary action makes the next step obvious.

**Do**
- Exactly one primary action per screen.
- Primary: solid fill, high contrast, action verb (`Start free`, `Create invoice`).
- Secondary: outline or tinted. Tertiary: text link.
- Keep placement consistent across screens.

**Don't**
- Three solid buttons side by side.
- A ghost button as the main action.
- Multiple "primary" colours.

**Test.** Blur the screen. Is there one obvious button? If you see three, fix the hierarchy.

---

## 11. Add an accent colour

**Why.** Colour is meaning. When the accent is used only for action and state, users learn where to look and what is interactive.

**Do**
- One accent for interactive and active states.
- Neutral surfaces and text.
- Semantic colours reserved for success, warning, danger.
- Keep accent coverage low — roughly under 10% of pixels.

**Don't**
- Five brand colours at equal strength.
- Accent on decoration, backgrounds and headings simultaneously.
- Low-contrast accent text on a tinted background.

**Test.** Does the eye land on the action, or on decoration?

---

## 12. Keep icons consistent

**Why.** Mixed icon styles read as sloppy even when users cannot name why. Consistency makes a row of icons feel like one system.

**Do**
- One family: Lucide, Heroicons, Phosphor, Material Symbols — pick one.
- Same stroke width, fill style and corner treatment.
- Same optical size: 16, 20 or 24px.
- Align icons optically with adjacent text.

**Don't**
- Mix emoji, filled, outline and 3D icons in one row.
- Scale one icon up to fill space.
- Use a logo as a generic icon.

**Test.** Remove colour. Do the icons look like siblings? Replace any stranger.

---

## 13. Remove embellishments

**Why.** Decoration competes with content for attention and makes an interface feel busier without being clearer.

**Delete**
- Decorative gradients and glows behind text.
- Blobs, orbs, grid overlays and noise textures with no function.
- Glassmorphism used as a default surface.
- Sparkle icons and "AI" glows.
- Fake charts and meaningless data visualisations.

**Keep**
- Texture that carries brand meaning.
- Visuals that explain the product or the data.
- A single deliberate signature element, if the brand has one.

**Test.** Does the element explain, guide or identify? If it only decorates, remove it.

---

## 14. Inner radius = outer − padding

**Why.** Concentric corners look machined. Mismatched or double-rounded nested corners look accidental.

```text
inner-radius = outer-radius − gap
```

Examples:

| Outer | Gap | Inner |
|---|---|---|
| 16 | 8 | 8 |
| 12 | 4 | 8 |
| 24 | 12 | 12 |

**Implementation**

```css
.card { border-radius: 16px; padding: 8px; }
.card__inner { border-radius: calc(16px - 8px); }
```

**Don't**
- Give the inner element the same radius as the outer one.
- Give the inner element a larger radius.
- Fully round an image inside a rounded card unless the corners are designed for it.

**Test.** Corners look parallel; no pinched or uneven gap.

---

## 15. Improve text contrast

**Why.** Low-contrast grey text is the most common accessibility failure in generated UI, and it fails in daylight, on projectors and for older eyes.

**Targets (WCAG AA)**
- Body text: at least 4.5:1.
- Large text (≥24px, or ≥18.66px bold): at least 3:1.
- UI boundaries, icons and focus rings: at least 3:1.

**Watch out**
- `#999` on white is about 2.85:1 — not enough for body.
- `#767676` on white is about 4.54:1 — a safe minimum.
- Reducing opacity lowers contrast; do not use `opacity: 0.5` for text.

**Test.** Desaturate the screen and squint. If the body is hard to read, raise the contrast.

---

## 16. Wrap headlines properly

**Why.** Bad line breaks create orphans, awkward rag and headlines that look unedited.

**Do**
- Limit display text to about 20–28 characters per line.
- `text-wrap: balance` for short headlines.
- `text-wrap: pretty` for body copy.
- Two or three lines maximum for a hero headline.
- Rewrite the headline if it cannot wrap well.

```css
h1 { max-width: 24ch; text-wrap: balance; }
p  { max-width: 65ch; text-wrap: pretty; }
```

**Don't**
- Leave a single word on the last line.
- Force a line break with `<br>` at one viewport width.
- Let a headline run four or more lines.

**Test.** Resize the container. No orphans, no four-line headline.

---

## 17. Align by eye, not pixels

**Why.** Mathematical centering ignores the shape of glyphs and icons. Optical alignment is what users perceive as correct.

**Do**
- Nudge icons toward the text baseline or optical center.
- Add a little extra padding on the side of a text button where the glyph has less visual weight.
- Make circles slightly larger than squares to appear equal.
- Trust the zoomed-out view.

**Don't**
- Center by bounding box alone.
- Let a play triangle sit visually left of center.
- Align text by its container rather than its side bearings.

**Test.** Zoom out. Do the elements look aligned? If they look off, they are off.

---

## 18. Use tabular nums

**Why.** Proportional digits change width, so counters, timers and table columns jitter as values update.

```css
.numeric, table, .timer, .price {
  font-variant-numeric: tabular-nums;
}
```

**Use for**
- Tables and dashboards.
- Timers and countdowns.
- Prices, scores and counters that change.
- Any column of numbers users compare.

**Don't**
- Use tabular numerals for long prose; proportional figures read better there.

**Test.** Change a value from `1` to `8`. If the layout shifts, enable tabular numerals.

---

## 19. Add loading states

**Why.** Silence feels broken. Users need to know that the click registered, that work is happening, and whether it succeeded.

**Thresholds**
- Under 100ms: no indicator.
- 100–300ms: usually nothing, or a subtle state change.
- Over 300ms: skeleton, spinner or progress.
- Over 1s: progress with context, or a skeleton that matches the final layout.
- Unknown duration: spinner plus a short status label.

**Patterns**
- Submit: disable the button, show a pending label or spinner.
- Lists: skeleton rows matching final row height.
- Optimistic updates: apply immediately, roll back visibly on failure.
- Empty and error states are part of loading design — design them too.

**Test.** Throttle to slow 3G. Is the interface honest about waiting? No silent clicks.

---

## 20. Animate useful feedback

**Why.** Motion is a feedback channel. Decorative motion delays the interface and competes with content.

**Do**
- 120–240ms for most UI transitions.
- Ease-out for entrances, ease-in for exits, ease-in-out for moves.
- Animate `transform` and `opacity`; avoid animating layout properties.
- Show cause and effect: where a panel came from, what changed, what is now active.
- Respect `prefers-reduced-motion`.

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

**Don't**
- Infinite decorative loops.
- Animating everything on scroll.
- Long, cinematic transitions in product UI.

**Test.** Remove the animation. Is anything harder to understand? If not, it was decoration.
