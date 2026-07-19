# Gmail Connector Integration — AWS Email Verification (Claude + Gmail)

> Connecting Claude to Gmail via the connector system and verifying the connection by fetching real, recent AWS-related emails.

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
This project documents connecting Claude to a Gmail account through Anthropic's connector system, and verifying that the connection returns real, current inbox data by fetching the last 2 AWS-related emails.

## What I Did
1. Connected Gmail to Claude via the connector system.
2. Asked Claude to fetch the last 2 AWS-related emails from the inbox.
3. Verified the connection was genuine by checking that actual AWS-related emails were returned (not placeholder or fabricated content).
4. Recorded the real email content below as proof of verification.
5. The `project-docs-generator` skill was automatically triggered by Claude for this task, without being explicitly named — confirming the skill activates on its own when the context matches (as shown in the screenshot).

## How I Verified It Worked
Claude searched the connected Gmail inbox and returned these two actual, most recent AWS-related emails:

**1. "AWS Certification wants to hear from you"**
- From: do-not-reply@certmetrics.com
- Date: July 19, 2026
- Preview: Congratulations on achieving the AWS Certified Solutions Architect - Associate certification, with a request for feedback on the certification experience.

**2. "Congratulations on recertifying your AWS Certification!"**
- From: do-not-reply@certmetrics.com
- Date: July 12, 2026
- Preview: Confirmation of successfully recertifying the AWS Certified Solutions Architect - Associate certification, valid through July 11, 2029.

Both emails are real, dated, and sender-verified results pulled directly from the connected inbox — confirming the Gmail connector is genuinely live rather than returning generic or fabricated output.

## Tools Used
| Tool / App | Purpose |
|---|---|
| Claude.ai (chat) | Requested the task and reviewed the results |
| Gmail connector (via Claude.ai connectors) | Searched the inbox and returned real AWS-related email data |

## Prompts
See [`PROMPTS.md`](./PROMPTS.md) for the exact prompt used to connect Gmail and fetch the AWS-related emails.

## Screenshots / Demo
> Private/sensitive data has been redacted or blurred.

See [`SCREENSHOT.md`](./SCREENSHOT.md) for the screenshot of this project.

## Repository Structure
```
.
├── README.md
├── PROMPTS.md
└── SCREENSHOT.md
```

## Notes / Limitations
- Verification here relies on cross-checking that the returned emails are real, dated, and sender-specific — not generic placeholder text.
- Only 2 emails specifically about AWS certification were found as the most recent AWS-related messages; other search matches were unrelated (job alerts, newsletters) and were excluded from the verification set.
