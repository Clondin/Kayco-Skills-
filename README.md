# KAYCO PowerPoint Skill

Codex skill for creating polished KAYCO-branded PowerPoint decks.

## What It Includes

- KAYCO purple-led presentation style guidance
- Bundled KAYCO logo asset
- Header, typography, layout, and imagegen rules
- PowerPoint compatibility verification expectations
- Reference guidance for AI-at-work training decks

## Skill Structure

```text
kayco-powerpoint/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── assets/
│   └── kayco-logo.png
└── references/
    └── brand-guide.md
```

## Install

Copy this folder into your Codex skills directory:

```powershell
Copy-Item -Recurse .\kayco-powerpoint $env:USERPROFILE\.codex\skills\
```

Then invoke it with:

```text
Use $kayco-powerpoint to create a polished KAYCO PowerPoint deck.
```
