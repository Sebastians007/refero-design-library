# AGENTS.md — Read this first

You have been pointed at a library of **100 real design systems** (`designs/*.md`), each a complete `DESIGN.md` spec. The user may ask for anything from "make this look better" to "10x my design" to "make me a brand from scratch". This file tells you how to turn that into concrete, high-quality work.

**Files to use**
- `styles.json` — machine-readable index: site, theme, mood, typefaces, palette. Use it to shortlist styles fast.
- `designs/<site>-DESIGN.md` — the full spec for one style. Read the whole file before applying it.
- `GUIDE-FOR-AI.md` — the detailed application guide (token setup, components, formats, prompt templates, QA checklist).

---

## 1. Classify the request

Decide which of these the user wants. If it's mixed, handle them in order.

| Request type | Example | What to do |
|---|---|---|
| **Audit / improve** their existing design | "make my site look better", "critique my deck" | Run the Audit (section 3), then Recommend (section 4). Apply fixes only if asked. |
| **Restyle** toward a look | "make it feel like Linear", "dark and premium" | Shortlist (section 2), then Apply (section 5). |
| **Create from scratch** | "design me a landing page for my coffee brand" | Shortlist, pick 1 to 3 candidates, build the best one, explain why. |
| **Vague amplifier** | "10x this", "100x my design", "make it go viral" | Audit first, then apply the top high-leverage changes. Don't just swap colors. See section 6. |
| **Pure question** | "which style fits a fintech?" | Answer with a shortlist and reasons. Don't build anything unless asked. |

If the request is vague, don't stop to ask. Make the most reasonable assumption, say it in one line, and proceed. Ask only if the target (which page, which product, which audience) can't be inferred at all.

---

## 2. Shortlist a style

1. Read `styles.json`. Filter by `theme` (light or dark) and by `mood` keywords that match the user's goal.
2. Pick **1 to 3** candidates. Prefer styles whose mood and typefaces suit the product's audience.
3. Open each candidate's `DESIGN.md`. Check its **Do's and Don'ts**, **Typographic Voice**, and **Similar Brands** before committing.
4. Explain the choice in 2 or 3 sentences: why this look fits this user's goal.

Mood to goal, quick map:
- Trust, finance, B2B: calm, precise, light, restrained accent.
- Developer tools, AI products: technical, dark, monospace accents, high contrast.
- Consumer, lifestyle, food: warm, vivid, rounded, photography-led.
- Editorial, content, newsletters: serif-led, paper or cream, generous whitespace.
- Premium, luxury: dark or muted neutrals, large display type, few elements.

---

## 3. Audit an existing design

Score each area 1 to 5 and write one concrete finding per area. Use exact values where you can (hex, px, font names).

1. **Hierarchy**: is there one clear primary message and action? Is the type scale distinct (no more than about 5 sizes in use)?
2. **Color**: how many distinct colors are in use? Is there one accent? Is contrast readable (WCAG AA for body text)?
3. **Type**: how many families and weights? Does body text have a comfortable line height (about 1.4 to 1.6)?
4. **Spacing and rhythm**: is spacing on a consistent scale (4, 8, 12, 16, 24, 32, 48)? Are sections evenly paced?
5. **Components**: are buttons, cards, and inputs consistent in radius, height, padding, and states?
6. **Imagery and surfaces**: is imagery consistent in style? Are backgrounds and shadows coherent?
7. **Copy**: is the headline specific and benefit-led? Is the tone consistent?

---

## 4. Recommend (the core deliverable)

Write recommendations in this order. Keep them specific and ranked by impact.

1. **Verdict** (1 or 2 sentences): what works, what is holding it back.
2. **Top 5 changes**, ranked by expected impact. For each:
   - **What**: the exact change (for example "set the primary button to #0007cb, 16px/600, 8px radius").
   - **Why**: the principle or the matched style rule it comes from.
   - **Effort**: small, medium, or large.
3. **Target style**: the recommended DESIGN.md (file name) and the 3 or 4 rules you'd borrow from it.
4. **Quick wins** (under 30 minutes): a short list.
5. **Next step**: offer to apply the changes, and ask only one question if something essential is missing.

Do not dump the whole DESIGN.md into the reply. Quote only the few values and rules you're using.

---

## 5. Apply a style

Follow `GUIDE-FOR-AI.md` section 3 (tokens first, then components, then layout, then surfaces, then do's and don'ts). Key rules:

- Turn colors, type scale, and spacing into variables before writing any component.
- Use only the documented typefaces and weights. If one is unavailable, use the file's listed substitute.
- Keep one accent color. Keep the theme (light or dark) consistent.
- Never copy a screenshot, logo, trademark, or copyrighted text from the source site.
- Verify against the file's Do's and Don'ts before you finish.

---

## 6. "10x" and "100x" requests

Take them literally as an outcome goal, and be honest about what changes the result. Work in this order, because each step has more leverage than the one after it:

1. **Message and offer**: is the headline clear and specific? Is there one obvious action? (Usually the biggest lift, and it costs no design effort.)
2. **Hierarchy and layout**: remove clutter, make one thing dominant, shorten the path to the action.
3. **Consistency**: one type system, one accent, one spacing scale, one component set.
4. **Proof and imagery**: real product screenshots, specific numbers, and quality photography beat decorative graphics.
5. **Motion and polish**: only after 1 to 4 are solid. Keep it subtle and purposeful.

State plainly that a 100x design comes from a clearer message and fewer, better choices, not from more effects. Show before and after reasoning, not just a new look.

---

## 7. Output standards

- Lead with the result. No filler.
- Name the file you used (for example `designs/linear-DESIGN.md`).
- Give exact values, not adjectives. "#0007cb at 16px/600", not "a bold blue".
- When you apply changes, list every file you changed and why, and keep the changes small enough to review.
- Flag assumptions in one line each.

---

## 8. Anti-patterns to avoid

- Recoloring everything without changing hierarchy. Color is the least important lever.
- Using more than one accent color, or more than three type weights, without a reason.
- Copying a brand's look so closely that it reads as that brand. Borrow principles, then make it the user's.
- Adding shadows, gradients, and animation to hide weak layout.
- Changing the whole design when the user asked for two or three specific fixes.
- Presenting a restyle as a complete rebrand when the user only wanted better spacing.

---

*When this file and a specific `DESIGN.md` conflict, the specific file's own Agent Prompt Guide and Do's and Don'ts win for that style. The user's explicit request wins over both.*
