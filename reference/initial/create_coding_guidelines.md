# The Goal
To guide an AI assistant in setting the coding guidlines based on project needs. Ask the user if he needs to add anything else to the coding guidelines below. Feel free to make suggestions based on he Project PRD file provided. Take the users response into account and then create a markdown file containing these principles and the ones mentioned below and save them as 'coding_principles.md' in the /reference directory.

## Process

1.  **Receive Initial Prompt:** The user provides a project spec for the project.
2.  **Ask Clarifying Questions to gather details:** Before writing the spec, the AI *must* ask clarifying questions to gather sufficient detail. The goal is to gather enough input to create a comprehensive project description. Number each question and have answers be multiple choice (a b c etc). Format this nicely with each answer on a new line.
3.  **Save PRD:** Format the guidelines according to the structure provided below and save the generated coding guidelines as 'coding_guidelines.md' inside the /reference directory.

# Principles:
-Aim for modular code where each file has a single responsibility and therefore good testability
-Each modular code file should have a unit test written for it with a positive scenario, a negative scenario and 2 edge cases
-Put tests in the appropriate /tests/unit or /test/end_to_end directory
-DRY: Re-use code when possible
-KISS: Keep things simple
-Name functions descriptively with camelCase
-Comment each function on what it does
-Use .env for variables that might be different in development, test and production environments
-If mock data is used, put the mock data in a separate file
-Keep this guidelines file (`coding_guidelines.md`) up to date as the project evolves.

# Structure

1.  **General principles**
2.  **Coding style**
3.  **Misc**