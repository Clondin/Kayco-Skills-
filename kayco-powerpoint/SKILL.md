---
name: kayco-powerpoint
description: "Use this skill any time a .pptx file is involved in any way — as input, output, or both. This includes creating, reading, extracting, editing, combining, splitting, templating, or QAing PowerPoint decks. Trigger whenever the user mentions \"deck,\" \"slides,\" \"presentation,\" or references a .pptx filename. For KAYCO, kosher food company, supplier, internal meeting, executive update, workshop, AI-at-work, or branded presentation work, use the KAYCO purple-led visual system, bundled logo assets, and brand-safe image guidance in this skill."
license: Proprietary. LICENSE.txt has complete terms
---

# PPTX Skill

This is the general PowerPoint skill with a KAYCO brand mode. Use the generic PPTX workflow for any deck, and activate KAYCO brand mode whenever the deck is for KAYCO, a KAYCO internal audience, a kosher food company context, supplier work, an executive update, a workshop, or a branded KAYCO presentation.

## Quick Reference

| Task | Guide |
|------|-------|
| Read/analyze content | `extract-text presentation.pptx` |
| Edit or create from template | Read [editing.md](editing.md) |
| Create from scratch | Read [pptxgenjs.md](pptxgenjs.md) |
| KAYCO brand styling | Read [references/brand-guide.md](references/brand-guide.md) |
| KAYCO brand logos | Read [references/brand-logos.md](references/brand-logos.md) |

---

## KAYCO Brand Mode

Use this mode for KAYCO, kosher food company, supplier, internal meeting, executive update, workshop, AI-at-work, or branded presentation requests.

### Brand Assets

- Use `assets/kayco-logo.png` as the primary deck logo.
- Use individual brand logos from `assets/brand-logos/` only when the slide is specifically about that brand, product example, supplier/retailer context, or cross-brand comparison.
- Read `references/brand-guide.md` before designing KAYCO slides.
- Read `references/brand-logos.md` before using a specific KAYCO brand mark.
- Insert logos as images and preserve original aspect ratios. Do not recreate, redraw, recolor, or generate logos.

### KAYCO Visual System

- Primary brand color: KAYCO purple `#9D257E`.
- Supporting palette: deep plum `#4D0F41`, secondary plum `#6D185C`, soft blush `#F2B8DF`, pale lavender `#F8ECF5`, warm pale background `#FCF6FA`, ink `#1A1A1A`, body `#2B2B2B`, muted `#6B6B6B`, hairline `#E6C7DC`, white `#FFFFFF`.
- Prefer a narrow page-name strip: KAYCO logo on the left, one right-aligned page name in KAYCO purple, and no tall stacked-eyebrow headline panel.
- Use KAYCO purple for hero numbers, step circles, call-to-action bars, and sparse visual anchors.
- Keep content slides spacious and commercial: strong typography, clear hierarchy, and whitespace before boxes.
- Use purple-led cover and closing slides when appropriate, but avoid decorative clutter, robots, brains, glowing circuits, and generic stock-photo styling.

### KAYCO Layout Guidance

- Build editable PowerPoint content whenever possible: slide text, tables, callouts, labels, diagrams, and charts should be native objects.
- Prefer large integrated visual plates, half-bleed images, diagrams, or hierarchical stat displays over small pasted-in thumbnails.
- Use soft lavender panels only when they group genuinely related content. Do not let KAYCO styling become a grid of outlined cards.
- For AI training decks, explain concepts through concrete workplace examples: supplier documents, spreadsheets, checklists, routing lines, product reviews, and approved tools/channels.
- Preserve source-backed details. If a number, SKU detail, sensitivity table, meeting agenda, presenter title, or internal metric is unclear, mark it as unconfirmed instead of inventing it.

### KAYCO Imagegen Rules

Use `imagegen` for:

- Full-bleed cover art.
- Wide supporting visuals for demo, data, document-review, prompting, workflow, or guardrail slides.
- Text-free food-business or workflow imagery that adds atmosphere.

Do not ask imagegen for:

- KAYCO logos or KAYCO brand logos.
- Readable slide text, labels, numbers, charts, tables, citations, or UI copy.
- Fake brand marks.
- Robots, brains, glowing circuits, or generic AI imagery.

Prompt images with:

- KAYCO purple `#9D257E`, deep plum, white, soft blush, pale lavender, subtle charcoal.
- Food-business context when relevant: unlabeled cartons, supplier documents, spreadsheets, checklists, routing lines.
- Calm negative space where editable slide text will sit.

