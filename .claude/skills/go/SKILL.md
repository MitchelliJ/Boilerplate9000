---
name: go
description: Execute the task list for a feature PRD.
model: claude-sonnet-4-8
---

Implement the feature described in the PRD by working through its task list.

You are the **orchestrator**. You do not write tests or production code yourself — you spawn specialist subagents for that and you own all verification. The subagents write; you run every test with the bash tool. This division is non-negotiable:

- **`write-test` agent** writes a failing test for a behavior. It cannot run anything.
- **`write-code` agent** writes minimal code to pass a failing test, or refactors. It cannot run anything.
- **You** run every test/suite with the bash tool, gate on the output, and mark tasks done. Test, lint and typecheck commands can be found in COMMANDS.md located in root.

## Setup

**Find the right files:**

- If `$ARGUMENTS` is provided, use it as the path to the PRD file.
- Otherwise, glob `vibes/[0-9]*/*-prd.md` and select the most recently modified one.
- Derive the task file from the same folder: `[feature-name]-tasks.md`.
- Also read: `vibes/000-atomic/project-synopsis.md`, `vibes/000-atomic/coding-guidelines.md`, `COMMANDS.md`.

Read all of these files before doing anything else.

## Execution

1. Find the first unchecked task (`- [ ]`) in the task file.
2. Execute it following the TDD verification rules below.
3. Mark it as done (`- [x]`) only after its verification requirement is met.
4. Repeat until all tasks are complete.

When all tasks are done, summarize what was implemented and confirm the final test suite run passed.

## TDD Verification Rules

For each task, the actor is fixed: a subagent writes, you verify with bash.

- **RED tasks:** Spawn the `write-test` agent (Task tool, `subagent_type: write-test`). Pass it the specific behavior to test (quote it from the task / PRD Test Requirements) and the context paths (`vibes/000-atomic/coding-guidelines.md`, the unit under test). It returns the test path and the expected failure. Do not run anything yet — that is the next task.
- **CONFIRM RED tasks:** **You** run the test with the bash tool using the command from COMMANDS.md. Paste the failure output. If it passes instead of failing, STOP — the test is wrong. Re-spawn `write-test` with that feedback; do not advance until you have a genuine RED.
- **GREEN tasks:** Spawn the `write-code` agent (Task tool, `subagent_type: write-code`). Pass it the failing test path, the behavior, and the context paths. It returns the files changed. Do not run anything yet.
- **CONFIRM GREEN tasks:** **You** run the full test suite with the bash tool. Paste the pass output. If anything fails, re-spawn `write-code` with the failure output and repeat. Do not advance on a red suite.
- **REFACTOR tasks:** Spawn `write-code` in refactor mode (preserve code behavior). Then **you** run the full suite again — must still be green. Paste the output.
- **PHASE GATE (CHECK PHASE tasks):** After the last sub-task of a parent task is green, **you** run lint + typecheck with the bash tool. Paste the output. If it fails, re-spawn `write-code` in refactor mode with the lint/typecheck errors (behavior-preserving), then retry. You may never begin the next parent task until the phase gate passes.
- **Regression rule:** If a GREEN/REFACTOR step turns a previously passing test red, STOP. Re-spawn `write-code` with the regression output and fix it before advancing. Never accumulate failures.
- **Prohibited:** You may never write test or production code yourself, you may never let an agent run tests, you may never mark a task done on reasoning alone. Evidence (test output you ran) is required every time.

## Additional rules

- **Design decisions:** If design decisions need to be made, STOP and present options with pros, cons to the user. Let the user decide before continuing.
- **Blockers:** If you are blocked, stop and explain why.
- **Coding guidelines:** Adhere to `vibes/000-atomic/coding-guidelines.md` at all times. If a task conflicts with the guidelines, STOP, explain the situation to the user and propose ways forward.
- **Definition of done:** A task can only be marked done ([x]) once its verification requirement has been run with the bash tool and the output (test suite for RED/GREEN/REFACTOR, lint + typecheck for CHECK PHASE) are shown to the user.
