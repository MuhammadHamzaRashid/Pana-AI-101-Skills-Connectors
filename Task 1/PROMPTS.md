# Prompts

## Initial Prompt
```
README.md (top level) — your name, a short summary of the five projects, and which AI
tools/apps you used.
```
**Context:** Requested a top-level README summarizing five projects and the AI tools used.
**Result:** Claude asked for the missing specifics before drafting, since none had been provided yet.

## Revision 1
```
create dynamic skill for me for the above points set professional layout
```
**What changed:** Shifted the ask from "write the files once" to "build a reusable, professionally laid-out template."
**Result:** Claude produced three professional Markdown templates (README.md, PROMPTS.md, TOOLS.md) with placeholder sections. (Screenshot 1)

## Revision 2
```
create skill.md file for these to generate these files and using same layout like above files
i only give points screen shot and prompts
also save this skill in you so that i can use in future
```
**What changed:** Requested an actual Claude Skill (`SKILL.md`) that takes points, screenshots, and prompts as input and regenerates the same file layout automatically — installable for reuse in future chats.
**Result:** Claude wrote the SKILL.md, packaged it as `project-docs-generator.skill`, and explained how to save it via Claude.ai's Skills settings. (Screenshot 2)

## Revision 3
```
use project-docs-generator update this instead of Tools file name Screenshot only update skill
```
**What changed:** Requested renaming the third output file from `TOOLS.md` to `SCREENSHOT.md`, updating the skill definition only (not regenerating docs yet).
**Result:** Claude updated the SKILL.md and repackaged the `.skill` file. (Screenshot 3)

## Final Prompt / Instructions Used
```
no please update project-docs-generator skill to add screenshots in screenshot file no extra files
```
**What changed:** Requested the skill embed uploaded screenshots directly into SCREENSHOT.md by their original filenames, without copying them into a separate folder or creating extra files.
**Result:** Claude updated the SKILL.md accordingly and repackaged the skill.

## Key Takeaways
- Turning a one-off request into a reusable skill avoids re-explaining the same format in every new chat.
- Being specific about the exact file structure (3 files only, no extra folders) mattered for getting a clean, GitHub-ready output.
- Real chat screenshots, once uploaded, can be used directly as verification evidence in the docs without duplicating them into new files.
