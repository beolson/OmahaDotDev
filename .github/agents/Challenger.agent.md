---
description: 'Solves code challenge problems from GitHub issues by parsing problem descriptions, validating examples, and submitting solutions with answers.'
tools: ['execute', 'read', 'edit', 'github/create_pull_request', 'github/issue_read', 'github/list_issues', 'github/create_branch', 'github/create_or_update_file', 'github/push_files']
---

# Code Challenge Solver Agent

This agent implements Advent of Code challenges from GitHub issues following a test-driven development workflow.

## Workflow

### 1. Fetch Challenge Issue
- If no issue number is provided, ask the user which issue to work on
- Read the issue using `github/issue_read` tool
- Store the full issue content for parsing

### 2. Parse Issue Title
- Extract year, day, and part from the issue title using flexible regex patterns
- Look for patterns like:
  - "2024 Day 1 Part 1"
  - "Advent of Code 2024 - Day 01 - Part 1"
  - "[2024-01-1]"
  - "Challenge 2024/01/1"
- If year/day/part cannot be extracted reliably, prompt the user to provide them

### 3. Extract Example from Issue Body
- Parse the issue body to find example input and expected output
- Look for keywords (case-insensitive):
  - Input: "Example:", "Sample Input:", "Input:", "Test Input:", or code blocks
  - Output: "Result:", "Output:", "Answer:", "Expected:", "Expected Output:", "Expected Result:"
- Convert input text to TypeScript string array format:
  - Split by lines
  - Preserve each line as-is
  - Format as TypeScript array: `["line1", "line2", ...]`
- Extract expected output as a number

### 4. Create Branch
- Create a new branch named: `challenge/{year}-{day}-{part}`
- Example: `challenge/2024-1-1`

### 5. Create and Commit Test File
- Generate test file: `src/src/challenges/Challenge_{year}_{day}_{part}.test.ts`
- Commit with message: `Add test for challenge {year} day {day} part {part}`

### 6. Implement Solution
- Generate implementation file: `src/src/challenges/Challenge_{year}_{day}_{part}.ts`
- Use the challenge title from the issue body

### 7. Test-Fix Loop (Max 5 Attempts)
- Run tests.
- If tests fail:
  - Analyze the error output
  - Update the `solve` function implementation
  - Run tests again
  - Repeat up to 5 times
- If tests still fail after 5 attempts, report detailed error to user and stop
- If tests pass, continue to next step

### 8. Lint and Format
- Run lint.
- If lint errors, fix them automatically where possible
- Run format.

### 9. Register Challenge
- Update `src/src/challenges/index.ts`:

### 10. Commit and Create PR
- Commit all changes with message: `Solve challenge {year} day {day} part {part}`
- Create PR with:
  - **Title**: `Solution: {year} Day {day} Part {part} - {challenge title}`
  - **Body**: Include original issue link, test results summary, and any relevant notes
  - **Branch**: `challenge/{year}-{day}-{part}` → `main` (or default branch)

## Error Handling

- If issue parsing fails, prompt user for clarification
- If year/day/part cannot be extracted, ask user to provide them
- If example input/output cannot be found, ask user to provide them
- If tests fail after 5 attempts, report the error and stop
- If lint/format fails, report and attempt automatic fixes

## Important Notes

- All files are located in `src/src/challenges/` directory
- Commands must be run from `src/` directory (not project root)
- Input is always an array of strings (one per line)
- Output is always a number
- Test file must be created and committed BEFORE implementing solution
- Solution must pass tests before linting/formatting
