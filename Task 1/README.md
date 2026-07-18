# Project Docs Generator (Claude Skill)

> A Claude skill that turns raw project notes (points, prompts, tools, screenshots) into a ready-to-upload GitHub documentation package: README.md, PROMPTS.md, and SCREENSHOT.md.

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
This project is a custom Claude skill (`project-docs-generator`) built to automatically generate a professional 3-file documentation package for AI/skill projects, so they can be uploaded straight to GitHub without manually writing a README each time.

## What I Did
1. Asked Claude to generate a professional README/PROMPTS/TOOLS layout for documenting an AI project.
2. Had Claude turn that layout into a reusable **Claude Skill** (`SKILL.md`) so the same output format could be triggered automatically in future chats.
3. Had Claude package the skill into an installable `.skill` file for upload via Claude.ai's Settings → Capabilities → Skills.
4. Requested the third output file be renamed from `TOOLS.md` to `SCREENSHOT.md`, folding tools info into the README's own Tools Used table.
5. Requested the skill embed uploaded screenshots directly, with no extra copied files or folders.

## How I Verified It Worked
- Confirmed the skill's generated file layout (README/PROMPTS/SCREENSHOT) matched the requested professional format — see Screenshot 1.
- Confirmed the `.skill` file packaged successfully after the SKILL.md was written — see Screenshot 2.
- Confirmed the rename from `TOOLS.md` to `SCREENSHOT.md` was applied and the skill repackaged — see Screenshot 3.

## Tools Used
| Tool / App | Purpose |
|---|---|
| Claude.ai (chat) | Designed the doc layout, authored the SKILL.md, packaged the skill, and generated the final files |

## Prompts
See [`PROMPTS.md`](./PROMPTS.md) for the full sequence of prompts used to build this skill.

## Screenshots / Demo
> Private/sensitive data has been redacted or blurred.

See [`SCREENSHOT.md`](./SCREENSHOT.md) for the screenshots of this project in action.

## Repository Structure
```
.
├── README.md
├── PROMPTS.md
├── SCREENSHOT.md
└── project-docs-generator/
    └── SKILL.md
```

## Notes / Limitations
- The skill must be installed via Claude.ai's Skills settings (or by uploading the `.skill` file) before it can be invoked by name in future chats.
- Screenshots shown were captured and uploaded by the user directly — Claude cannot capture chat screenshots itself.
