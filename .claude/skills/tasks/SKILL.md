---
name: tasks
description: Generate a detailed task list from a feature PRD.
model: claude-sonnet-4-6
---

Generate a detailed task list from a feature PRD for a junior developer to implement.

## Process

1. **Locate files:** Ask the user for the path to the PRD if not provided. Always read `vibes/coding-guidelines.md` (ask if missing).
2. **Analyze PRD:** Read and analyze the PRD to understand the feature requirements.
3. **Analyze Coding Guidelines:** Adhere to coding guidelines at all times. If there are conflicts, inform the user.
4. **Generate complete task list:** Produce all parent tasks/phases and their sub-tasks.
5. **Identify Relevant Files:** List all files that will need to be modified or created.
6. **Save:** Write the task list to the same folder as the PRD, named `to-do-prd-[feature-name].md`.
   - Example: if PRD is at `vibes/1. Project initialization/prd-project-initialization.md`, save to `vibes/1. Project initialization/to-do-prd-project-initialization.md`

## Output structure

Each feature block follows strict RED → GREEN → REFACTOR order. Tests are written before implementation, always.

```markdown
# Relevant Files

- `path/to/file.ts` - Brief description of why this file is relevant
- `path/to/file.test.ts` - Unit tests for [feature]

# Tasks

- [ ] 1.0 [Feature Name]
  - [ ] 1.1 RED: Write failing unit test(s) for [specific behavior from PRD Test Requirements]
  - [ ] 1.2 CONFIRM RED: Run test suite — verify 1.1 fails with expected error
  - [ ] 1.3 GREEN: Implement minimal code to make test(s) pass — nothing more
  - [ ] 1.4 CONFIRM GREEN: Run test suite — verify all tests pass
  - [ ] 1.5 REFACTOR: Clean up code and tests without changing behavior; confirm still GREEN
- [ ] 2.0 [Feature Name]
  - [ ] 2.1 RED: Write failing unit test(s) for [specific behavior]
  - [ ] 2.2 CONFIRM RED: Run test suite — verify 2.1 fails with expected error
  - [ ] 2.3 GREEN: Implement minimal code to make test(s) pass
  - [ ] 2.4 CONFIRM GREEN: Run test suite — verify all tests pass
  - [ ] 2.5 REFACTOR: Clean up; confirm still GREEN
- [ ] N.0 Final: Run full test suite + lint + typecheck (COMMANDS.md) — all must pass, if not notify user what we could have done differently in the PRD-phase to prevent this block.

# Notes

**IRON LAW:** No implementation task may begin until the RED task has been confirmed failing.
**IRON LAW:** No task is marked done until the test suite has been run and output confirmed.
**Never** defer tests to "later" — if a behavior matters, it has a test now.
The location where the tests should be saved is specified in the coding-guidelines.md.
If the user needs to take manual steps (such as entering DNS-records or editting Github-Actions), the task becomes to provide clear instructions to the user.
When done, include a suggestion for a commit message in the message to the user that clearly represents the done work.
```
