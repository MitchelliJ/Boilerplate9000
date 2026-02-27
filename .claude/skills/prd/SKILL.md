---
name: prd
description: Generate a Product Requirements Document (PRD) for a feature.
model: claude-opus-4-6
---

The feature to build: $ARGUMENTS

## Process

1. **Receive feature description:** Use `$ARGUMENTS` as the initial feature description. If empty, ask the user to describe the feature.
2. **Ask Clarifying Questions:** Ask questions covering these areas (adapt to the feature — provide lettered/numbered options for easy responses).
3. **Generate PRD:** Using the answers, write the full PRD following the structure below.
4. **Save:** Create the folder `vibes/[N]. [Feature Name]/` (N = feature number from spec) and save as `prd-[feature-name].md` inside it. Create the folder if it doesn't exist.

## PRD Structure

1. **Introduction/Overview** — Feature summary, problem it solves, goal
2. **Goals** — Specific, measurable objectives
3. **User Stories** — (As a [user], I want to [action] so that [benefit])
4. **Functional Requirements**
5. **Technical Requirements (if any)**
6. **Non-Goals (Out of Scope)** — Explicit exclusions to manage scope
7. **Open Questions** — Remaining unknowns needing clarification

The PRD should be clear, concise, actionable, and suitable for a junior developer to understand and implement this feature.

**IMPORTANT:** Only create unit tests when specifically asked for.
