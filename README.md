# KAYCO Skills

A collection of Codex skills for KAYCO-related workflows, branding, internal tools, documents, and presentations.

## Skills

### `kayco-powerpoint`

Creates polished KAYCO-branded PowerPoint decks with the approved purple-led visual style, bundled KAYCO and KAYCO brand logos, editable slide layout guidance, imagegen art-direction rules, and PowerPoint compatibility checks.

## Repository Structure

Each skill should live in its own folder:

```text
Kayco-Skills-/
├── README.md
└── kayco-powerpoint/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── assets/
    │   ├── kayco-logo.png
    │   └── brand-logos/
    └── references/
        ├── brand-guide.md
        └── brand-logos.md
```

## Install A Skill

Copy the desired skill folder into your local Codex skills directory. For example:

```powershell
Copy-Item -Recurse .\kayco-powerpoint $env:USERPROFILE\.codex\skills\
```

Then invoke it by name:

```text
Use $kayco-powerpoint to create a polished KAYCO PowerPoint deck.
```

## Notes

- Keep each skill self-contained.
- Put brand assets under that skill’s `assets/` folder.
- Put longer reusable guidance under that skill’s `references/` folder.
- Avoid committing sensitive KAYCO data, private internal metrics, or confidential documents.