### KAYCO Tone

- Friendly and practical, not hype-driven.
- Direct and confident for buyer, investor, executive, and supplier audiences.
- For warnings, include a grounded "what can go wrong" example.
- Avoid internal-language tells unless the audience is explicitly internal.

---

## Reading Content

```bash
# Text extraction, one `## Slide N` section per slide
extract-text presentation.pptx

# Visual overview
python scripts/thumbnail.py presentation.pptx

# Raw XML
python scripts/office/unpack.py presentation.pptx unpacked/
```

---

## Editing Workflow

**Read [editing.md](editing.md) for full details.**

1. Analyze template with `thumbnail.py`
2. Unpack → manipulate slides → edit content → clean → pack

---

## Creating from Scratch

**Read [pptxgenjs.md](pptxgenjs.md) for full details.**

Use when no template or reference presentation is available.

---

## The Slop Problem (Read This First)

AI-generated decks fail in a specific, recognizable way. Recognizing the failure mode is more important than any individual design tip below.

**The single most common AI-deck failure: every piece of content gets wrapped in its own outlined card.** A headline gets a tinted box. Four supporting points get four white outlined boxes with left accent bars. The closing summary gets another box. Stats get boxes. The "01/02/03" reasons get boxes. By slide 4 the deck looks like a spreadsheet of mini-cards and the eye can't tell what's important.

**Boxes must earn their place.** A box should signal "this is a different kind of thing" — a call-to-action, a stat group worth quarantining, a clickable element in a mockup. When every element is boxed equally, boxes stop carrying meaning and become decoration. Strip them.

The rest of this section makes that concrete.

### Diagnose box density before you build

Before writing any slide, count the boxes you're tempted to draw. If the answer is more than 2-3 outlined containers per content slide, you're heading toward slop. For each box, ask:

- Is this box doing structural work (grouping items that belong together visually)?
- Or am I outlining things because I don't trust typography and whitespace alone?

If it's the second answer, the box has to go. Whitespace separates items. Bold labels distinguish them. A small filled dot or numbered circle can anchor a row without enclosing it.

### What replaces boxes

- **Whitespace and typography**: bold dark labels + body text + 0.3-0.5" vertical gap. Reads as a list without needing borders.
- **Small filled circles** as row anchors (0.2" diameter, brand accent color). Dots, not frames.
- **Numbered filled circles** for ordered/process content (0.5" diameter, brand color filled, white digit centered). Used as steps in a flow connected by a thin line.
- **Ghost numerals**: large pale-tint numbers (01/02/03) sitting behind or beside content as anchors, not containers.
- **Subtle filled section panels** with very soft fill (5-8% tint of brand color) and rounded corners. Use sparingly — at most one or two per content slide — to group items that belong together while letting the inner content remain border-free.
- **Hairline rules** (`E3CDBA` or similar, 1px) as table-row dividers or section separators.

### Earned shapes (where a box IS the right answer)

- The closing call-to-action bar on a submission/summary slide (deep brand color, white text). One per deck.
- A connecting line behind a numbered process flow (visual continuity between steps).
- A header strip / page-name tab at the top of content slides — see "Page-name strips" below.
- A genuinely interactive UI element when prototyping a mockup.

### Headers: page-name strips, not headline panels

A common slop pattern: each interior slide gets a tall (1"+) white header bar containing a small all-caps "eyebrow" + a large magenta headline + a right-side category tag. Three pieces of typography occupying ~18% of the slide on every page, often repeating language the body of the slide already shows.

**Do this instead**: a narrow (~0.7") header strip with the company logo on the left and a single right-aligned page name in brand color (e.g. "Pricing", "Logistics", "Operations"). One tier of typography. Functions like a tab strip in a printed report. The body of the slide is free to lead with whatever the slide is actually about, not a restated section heading.

### Stat displays: hierarchy beats grids

The other common failure: four "equally important" stat boxes in a 2x2 or 1x4 grid, each with the same size number and same outlined container. Now the eye has nothing to grab onto.

**Apply hierarchy.** If one number tells the story, make it large (60-90pt) and let the supporting numbers be smaller (24-32pt) reference figures on a quiet baseline strip. A pricing slide comparing two numbers should look like `$4.99 → $2.50` with everything else as supporting text underneath a hairline rule. Equal-weight stat grids communicate "here is some data"; hierarchical stat displays communicate "here is the point."

### Don't editorialize a pitch deck

Italic Georgia pull-quotes, oversized decorative quotation marks behind text, magazine-style typography — these signal "this is an editorial spread" and read as soft when the deck is supposed to read as confident commercial pitch. If the audience is a buyer, an investor, or a decision-maker, the value statements should be in the body font, bold, direct. Save editorial typography for the genuinely reflective moments (a single closing line, a customer-quote slide where someone actually said the words).

### Don't fabricate data

It is tempting, when laying out a numbers-heavy slide, to invent a stat that would visually complete the row. Don't. Specifically:

- Never invent margin percentages (especially when presenting to the party who owns that margin).
- Never invent market sizes, growth rates, conversion rates, or category share figures.
- If a slide has three stats and a fourth would balance the layout, restructure the layout, not the data.
- If the user gave you cost and price, you may compute the implied markup as a derivative — but flag it clearly as derived, and reconsider whether showing it to the eventual audience makes sense.

### Internal-language tells

Watch for and strip these:

- Footers reading "Sources: user prompt" or "Generated closing image" or any phrase that exposes the AI-draft origin. Replace with real source language ("Company X spec sheet; calculated logistics math") or remove.
- Placeholder names: "Client Name", "[Insert Logo]", "TBD".
- Internal-only framing words when the deck has been adapted for an external audience: "submitted for review", "draft for approval", "preliminary".

When adapting an internal document for an external audience, re-read every footer, header, eyebrow, and tag with that audience in mind.

---

## Design Ideas

**Don't create boring slides.** Plain bullets on a white background won't impress anyone. Consider ideas from this list for each slide.

### Before Starting

- **Pick a bold, content-informed color palette**: The palette should feel designed for THIS topic. If swapping your colors into a completely different presentation would still "work," you haven't made specific enough choices.
- **Dominance over equality**: One color should dominate (60-70% visual weight), with 1-2 supporting tones and one sharp accent. Never give all colors equal weight.
- **Dark/light contrast**: Dark backgrounds for title + conclusion slides, light for content ("sandwich" structure). Or commit to dark throughout for a premium feel.
- **Commit to a visual motif**: Pick ONE distinctive element and repeat it — rounded image frames, icons in colored circles, thick single-side borders. Carry it across every slide. **But apply it sparingly per slide** — if the motif is "outlined cards," that doesn't mean every text block becomes an outlined card. The motif should appear 1-3 times per slide, not 6-10.

### Color Palettes

Choose colors that match your topic — don't default to generic blue. Use these palettes as inspiration:

| Theme | Primary | Secondary | Accent |
|-------|---------|-----------|--------|
| **Midnight Executive** | `1E2761` (navy) | `CADCFC` (ice blue) | `FFFFFF` (white) |
| **Forest & Moss** | `2C5F2D` (forest) | `97BC62` (moss) | `F5F5F5` (cream) |
| **Coral Energy** | `F96167` (coral) | `F9E795` (gold) | `2F3C7E` (navy) |
| **Warm Terracotta** | `B85042` (terracotta) | `E7E8D1` (sand) | `A7BEAE` (sage) |
| **Ocean Gradient** | `065A82` (deep blue) | `1C7293` (teal) | `21295C` (midnight) |
| **Charcoal Minimal** | `36454F` (charcoal) | `F2F2F2` (off-white) | `212121` (black) |
| **Teal Trust** | `028090` (teal) | `00A896` (seafoam) | `02C39A` (mint) |
| **Berry & Cream** | `6D2E46` (berry) | `A26769` (dusty rose) | `ECE2D0` (cream) |
| **Sage Calm** | `84B59F` (sage) | `69A297` (eucalyptus) | `50808E` (slate) |
| **Cherry Bold** | `990011` (cherry) | `FCF6F5` (off-white) | `2F3C7E` (navy) |

### For Each Slide

**Every slide needs a visual element** — image, chart, icon, or shape. Text-only slides are forgettable.

**Layout options:**
- Two-column (text left, illustration on right)
- Icon + text rows (icon in colored circle, bold header, description below) — NO outlined containers around each row
- 2x2 or 2x3 grid of dot-anchored items (small filled circle + bold label + body sentence). Whitespace between rows, not borders.
- Half-bleed image (full left or right side) with content overlay
- Soft-tinted section panel grouping 3-4 stats, with the stats themselves border-free inside

**Data display:**
- ONE dominant stat (60-90pt big number in brand color) + supporting captions
- Comparison with arrow: `BIG NUMBER → BIG NUMBER` with small labels under each, no enclosing box
- Hierarchical stat groups (one story stat, several support stats in smaller type below a hairline)
- Process flow: numbered filled circles connected by a thin line, bold labels and body sentences below each

**Visual polish:**
- Small filled dots (brand color, 0.2" diameter) as row anchors instead of bullets or boxes
- Hairline rules between table rows or sections (`E3CDBA` or 1px brand-tint)
- Italic accent text for taglines (sparingly, max one per slide)

### Typography

**Choose an interesting font pairing** — don't default to Arial. Pick a header font with personality and pair it with a clean body font.

| Header Font | Body Font |
|-------------|-----------|
| Georgia | Calibri |
| Arial Black | Arial |
| Calibri | Calibri Light |
| Cambria | Calibri |
| Trebuchet MS | Calibri |
| Impact | Arial |
| Palatino | Garamond |
| Consolas | Calibri |

| Element | Size |
|---------|------|
| Slide title | 36-44pt bold |
| Page name (header strip) | 14pt bold brand color |
| Section header | 9-10pt all-caps with letter-spacing, muted gray |
| Body text | 11-14pt |
| Hero stat number | 60-96pt bold brand color |
| Stat caption | 10-12pt muted |
| Captions | 10-12pt muted |

### Spacing

- 0.5" minimum margins
- 0.3-0.5" between content blocks
- Leave breathing room — don't fill every inch
- Page-name header strip: ~0.7" tall (650000-720000 EMU). NOT 1"+ — that's a headline panel, not a header.

### Avoid (Common Mistakes — In Priority Order)

**TOP-PRIORITY AI-DECK TELLS:**

- **Don't wrap every text block in an outlined card** — uniform outlined containers everywhere is the #1 visual signal of AI-generated slop. Boxes should be RARE and earn their place. See "The Slop Problem" above.
- **Don't build tall stacked-eyebrow headers on every slide** — the eyebrow-above-headline-with-right-tag pattern occupying 1/6 of the slide on every content page is AI slop. Use a narrow page-name strip instead.
- **Don't grid equal-weight stat boxes** — four equally sized number-and-label cards in a 2x2 communicates nothing. Make ONE the hero and demote the rest to supporting text.
- **Don't fabricate financial data** — especially margins, market shares, conversion rates. If the layout needs a fourth stat, fix the layout.
- **Don't leave internal-language tells in footers** — "Sources: user prompt", "Generated by", placeholder names. Strip on every pass.
- **Don't editorialize a pitch deck** — italic Georgia pull-quotes and giant decorative quotation marks behind text are magazine-spread treatments. Pitch decks need bold, direct, body-font statements.

**OTHER MISTAKES:**

- **Don't repeat the same layout** — vary columns, cards, and callouts across slides
- **Don't center body text** — left-align paragraphs and lists; center only titles
- **Don't skimp on size contrast** — titles need 36pt+ to stand out from 14-16pt body
- **Don't default to blue** — pick colors that reflect the specific topic
- **Don't mix spacing randomly** — choose 0.3" or 0.5" gaps and use consistently
- **Don't style one slide and leave the rest plain** — commit fully or keep it simple throughout
- **Don't create text-only slides** — add images, icons, charts, or visual elements; avoid plain title + bullets
- **Don't forget text box padding** — when aligning lines or shapes with text edges, set `margin: 0` on the text box or offset the shape to account for padding
- **Don't use low-contrast elements** — icons AND text need strong contrast against the background; avoid light text on light backgrounds or dark text on dark backgrounds
- **NEVER use accent lines under titles** — these are a hallmark of AI-generated slides; use whitespace or background color instead
- **Don't add decorative full-width colored bars/rectangles** — header/footer bars, side ribbons, or colored stripes read as AI slop unless the user explicitly requests them
- **Don't default to cream/beige backgrounds** — when no background is specified, use white (`FFFFFF`) or the user's brand palette; avoid warm-neutral defaults like `F5F5DC`, `FAF0E6`, `FAEBD7`, `FFF8E1`
- **Don't ship text that overflows its shape** — if text doesn't fit, reduce font size, split across slides, or enlarge the container; never leave content cut off or spilling past bounds

---

## QA (Required)

Your first render usually has a few real issues — overlaps, overflow, misalignment, AND box-density slop. Find and fix those, then stop. Don't keep iterating on minor coordinate nudges or chase a "perfect" render.

Work, don't narrate: minimize prose between tool calls. Run the check, apply the fix, move on.

### Content QA

```bash
extract-text output.pptx
```

Check for missing content, typos, wrong order.

**When using templates, check for leftover placeholder text:**

```bash
extract-text output.pptx | grep -iE "\bx{3,}\b|lorem|ipsum|\bTODO|\[insert|this.*(page|slide).*layout|user prompt|generated by"
```

If grep returns results, fix them before declaring success.

### Visual QA

**⚠️ USE SUBAGENTS** — even for 2-3 slides. You've been staring at the code and will see what you expect, not what's there. Subagents have fresh eyes.

Convert slides to images (see [Converting to Images](#converting-to-images)), then use this prompt:

```
Visually inspect these slides for user-visible defects AND AI-deck slop.

