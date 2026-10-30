# Guide for AI Agents: Applying a DESIGN.md to Anything

This guide tells you how to take one of the 100 `DESIGN.md` files in [`designs/`](designs/) and use it to produce work that matches that visual language. It works for interfaces, documents, slides, emails, social posts, images, video, and anything else with a visual dimension.

---

## 1. Read the DESIGN.md in this order

Every file has the same sections. Read them in this order, because later sections depend on earlier ones.

| Order | Section | What to take from it |
|---|---|---|
| 1 | Header and `Theme` | Light or dark. Sets the overall contrast strategy. |
| 2 | Opening paragraph | The design philosophy. Use it to decide tone when the spec is silent. |
| 3 | `Tokens — Colors` | Exact hex values, token names, and the role of each color. |
| 4 | `Tokens — Typography` | Families, weights, sizes, line heights, letter spacing, and each role. |
| 5 | `Tokens — Spacing & Shapes` | Spacing scale, radius, borders, shadows. |
| 6 | `Components` | How buttons, cards, inputs, nav and others are built. |
| 7 | `Do's and Don'ts` | Hard rules. Obey these before anything else. |
| 8 | `Surfaces`, `Elevation`, `Imagery` | Background treatment, depth, and image style. |
| 9 | `Layout` | Grid, columns, density, and section rhythm. |
| 10 | `Agent Prompt Guide` | The file's own instructions to you. Follow them. |
| 11 | `Typographic Voice`, `Similar Brands` | Writing tone, and which other styles are close. |
| 12 | `Quick Start` | A short recipe for getting started. |

If a value is missing, prefer the closest documented value. Do not invent new colors, fonts, or radii.

---

## 2. Decide what you are making

Use the table below to choose what to carry over from the file.

| Output | Carry over | Leave out |
|---|---|---|
| Web page or app UI | Tokens, components, layout, do's and don'ts, imagery | Anything tied to a specific product's data or copy |
| Slide deck | Palette, type scale, surfaces, one accent | Dense component specs, interaction notes |
| Email | Palette, type, button style, spacing | Hover states, responsive grids beyond a single column |
| Social post or carousel | Palette, type, imagery mood, one accent | Layout grids, component specs |
| Image or illustration | Palette, mood, texture, lighting notes | Font names, UI components |
| Video or motion | Palette, type, motion notes if present, mood | Component specs |
| Document or report | Type scale, heading weights, table style, spacing | Hero and marketing components |
| Logo or brand mark | Palette and mood only | Any real logo, mark, or trademark from the source |

---

## 3. Build with the tokens, not the screenshot

1. **Define tokens first.** Turn the colors, type scale, and spacing into CSS variables, Tailwind config, or your tool's equivalent. The file lists token names, so reuse them.
2. **Build components from the Components section.** Follow each component's documented anatomy, states, and sizes.
3. **Compose screens or layouts from the Layout section.** Match the grid, density and section rhythm.
4. **Apply surfaces and elevation last.** Use the documented background and shadow rules.
5. **Check against Do's and Don'ts.** Fix any violation before you consider the output finished.

Do not copy a screenshot. The file describes the system, so build from that description.

---

## 4. Rules that apply everywhere

- **Obey the Do's and Don'ts.** They are the strongest guidance in the file.
- **Respect the theme.** Light styles stay light, dark styles stay dark, unless the user asks otherwise.
- **Limit accents.** Most DESIGN.md files define one accent color for emphasis. Don't spread it across the page.
- **Keep the type system.** Use only the documented families and weights. If a family is unavailable, use the file's substitute.
- **Use real spacing values.** Use the documented scale instead of arbitrary pixels.
- **Keep the voice.** Match the `Typographic Voice` section when writing copy.
- **Stay within the brand line.** Do not copy logos, trademarks, photos, or copyrighted text from the source site. Do not imply that work came from the original company.
- **Check contrast.** Make sure text meets readable contrast against its background, especially in dark styles.

---

## 5. Recipes by format

### Web page or landing page
1. Set up the color, type, and spacing tokens.
2. Build nav, hero, feature sections, and footer from the Components and Layout sections.
3. Apply the imagery and surface rules to sections.
4. Verify on mobile and desktop widths.

### App screen or dashboard
1. Set up tokens. Use the file's Surfaces section for backgrounds and cards.
2. Build data components (tables, charts, stat cards) using the documented styles.
3. Keep density consistent with the Layout section.

### Slide deck
1. Use the background color for each slide. Use one accent color per slide.
2. Set headlines using the display weight. Keep body text readable.
3. Use the same layout across slides unless content needs a change.

### Email
1. Use a single column, the documented button style, and the body type size.
2. Keep the background neutral and the accent for the call to action.
3. Test in a narrow viewport.

### Social post or carousel
1. Pick a background from the palette.
2. Use the display type for the headline and body type for supporting text.
3. Add one accent element. Keep the composition simple.

### Image or illustration prompt
Describe: the palette (hex values), the mood (from the header and opening paragraph), the lighting and texture (from Imagery and Surfaces), and what must be avoided (from Do's and Don'ts).

### Document or report
1. Use the type scale for headings and body.
2. Use the documented table style and spacing.
3. Keep margins and line heights consistent.

---

## 6. Prompt templates you can paste

**Generic build prompt**

> Use the attached DESIGN.md as the complete visual system. Follow its Do's and Don'ts and its Agent Prompt Guide.
> Build: [what you are making].
> Audience: [who it is for].
> Constraints: [length, format, platform, anything the user specified].
> Output: [file type or format].

**Image prompt**

> Create an image in the style described by the attached DESIGN.md. Palette: [hex values from the file]. Mood: [mood from the header]. Lighting and texture: [from Imagery and Surfaces]. Avoid: [from Do's and Don'ts]. Subject: [subject].

**Deck prompt**

> Make a [N]-slide deck using the attached DESIGN.md. Background: [hex]. Headline type: [family, weight, size]. Accent: [one hex]. Slide content: [outline].

---

## 7. Quality checklist before you deliver

- [ ] Colors are exact hex values from the file.
- [ ] Type families, weights, and sizes come from the type section.
- [ ] Spacing uses the documented scale.
- [ ] Components match their documented anatomy and states.
- [ ] Every Do's and Don'ts rule is satisfied.
- [ ] One accent color is used for emphasis.
- [ ] Theme (light or dark) is consistent.
- [ ] No logos, trademarks, or copyrighted assets from the source site.
- [ ] Text is readable at the intended size and viewing distance.

---

## 8. When the file and the user disagree

The user's explicit request wins. If a request conflicts with a hard rule (for example, "use this style but use a bright red accent"), follow the request and note the deviation in your response.

---

## 9. Choosing a style

- **Need warm and editorial?** Look for styles described as paper, cream, or serif-led.
- **Need dark and technical?** Look for styles described as midnight, obsidian, or code-editor.
- **Need playful?** Look for mascot, illustration, or vivid-accent styles.
- **Not sure?** Use the `Similar Brands` section of a file you like to find neighbors.

The index in the README lists each style's theme and mood.

---

*Generated from the 100 DESIGN.md files in this repo. Each file's own Agent Prompt Guide takes priority over this general guide when they conflict.*
