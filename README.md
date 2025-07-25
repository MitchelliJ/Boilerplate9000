# Boilerplate9000

This document outlines the intended workflow for using the guardrails prompts to build your application.

## Notes on setup_boilerplate.md

The included nodejs backend and astro frontend boilerplate is my preferred stack. You might need to move the Astro template selection to your manual terminal when executing this.
I recommend forking this repo and replacing it with boilerplate for your most used stack for new projects. It assumes Windows Powershell, please adjust if you are in iOS or Linux.


## 1. Define Project-Wide Guidelines

Use `set_coding_guidelines.md` to define your stack and make important choices for the project. These are things that are not specific to one feature, but encompass the whole application.

> **Note:** You could also scope out the entire application here with a comprehensive to-do list. However, I prefer to work on a per-feature basis.

## 2. Define Database Schema

Use `database_schema.md` to define your database schema. The reference file created will likely be a living document.

## 3. Create a Product Requirements Document (PRD)

Use `create_prd.md` for the feature you want to work on.

## 4. Generate Development Tasks

Use `generate_tasks.md` with the newly generated PRD to outline the development tasks. Make sure to review the generated tasks carefully.

## Miscellaneous Tips

- **Provide Context**: For best results, provide your AI assistant with relevant reference files (e.g., coding guidelines, database schema) at the start of each new conversation.
- **Separate Planning from Execution**: First, create detailed plans and reference materials. Then, instruct your AI assistant to execute the work based on those materials. Mixing planning and execution in a single prompt often leads to poor results.
- **Beware of Documentation Drift**: When using AI to update documentation, be mindful that it can drift away from the actual code over time. Regular manual reviews are recommended.
- Add Context7 MCP to your IDE if you are working with newer frameworks that LLM's have not learned to work with yet.

## Credits

This workflow is largely a personal evolution on the works of Harper Reed, Ryan Carson and David Dodda. You can find their work here:
- https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/ 
- https://github.com/snarktank/ai-dev-tasks (the YouTube video is worth watching)
- https://blog.daviddodda.com/most-ai-code-is-garbage-heres-how-mine-isnt

## Connect With Me

- 💼 [LinkedIn](https://www.linkedin.com/in/michielberk/)
- 🐦 [Bluesky](https://bsky.app/profile/michielberk.com)
- 🌐 [Personal Website](https://michielberk.com/)