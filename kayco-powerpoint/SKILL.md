---
name: kayco-powerpoint
description: Build or revise KAYCO-branded PowerPoint decks with the approved purple-led corporate style, bundled KAYCO logo, editable slide layouts, imagegen art-direction guidance, and desktop PowerPoint open/render verification. Use for KAYCO, kosher food company, AI-at-work, internal training, executive update, workshop, or presentation requests that need a polished .pptx.
---

# KAYCO PowerPoint

Use this skill when creating or improving a PowerPoint deck for KAYCO or a KAYCO internal audience.

## Core Workflow

1. Read `references/brand-guide.md` before designing or editing slides.
2. Use bundled logo assets from `assets/`:
   - `assets/kayco-logo.png`
3. Build editable PowerPoint content whenever possible:
   - Slide text, tables, callouts, bullets, labels, and diagrams should be native PowerPoint objects.
   - Use imagegen only for text-free art plates or atmospheric supporting visuals.
4. Make the output corporate polished, friendly, and practical.
5. Before final delivery, verify the `.pptx` opens in desktop PowerPoint. If it fails, rebuild with a more conservative PowerPoint export path before handing it off.

## Visual Direction

- Primary brand color: KAYCO purple `#9D257E`.
- Use the KAYCO logo in a consistent branded header unless the user asks otherwise.
- Prefer a clean full-width white or translucent header with the KAYCO logo on the left and slide name centered.
- Keep layouts spacious and premium; avoid decorative clutter, robots, brains, glowing circuits, and generic stock-photo styling.
- Use generated cover art as full-bleed when possible, with a purple readability panel or overlay for title text.
- For internal slides, prefer editable diagrams and large integrated visual plates over small pasted-in thumbnails.

## Imagegen Rules

Use `imagegen` for:

- Full-bleed cover art.
- Wide supporting visuals for demo, data, document-review, prompting, or guardrail slides.
- Text-free food-business or workflow imagery that adds atmosphere.

Do not ask imagegen for:

- KAYCO logos.
- Readable slide text, labels, numbers, charts, tables, citations, or UI copy.
- Robots, brains, glowing circuits, or fake brand marks.

Prompt images with:

- KAYCO purple `#9D257E`, deep plum, white, soft blush, pale lavender, subtle charcoal.
- Food-business context when relevant: unlabeled cartons, supplier documents, spreadsheets, checklists, routing lines.
- Calm negative space where editable slide text will sit.

## Content Tone

- Friendly and practical, not hype-driven.
- Explain concepts through concrete workplace examples.
- For warnings, include a grounded “what can go wrong” example.
- Avoid invented internal metrics. If presenter/title/use-case details are unknown, leave them neutral or ask the user.

## Verification

Always do at least one compatibility check before final delivery:

- Open the final `.pptx` with desktop PowerPoint through COM on Windows when available.
- If the file cannot be read, do not deliver it as final.
- If rendering previews, inspect for text clipping, image overlap, unreadable logos, and cramped cards.

Final response should link only to the final `.pptx` unless the user asks for previews or support files.
