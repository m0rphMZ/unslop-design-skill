# Before / after

Concrete fixes for the most common slop patterns.

---

## 1. Generic hero headline (rule 9)

**Before**

```text
Empower your workflow with AI-powered automation
```

**After**

```text
Close your books in 3 days, not 3 weeks
```

**Why.** The first could belong to any product. The second names the job, the outcome and a real timeframe. If the timeframe is not true, use another true specific — never invent one.

---

## 2. Badge stack (rule 1)

**Before**

```text
[✨ AI-powered] [⚡ Fast] [🔒 Secure] [🚀 New]
```

**After**

```text
[SOC 2 Type II ↗]
```

**Why.** Four decorative badges carry no decision. A verifiable compliance claim with a link does.

---

## 3. Three equal CTAs (rule 10)

**Before**

```text
[ Get started ]  [ Learn more ]  [ Book a demo ]
   solid            solid            solid
```

**After**

```text
[ Start free ]   See how it works   Book a demo
   solid          text link          text link
```

**Why.** Equal weight forces the user to choose between actions instead of following one.

---

## 4. Nested corner mismatch (rule 14)

**Before**

```css
.card        { border-radius: 16px; padding: 8px; }
.card__image { border-radius: 16px; }
```

**After**

```css
.card        { border-radius: 16px; padding: 8px; }
.card__image { border-radius: 8px; } /* 16 − 8 */
```

**Why.** Concentric corners read as intentional. Equal radii inside a padded card look pinched.

---

## 5. Low-contrast body text (rule 15)

**Before**

```css
body { color: #9a9a9a; background: #ffffff; } /* ≈ 2.8:1 */
```

**After**

```css
body { color: #4a4a4a; background: #ffffff; } /* ≈ 9.1:1 */
```

**Why.** Body copy must clear 4.5:1. Muted grey belongs to metadata, not paragraphs.

---

## 6. Orphaned headline (rule 16)

**Before**

```text
The all-in-one platform for modern teams
to plan, build, and ship everything
together
```

**After**

```css
h1 { max-width: 24ch; text-wrap: balance; }
```

```text
Plan, build and ship together —
without the tool sprawl
```

**Why.** `balance` fixes the rag; shortening the copy fixes the real problem.

---

## 7. Icon soup (rule 12)

**Before**

```text
🚀 Launch   ⚙️ Configure   ✅ Done   🧊 Deploy
```

**After**

```text
[rocket] Launch   [sliders] Configure   [check] Done   [box] Deploy
```

All icons from one family, 20px, 1.5px stroke.

**Why.** One family reads as a system. Emoji plus outline plus filled reads as a collage.

---

## 8. Mono headline (rule 4)

**Before**

```css
h1 { font-family: "JetBrains Mono", monospace; }
```

**After**

```css
h1 { font-family: "Inter", sans-serif; font-weight: 600; }
code, .token { font-family: "JetBrains Mono", monospace; }
```

**Why.** Mono signals exact, machine-readable content. A headline is neither.

---

## 9. Jittering counter (rule 18)

**Before**

```css
.timer { font-variant-numeric: normal; }
```

**After**

```css
.timer {
  font-variant-numeric: tabular-nums;
  min-width: 5ch;
  text-align: right;
}
```

**Why.** Proportional digits change width as values change, so the layout twitches every tick.

---

## 10. Silent submit (rule 19)

**Before**

```text
[ Create invoice ]  → nothing until the request finishes
```

**After**

```text
[ Creating… ⟳ ]     disabled, spinner, pending label
→ success toast: "Invoice created"
→ failure: inline error + retry, form values preserved
```

**Why.** A click that produces no immediate feedback feels broken, even when it worked.

---

## 11. Decoration behind content (rule 13)

**Before**

```text
Hero with a purple-to-pink gradient, three blurred blobs,
a grid overlay and a sparkle icon behind the headline.
```

**After**

```text
Neutral surface, product screenshot at 2× the size,
one accent colour reserved for the primary action.
```

**Why.** Decoration competes with the product. Removing it makes the product the visual event.

---

## 12. Optical misalignment (rule 17)

**Before**

```text
[ ▶  Play video ]   /* triangle looks left of center */
```

**After**

```text
[  ▶ Play video ]   /* icon nudged 1px right, 2px extra left padding */
```

**Why.** A triangle's visual center sits right of its bounding-box center. Measure less, look more.

---

## Mini audit

**Input:** SaaS pricing page with four equal cards, five badges per card, `#999` body text, three solid buttons and no loading state.

```text
Unslop score: 11/20 — Generic

1. Rule 7 — four equal-weight pricing cards; no recommended plan.
   Fix: enlarge the middle plan 1.2×, add "Most popular", keep others neutral.
2. Rule 10 — three solid CTAs.
   Fix: one primary per card; demote "Contact sales" to a text link.
3. Rule 1 — 20 badges, 16 decorative.
   Fix: keep plan name, price and one real limit badge.
4. Rule 15 — body copy #999 on white (2.8:1).
   Fix: #4A4A4A (9.1:1).
5. Rule 19 — "Upgrade" gives no feedback.
   Fix: disable + spinner + "Redirecting…", handle errors inline.
```

Fix order: hierarchy and contrast first, decoration last.
