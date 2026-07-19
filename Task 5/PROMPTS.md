# Prompts

## Initial Prompt
```
explain, in plain English, exactly what the MCP builder skill does.
```
**Context:** Wanted a clear, non-technical explanation of what the `mcp-builder` skill covers.
**Result:** Claude read the actual SKILL.md and explained it as a 5-step playbook (research the API/protocol, plan tools, build the server, test/review, create evaluations) for building MCP servers — not something that acts on its own. (Screenshots 1–2)

## Revision 1
```
flag anything sensitive: does it contact any external server, handle credentials, or send
your data anywhere unexpected?
```
**Context:** Requested an explicit safety/privacy review of the skill.
**Result:** Claude searched the skill's files for credential and data-handling references, then reported that the skill file itself only fetches public documentation (read-only) and doesn't transmit user data; any real credential handling would occur in servers built by following the guide, not in the skill itself. (Screenshot 3)

## Final Prompt / Instructions Used
```
this skill used MCP for different applications and it is safe and because its only fetching
documentation from outside
```
**Context:** User proposed a summary of the skill for Claude to confirm.
**Result:** Claude confirmed the safety conclusion but corrected the characterization — the skill doesn't "use MCP for different applications" itself; it's inert instructional documentation. The actual use of MCP happens afterward, in whatever server a person builds by following the guide.

## Key Takeaways
- A skill file (SKILL.md) is passive instructions, not an active integration — worth distinguishing clearly when documenting what a skill "does."
- Verifying safety claims by actually searching the skill's file contents (rather than assuming) produces a more trustworthy answer.
- Corrections to a user's summary should be specific about what changed and why, not just a blanket confirmation.
