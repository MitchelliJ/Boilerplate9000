---
name: go
description: Execute the task list for a feature PRD.
model: claude-sonnet-4-6
---

Implement the feature described in the PRD by working through its task list.

## Setup

**Find the right files:**
- If `$ARGUMENTS` is provided, use it as the path to the PRD file.
- Otherwise, glob `vibes/*/prd-*.md` and select the most recently modified one.
- Derive the task file from the same folder: `to-do-prd-[feature-name].md`.
- Also read: `vibes/spec-*.md`, `vibes/coding_guidelines.md`, `COMMANDS.md`.

Read all of these files before doing anything else.

## Execution

1. Find the first unchecked task (`- [ ]`) in the task file.
2. Implement it fully, following the coding guidelines at all times.
3. Mark it as done by updating `- [ ]` to `- [x]` in the task file.
4. Move to the next unchecked task without pausing.
5. Repeat until all tasks are complete.

When all tasks are done, summarize what was implemented.

## Rules

- **Design decisions:** If design decisions need to be made, present options with pros and cons and let the user decide before continuing.
- **Blockers:** If you are genuinely blocked, stop and explain why.
- **Coding guidelines:** Adhere to `vibes/coding_guidelines.md` at all times. If a task conflicts with the guidelines, explain the situation to user and propose ways forward.
