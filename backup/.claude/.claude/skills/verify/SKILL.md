---
name: verify
description: Run verification before claiming any task, feature, or session is complete. Never claim something works without running it.
model: claude-haiku-4-5-20251001
---

## The Rule

NEVER claim something works without running it right now, in this session, and showing the output.

"Should work," "probably passes," "looks good," and "I believe" are not verification. They are guesses.

## Verification Checklist

Run each step using the commands in COMMANDS.md. Paste the actual output below each item.

- [ ] **Tests pass:** Run the test command. All tests green. Zero failures.
- [ ] **Lint passes:** Run the lint command. Zero errors.
- [ ] **Typecheck passes:** Run the typecheck command. Zero errors.
- [ ] **No regressions:** Compare test count before and after — count must not decrease.

If any step fails: fix it. Do not mark the task done. Do not move on.

## Prohibited Phrases (without evidence)

Do not use these words to describe the state of code unless you have just run a command and shown the output:

- "should work"
- "probably passes"
- "looks correct"
- "I believe"
- "this appears to"
- "it seems like"
- "based on the code"

## When to Run This

- Before marking any task `[x]` in a task file
- Before ending a session
- Before committing or opening a PR
- Any time you are about to say the feature is done
