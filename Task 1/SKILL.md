---
name: project-docs-generator
description: Generates a professional 3-file documentation package (README.md, PROMPTS.md, TOOLS.md) for an AI/skill project, ready to upload to GitHub. Use this skill whenever the user gives you raw project notes — bullet points on what they did, the prompts they used, which AI tools/apps they used, and/or screenshots — and asks for a README, project writeup, or documentation to put on GitHub/Git for a Claude skill, AI project, or automation they built. Trigger even if the user only gives partial input (e.g. just bullet points, or just prompts) and asks to "create the files," "generate the docs," "make a README for this," or similar.
---

# Project Docs Generator

Turns a user's raw project notes (bullet points, prompts, tool list, screenshots) into three polished, GitHub-ready Markdown files: `README.md`, `PROMPTS.md`, and `TOOLS.md`.

## When to use this

Use whenever the user wants to document an AI project, custom Claude skill, or automation they built for a portfolio, assignment, or GitHub repo — and gives you some combination of:
- Bullet points / notes describing what they did and how they verified it
- The prompt(s) they used (initial + revised)
- A list of AI tools/apps used
- Screenshots or a clip of the result

The input is often incomplete or messy — that's expected. Fill in what's given, use clean placeholders for what's missing, and never block on missing details unless truly nothing usable was provided.

## Output format

Always generate exactly three files, in this structure (note: the third file is `SCREENSHOT.md`, not `TOOLS.md` — tools info lives in the README's "Tools Used" table):

### 1. `README.md`
```markdown
# [Project / Skill Name]

> One-sentence summary of what this skill does and the problem it solves.

## Table of Contents
- [Overview](#overview)
- [What I Did](#what-i-did)
- [How I Verified It Worked](#how-i-verified-it-worked)
- [Tools Used](#tools-used)
- [Prompts](#prompts)
- [Screenshots / Demo](#screenshots--demo)
- [Repository Structure](#repository-structure)
- [Notes / Limitations](#notes--limitations)

---

## Overview
[Fill from user's notes]

## What I Did
[Numbered or bulleted steps from user's notes]

## How I Verified It Worked
[From user's notes on testing/verification]

## Tools Used
| Tool / App | Purpose |
|---|---|
| [from user's tool list] | [purpose, inferred or stated] |

## Prompts
See [`PROMPTS.md`](./PROMPTS.md) for the full initial prompt and any revised versions used during iteration.

## Screenshots / Demo
See [`SCREENSHOT.md`](./SCREENSHOT.md) for the screenshots/demo of this project.

## Repository Structure
\`\`\`
.
├── README.md
├── PROMPTS.md
├── SCREENSHOT.md
└── [skill-folder]/
\`\`\`

## Notes / Limitations
[Any caveats the user mentioned, or leave a short placeholder]
```

### 2. `PROMPTS.md`
```markdown
# Prompts

## Initial Prompt
\`\`\`
[user's first prompt]
\`\`\`
**Context:** [why phrased this way, if known]
**Result:** [what it produced, if known]

## Revision 1 (if applicable)
\`\`\`
[revised prompt]
\`\`\`
**What changed:** [describe]
**Result:** [describe]

## Final Prompt / Instructions Used
\`\`\`
[final version]
\`\`\`

## Key Takeaways
- [Any lessons the user shared about what worked/didn't]
```

### 3. `SCREENSHOT.md`
```markdown
# Screenshots / Demo

> Private/sensitive data has been redacted or blurred.

[For each uploaded screenshot, embed it using its actual uploaded filename/path — e.g. `![Step 1](<original-uploaded-filename>)` — with a one-line caption of what it shows. Do not copy images into a new folder or rename them. If no screenshots were provided, leave a single placeholder line instructing the user to add their own image before pushing to Git.]
```

## Process

1. **Collect input**: Read whatever the user gives you — bullet points, prompt text, tool names, screenshots (as images or descriptions). Don't ask for everything up front; work with what's provided in one pass.
2. **Map notes to sections**: Slot the user's actual content into the templates above. Never invent specifics (fake tool names, fake results, fake metrics) — use bracketed placeholders like `[details not provided]` only where genuinely nothing was given.
3. **Screenshots**: Claude cannot generate real screenshots, but if the user has uploaded actual image files, use them directly — do not copy, rename, or duplicate them into a new `screenshots/` folder or any other extra file. Embed each uploaded image in `SCREENSHOT.md` by referencing its original uploaded filename/path as-is, with a short caption describing what it shows. Only the three deliverable files (`README.md`, `PROMPTS.md`, `SCREENSHOT.md`) should be produced — no additional image copies or folders. If the user hasn't uploaded any images, leave a single placeholder line in `SCREENSHOT.md` instructing them to add their own image before pushing to Git.
4. **Redaction reminder**: Always keep the "private data redacted" note in `SCREENSHOT.md` — remind the user to blur/crop sensitive info before pushing publicly.
5. **Generate all three files** as separate downloadable Markdown files (`README.md`, `PROMPTS.md`, `SCREENSHOT.md`), not a single combined file, so they map directly onto a Git repo.
6. **Deliver**: Save files to the outputs directory and present them to the user for download.

## Notes
- Keep tone concise and professional — this is a portfolio/GitHub artifact, not a chat answer.
- If the user gives an updated/second round of notes later, regenerate the same three files rather than creating new variants.
