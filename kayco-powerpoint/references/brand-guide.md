# KAYCO PowerPoint Brand Guide

Use this guide when the deck is for KAYCO, a KAYCO internal audience, a kosher food company context, a supplier conversation, an executive update, or a branded KAYCO presentation.

## Palette

- KAYCO purple: `#9D257E`
- Deep plum: `#4D0F41`
- Secondary plum: `#6D185C`
- Soft blush: `#F2B8DF`
- Pale lavender: `#F8ECF5`
- Warm pale background: `#FCF6FA`
- Ink: `#1A1A1A`
- Body: `#2B2B2B`
- Muted: `#6B6B6B`
- Hairline: `#E6C7DC`
- White: `#FFFFFF`

## Typography

- Preferred title font: `Poppins`
- Preferred body font: `Lato`
- Fallback title font: `Aptos Display` or `Georgia`
- Fallback body font: `Aptos` or `Calibri`

## Header System

Default content-slide header:

- Keep the header narrow, around 0.7 inches tall.
- Use the KAYCO logo at top left.
- Use one page name or section name, right-aligned in KAYCO purple.
- Avoid stacked eyebrow + headline + category-tag headers on every slide.
- Use a hairline divider only when it helps separate the header from dense content.

Cover slide:

- Full-bleed generated image or strong purple-led background when appropriate.
- Use a KAYCO purple panel or overlay only when needed for title readability.
- Keep the logo clear and do not place it over busy generated imagery.

Closing slide:

- Purple-led background is appropriate.
- A single direct closing line or action bar is enough.
- Keep the KAYCO logo visible unless the user asks for an unbranded close.

## Layout Patterns

- Use KAYCO purple for hero numbers, step circles, sparse anchors, and important call-to-action bars.
- Use white and pale lavender for quiet support areas, but do not turn every text block into a card.
- Use native PowerPoint shapes for diagrams, flow lines, document icons, spreadsheet/table icons, checkmarks, and lock/privacy markers.
- Prefer large integrated image plates, half-bleed visuals, or editable diagrams over tiny thumbnails.
- If using panels, use one or two soft-tinted grouping panels per slide, not a grid of equal outlined boxes.

## AI Training Deck Content Patterns

For "What an LLM is":

- Use a concrete next-word prediction example such as:
  `The capital of France is ___` -> likely next word `Paris`.
- Explain that it is pattern prediction, not a database lookup.
- Tie consequences to workplace implications.

For prompting:

- Show a worked example, not only a taxonomy.
- Map `Context`, `Task`, `Format`, and `Constraints` to real prompt sentences.

For guardrails:

- Pair each warning with a specific example of what can go wrong.
- Keep privacy guidance nuanced and tied to approved company tools/channels unless a current policy source is provided.

## Output Safety

- Do not invent internal usage numbers, savings, titles, margins, market sizes, category shares, or presenter credentials.
- Mark unknown fields as unconfirmed, or use TBD only when the user explicitly wants placeholders.
- Strip internal framing language when adapting internal material for an external audience.
- Re-check footers, source lines, and cover/closing slides for audience fit.