Check for AI-deck slop FIRST:
- Box density: count outlined containers on each content slide. More than 2-3 per slide is slop.
- Tall stacked headers: is the header strip occupying >0.9" with eyebrow + giant headline + right tag? That's slop.
- Equal-weight stat grids: are 4 stats sized identically with identical containers? Apply hierarchy.
- Pull-quotes in pitch context: italic Georgia editorial typography in a commercial pitch is wrong tone.
- Internal-language footers: "user prompt", "generated", placeholder names.
- Fabricated stats: margins, percentages, market sizes that weren't in the source material.

Then check standard defects:
- Overlapping elements (text through shapes, lines through words, stacked elements)
- Text overflow or cut off at edges/box boundaries
- Decorative lines positioned for single-line text but title wrapped to two lines
- Source citations or footers colliding with content above
- Elements too close (< 0.3" gaps) or cards/sections nearly touching
- Uneven gaps (large empty area in one place, cramped in another)
- Insufficient margin from slide edges (< 0.5")
- Columns or similar elements not aligned consistently
- Low-contrast text (e.g., light gray text on cream-colored background)
- Low-contrast icons (e.g., dark icons on dark backgrounds without a contrasting circle)
- Text boxes too narrow causing excessive wrapping
- Leftover placeholder content

For each slide, list user-visible issues in priority order (slop first, defects second). Skip sub-pixel positioning and cosmetic nitpicks a viewer wouldn't notice.

Read and analyze these images — run `ls -1 "$PWD"/slide-*.jpg` and use the exact absolute paths it prints:
1. <absolute-path>/slide-N.jpg — (Expected: [brief description])
2. <absolute-path>/slide-N.jpg — (Expected: [brief description])
...
```

### Verification Loop

1. Generate slides → Convert to images → Inspect
2. **Check box density first** — count outlined containers per slide. If any content slide has more than 3, that slide needs restructuring before you fix anything else.
3. **Check text bounds second** — for every text box, confirm the rendered text fits inside its shape. Overflow is the most common defect and is always user-visible.
4. List any other issues found
5. Fix issues, starting with box density (structural), then overflow (defect), then alignment (polish)
6. Re-verify only the affected slides
7. **Stop after one fix-and-verify cycle** unless a new *user-visible* defect appears (overlap, overflow, missing content). Do not loop on sub-pixel positioning, minor color tweaks, or issues a viewer wouldn't notice.

### Audience Pass (For Adapted Decks)

If you're adapting a deck for an external audience (e.g. an internal submission being shown to a buyer or investor), do an explicit pass for audience-appropriate content:

- Strip internal framing language ("submitted for review", "draft", placeholder names)
- Remove any data the audience shouldn't see (e.g. don't show a buyer their own margin)
- Re-read every footer and source line
- Check the cover and closing slides especially — these set tone

---

## Converting to Images

Convert presentations to individual slide images for visual inspection:

```bash
python scripts/office/soffice.py --headless --convert-to pdf output.pptx
rm -f slide-*.jpg
pdftoppm -jpeg -r 150 output.pdf slide
ls -1 "$PWD"/slide-*.jpg
```

**Pass the absolute paths printed above directly to the view tool.** The `rm` clears stale images from prior runs. `pdftoppm` zero-pads based on page count: `slide-1.jpg` for decks under 10 pages, `slide-01.jpg` for 10-99, `slide-001.jpg` for 100+.

**After fixes, rerun all four commands above** — the PDF must be regenerated from the edited `.pptx` before `pdftoppm` can reflect your changes.

---

## Dependencies

- `pip install Pillow` - thumbnail grids
- `npm install -g pptxgenjs` - creating from scratch
- LibreOffice (`soffice`) - PDF conversion (auto-configured for sandboxed environments via `scripts/office/soffice.py`)
- Poppler (`pdftoppm`) - PDF to images
