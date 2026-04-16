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
2. Execute it following the TDD verification rules below.
3. Mark it as done (`- [x]`) only after its verification requirement is met.
4. Move to the next unchecked task without pausing.
5. Repeat until all tasks are complete.

When all tasks are done, summarize what was implemented and confirm the final test suite run passed.

## TDD Verification Rules

These rules are non-negotiable. Do not mark a task done without meeting its condition.

- **RED tasks (x.1):** Write the test. Do not run it yet — that is the next task.
- **CONFIRM RED tasks (x.2):** Run the test suite using the command from COMMANDS.md. Paste the failure output. If the test passes instead of failing, STOP — the test is wrong. Rewrite it before continuing.
- **GREEN tasks (x.3):** Write the minimum code needed to make the failing test pass. No extra logic.
- **CONFIRM GREEN tasks (x.4):** Run the full test suite. Paste the pass output. If anything fails, fix it before marking done. Do not advance.
- **REFACTOR tasks (x.5):** Clean code and tests. Run the suite again. Must still be green.
- **Regression rule:** If a GREEN step causes a previously passing test to fail, STOP. Fix the regression before advancing. Never accumulate failures.
- **Prohibited:** Marking any task done based on reasoning alone. Evidence (test output) required every time.

## Rules

- **Design decisions:** If design decisions need to be made, present options with pros, cons and expected complexity and let the user decide before continuing.
- **Blockers:** If you are genuinely blocked, stop and explain why.
- **Coding guidelines:** Adhere to `vibes/coding_guidelines.md` at all times. If a task conflicts with the guidelines, explain the situation to user and propose ways forward.
