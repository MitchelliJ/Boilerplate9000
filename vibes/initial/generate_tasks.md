## The goal
To guide an AI assistant in creating a detailed, step-by-step task list based on an existing PRD. The task list will be handed off to a junior developer for implementation. It is required to be formatted in markdown and saved to the /reference directory in the root of the project with the filename 'to-do-[prd-file-name].md' (e.g., 'to-do-banking-app-prd.md').

## The process
1.  **Receive PRD Reference:** The user points the AI to a specific PRD file and Coding Guidelines file. Ask for these if one is missing
2.  **Analyze PRD:** The AI reads and analyzes the Project Description, Users, User Stories, Main Screens, Feature List and Other Requirements
3.  **Analyze Coding Guidelines:** The AI reads and analyses the Coding Guidelines
3.  **Phase 1: Generate Parent Tasks:** Based on the PRD analysis and Coding Guidelines, create the file and generate the high-level tasks required in order to complete the project. Present these tasks to the user in the specified format (without sub-tasks yet). Inform the user you have generated the high-level tasks based on the PRD and Coding Guidelines. Then ask if the user is ready to generate the sub-tasks.
4.  **Wait for Confirmation:** Pause and wait for the user to confirm.
5.  **Phase 2: Generate Sub-Tasks:** Once the user confirms, break down each parent task into smaller, actionable sub-tasks necessary to complete the parent task. Ensure sub-tasks cover the implementation details implied by the PRD and adhere to Coding Guidelines.
6.  **Identify Relevant Files:** Based on the tasks and PRD, identify potential files that will need to be created or modified. List these under the `Relevant Files` section.
7.  **Generate Final Output:** Combine the parent tasks, sub-tasks, relevant files, and notes into the final Markdown structure
8.  **Save Task List:** Save the generated document in the /reference directory with the filename 'to-do-[prd-file-name].md' (e.g., 'to-do-banking-app-prd.md')
9.  **Wait for Confirmation:** Pause and wait for the user to respond with "Go" before implementing the steps

## The structure
The generated task list must adhere to this structure:
```markdown
# Relevant Files

- `path/to/potential/file1.ts` - Brief description of why this file is relevant (e.g., Contains the main component for this feature).
etc

# Tasks

- [ ] 1.0 Parent Task Title
  - [ ] 1.1 [Sub-task description 1.1]
  - [ ] 1.2 [Sub-task description 1.2]
- [ ] 2.0 Parent Task Title
- [ ] 3.0 Parent Task Title
  - [ ] 3.1 [Sub-task description 3.1]
etc

# Notes
After completing a task, mark it as done.
```
