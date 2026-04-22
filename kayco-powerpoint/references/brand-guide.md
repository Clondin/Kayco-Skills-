# KAYCO PowerPoint Brand Guide

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

Default header for most slides:

- Height around 12 percent of slide height.
- White or translucent white full-width band.
- KAYCO logo at top left.
- Optional thin accent rule or small label to the right of the logo.
- Slide name centered in KAYCO purple.
- Section label at top right in muted gray.

Cover slide:

- Full-bleed generated image background.
- Same header system unless the user asks for a cleaner cover.
- Left-side KAYCO purple panel or overlay for title readability.

Closing slide:

- Purple-led background.
- Keep header with the KAYCO logo unless the user asks otherwise.
- Large simple `Questions.` or equivalent closing message.

## Layout Patterns

- Use full-width purple title bands for section framing.
- Use white or pale-lavender rounded cards for content.
- Use vertical purple strips or large numerals for hierarchy.
- Use native PowerPoint shapes for diagrams:
  - cards
  - flow lines
  - document icons
  - spreadsheet/table icons
  - checkmarks
  - lock/privacy markers
- Avoid tiny image thumbnails. If using generated art, make it a large integrated side plate or background.

## AI Training Deck Content Patterns

For “What an LLM is”:

- Use a concrete next-word prediction example such as:
  `The capital of France is ___` -> likely next word `Paris`.
- Explain that it is pattern prediction, not a database lookup.
- Tie consequences to workplace implications.

For prompting:

- Show a worked example, not only a taxonomy.
- Map `Context`, `Task`, `Format`, and `Constraints` to real prompt sentences.

For guardrails:

- Pair each warning with a specific example of what can go wrong.
- Keep privacy guidance nuanced and tied to approved company tools.

## Output Safety

- Do not invent internal usage numbers, savings, titles, or presenter credentials.
- Mark unknown fields as TBD only if the user wants placeholders.
- Prefer “approved tools/channels” wording for privacy unless a current policy source is provided.
