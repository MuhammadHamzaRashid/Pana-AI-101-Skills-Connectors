# MCP Builder Skill — Explanation & Safety Review

> A plain-English explanation of what the `mcp-builder` skill does, plus a safety review of whether it contacts external servers, handles credentials, or sends data anywhere unexpected.

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
This project documents a conversation asking Claude to explain the `mcp-builder` skill in plain English and flag anything sensitive about it (external contact, credential handling, unexpected data flow).

## What I Did
1. Asked Claude to explain, in plain English, exactly what the MCP builder skill does.
2. Asked Claude to flag anything sensitive — external server contact, credential handling, or unexpected data transmission.
3. Proposed a summary characterization of the skill ("used MCP for different applications... safe because it only fetches documentation from outside") for Claude to confirm or correct.
4. Received a correction: the skill itself is inert instructional documentation, not an active MCP application — it doesn't "use MCP" on its own. The actual MCP usage happens later, in whatever server gets built by *following* the guide.

## How I Verified It Worked
- Claude read the actual `mcp-builder` SKILL.md and reference files directly (rather than answering from general assumptions) before explaining it.
- Claude searched the skill's files specifically for credential/data-handling references before making safety claims — see Screenshot 3.
- The explanation matched the skill's real structure: a 5-step playbook (research, plan tools, build, test/review, create evaluations), confirmed against the actual file content — see Screenshots 1 and 2.
- Claude's correction was substantive, not just agreement: it distinguished between the skill (inert guide) and the servers it helps build (where actual credential handling would occur).

## Tools Used
| Tool / App | Purpose |
|---|---|
| Claude.ai (chat) | Read the mcp-builder skill file, explained it, performed the safety review, and corrected the user's summary |

## Prompts
See [`PROMPTS.md`](./PROMPTS.md) for the exact prompts used in this exchange.

## Screenshots / Demo
> Private/sensitive data has been redacted or blurred.

See [`SCREENSHOT.md`](./SCREENSHOT.md) for the screenshots of this conversation.

## Repository Structure
```
.
├── README.md
├── PROMPTS.md
└── SCREENSHOT.md
```

## Notes / Limitations
- This documents an explanatory/safety-review conversation, not a code build — there is no server or output artifact beyond the explanation itself.
- The correction made (skill vs. active application) is an important distinction for anyone reusing this skill: the SKILL.md file is passive instructions until acted on.
