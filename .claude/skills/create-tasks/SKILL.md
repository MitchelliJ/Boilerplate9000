---
name: create-tasks
description: Generate a detailed task list from a feature PRD so the work can be handed of to a junior developer
model: claude-sonnet-4-6
---

Generate a detailed task list from a feature PRD so a junior developer can implement this using test driven development.

## Process

1. **Locate files:** Read `vibes/000-atomic/project-synopsis.md` and `vibes/000-atomic/coding-guidelines.md` for context. Ask the user for the path if missing.
2. **Analyze PRD:** Read the provided PRD in its feature folder `vibes/[NNN]-[feature-name]/` to understand the requirements. Ask the user for the path if missing.
3. **Generate complete task list:** Produce all parent tasks/phases and their sub-tasks.
4. **Identify Relevant Files:** List all files that will need to be modified or created.
5. **Save:** Write the task list to the same folder as the PRD, named `[feature-name]-tasks.md` (e.g.: if PRD is at `vibes/001-project-initialization/project-initialization-prd.md`, save to `vibes/001-project-initialization/project-initialization-tasks.md`)

## Important rules

1. Task list should be unambiguous. Following it should automatically adhere to coding guidelines at all times.
2. Each task is prepended by a checkbox to monitor progress
3. A test driven design approach following RED -> GREEN -> REFACTOR should be followed at all times. If it is sensible to break this pattern, STOP and ask consent to the user.
4. Test tasks (CONFIRM RED and CONFIRM GREEN) should always be verified with the bash tool. This step must be an explicit task in the task list.
5. Every parent task ends with a CHECK PHASE sub-task that runs lint + typecheck with the bash tool.
6. Order the tasks according to build dependencies so they can be implemented sequentially.
7. A test should be scoped to a single behavior.
8. Acceptance criteria are usually one unit of assertion within a test.
9. If the user needs to take manual steps (such as entering DNS-records or provisioning a server), the task becomes to provide clear instructions to the user.

## Output structure

```markdown
# Relevant Files

- `path/to/file.ts` - Brief description of why this file is relevant
- `path/to/file.test.ts` - Unit tests for [feature]

# Tasks

- [ ] 1.0 [Example feature Name]
  - [ ] 1.1 RED: Write failing unit test(s) with the write-test agent for [specific behavior from PRD Test Requirements]
  - [ ] 1.2 CONFIRM RED: Run test with bash tool — verify 1.1 fails with expected error
  - [ ] 1.3 GREEN: Implement minimal code to make test(s) pass with the write-code agent
  - [ ] 1.4 CONFIRM GREEN: Run test with bash tool — verify all tests pass
  - [ ] 1.5 REFACTOR: Clean up code without changing behavior; CONFIRM GREEN by running test with bash tool
  - [ ] 1.6 CHECK PHASE: Run lint + typecheck with bash tool.
- [ ] 2.0 [Another feature Name]
  - [ ] 2.1 RED: Write failing unit test(s) with the write-test agent for [specific behavior from PRD Test Requirements]
  - [ ] 2.2 CONFIRM RED: Run test with bash tool — verify 2.1 fails with expected error
  - [ ] 2.3 GREEN: Implement minimal code to make test(s) pass with the write-code agent
  - [ ] 2.4 CONFIRM GREEN: Run test with bash tool — verify all tests pass
  - [ ] 2.5 REFACTOR: Clean up code with the write-code agent without changing behavior; CONFIRM GREEN by running test with bash tool
  - [ ] 2.6 CHECK PHASE: Run lint + typecheck with bash tool.
- [ ] N.0 Final: Run full test suite + lint + typecheck — all must pass. If not all tests pass, STOP and notify user what we could have done differently in the PRD-phase to prevent this block.
- [ ] Commit message: When done, include a one sentence functional description of the change.
```
