---
name: tdd
description: Drive implementation of a single unit through strict RED-GREEN-REFACTOR. Use when implementing a specific function, class, or module interactively.
model: claude-sonnet-4-6
---

The unit to implement: $ARGUMENTS

## The Iron Law

NO PRODUCTION CODE BEFORE A FAILING TEST.

If code was written before a test existed: delete it entirely. Do not keep it as reference. Start from RED.

## The Cycle

### RED

1. Write the smallest possible test that demonstrates one desired behavior.
2. The test must be specific: one behavior, one assertion.
3. Run the test suite (use COMMANDS.md). It **must fail**.
4. Show the failure output.
5. If it passes: the test is wrong or the behavior already exists. Investigate and rewrite the test before continuing.

### GREEN

6. Write the minimum code to make **only this test** pass. No extra logic, no handling of future cases.
7. Run the full test suite. **All** tests must pass — not just the new one.
8. Show the pass output.
9. If other tests break: fix the regression before advancing.

### REFACTOR

10. Clean up code and test for clarity. No behavior changes.
11. Run the full test suite. Still green.
12. Show pass output.

### Repeat

Return to RED for the next behavior. One behavior per cycle.

## Red Flags — Stop and Restart if You Notice These

These are the rationalizations that break TDD. If you catch yourself thinking any of these, stop, delete what was written, and restart from RED:

- "It's too simple to need a test"
- "I'll add the test after, it's basically done"
- "Let me just sketch the implementation first"
- "This test is hard to write so I'll test it manually"
- "I already know this works"
- "The test is obvious, I can skip seeing it fail"
- "I'll write tests at the end when the feature is stable"

## Completion Criteria

A unit is complete when:

- [ ] Every behavior has a corresponding test written before its implementation
- [ ] Every test was observed failing before implementation
- [ ] Every test passes after minimal implementation
- [ ] No other tests were broken
- [ ] Code and tests have been refactored and are still green
- [ ] Final full suite run output is shown
