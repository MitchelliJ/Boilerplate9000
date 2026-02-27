---
name: tasks
description: Generate a detailed task list from a feature PRD.
model: claude-sonnet-4-6
---

Generate a detailed task list from a feature PRD for a junior developer to implement.

## Process

1. **Locate files:** Ask the user for the path to the PRD if not provided. Always read `vibes/coding_guidelines.md` (ask if missing).
2. **Analyze PRD:** Read and analyze the PRD to understand the feature requirements.
3. **Analyze Coding Guidelines:** Adhere to coding guidelines at all times. If there are conflicts, inform the user.
4. **Generate complete task list:** Produce all parent tasks/phases and their sub-tasks.
5. **Identify Relevant Files:** List all files that will need to be modified or created.
6. **Save:** Write the task list to the same folder as the PRD, named `to-do-prd-[feature-name].md`.
   - Example: if PRD is at `vibes/1. Project initialization/prd-project-initialization.md`, save to `vibes/1. Project initialization/to-do-prd-project-initialization.md`

## Output structure

```markdown
# Relevant Files

- `path/to/file.ts` - Brief description of why this file is relevant

# Tasks

- [ ] 1.0 Parent Task Title
  - [ ] 1.1 Sub-task description
  - [ ] 1.2 Sub-task description
- [ ] 2.0 Parent Task Title
  - [ ] 2.1 Sub-task description

# Notes

**IMPORTANT:** The second last task must always be to run any configured lint, typecheck and test commands outlined in COMMANDS.md.
**IMPORTANT:** The last task must always be instructions to the user to manually test and / or verify if the implementation was successful. If deemed useful these manual tests could be converted into automated tests later.