---
applyTo: "src/src/challenges/**"
---

# Advent of Code Challenge Implementation Guide

This guide explains how to implement and register new Advent of Code challenge solutions in this workspace.

## File Naming Convention

**CRITICAL:** Challenge files must follow this exact naming pattern:

- **Implementation file:** `Challenge_{year}_{day}_{part}.ts`
- **Test file:** `Challenge_{year}_{day}_{part}.test.ts`

**Examples:**
- `Challenge_2024_01_1.ts` (Year 2024, Day 1, Part 1)
- `Challenge_2024_01_2.ts` (Year 2024, Day 1, Part 2)
- `Challenge_2024_25_1.ts` (Year 2024, Day 25, Part 1)

**Important:** The `year`, `day`, and `part` properties in your implementation MUST match the values in the filename.

## Step 1: Implement the IChallenge Interface

Every challenge must implement the `IChallenge` interface, which requires five properties:

```typescript
interface IChallenge {
	year: number;        // The Advent of Code year (e.g., 2024)
	day: number;         // The day of the challenge (1-25)
	part: number;        // The part of the challenge (1 or 2)
	title: string;       // A descriptive title for the challenge
	solve: (input: Array<string>) => number;  // The solution function
}
```

### Key Points:
- The `solve` function receives puzzle input as an **array of strings** (one string per line of input)
- The `solve` function must return a **number** (the answer to the puzzle)
- The `year`, `day`, and `part` values MUST match the filename

### Implementation Example:

Create a file named `Challenge_2024_01_1.ts`:

```typescript
import type { IChallenge } from "./IChallenge";

const Challenge_2024_01_1: IChallenge = {
	year: 2024,
	day: 1,
	part: 1,
	title: "Historian Hysteria - Part 1",
	solve: (input: Array<string>): number => {
		// Your solution logic here
		// Parse the input array and solve the puzzle
		
		// Example implementation:
		let result = 0;
		for (const line of input) {
			// Process each line
			// ... your logic ...
		}
		return result;
	},
};

export { Challenge_2024_01_1 };
```

## Step 2: Create a Test File (MANDATORY)

**Every challenge MUST have a corresponding test file, and all tests MUST pass before the implementation is considered complete.**

Test data will be provided in the prompt when you're asked to implement a challenge.

### Test File Example:

Create a file named `Challenge_2024_01_1.test.ts`:

```typescript
import { expect, test } from "vitest";
import { Challenge_2024_01_1 } from "./Challenge_2024_01_1";

test("Challenge Day 1 Part 1 should solve the sample test", () => {
	// Test data will be provided in the prompt
	const input = [
		"line1",
		"line2",
		"line3"
	];
	
	// Expected result will be provided in the prompt
	expect(Challenge_2024_01_1.solve(input)).toBe(expected_answer);
});
```

### Testing Requirements:
- Use Vitest framework (`import { expect, test } from "vitest"`)
- Test description format: `"Challenge Day {day} Part {part} should solve the sample test"`
- Import the challenge object and call its `solve` method
- All tests MUST pass before the challenge is considered complete

## Step 3: Register the Challenge in index.ts

After creating your implementation and test files, you MUST register the new challenge in `index.ts`. This requires TWO steps:

### 3a. Add the Import Statement

Add an import at the top of the file:

```typescript
import { Challenge_2024_01_1 } from "./Challenge_2024_01_1";
```

### 3b. Add to the ChallengesIndex Array

Add your challenge to the `ChallengesIndex` array:

**Before:**
```typescript
import { Challenge00 } from "./Challenge00";
import { Challenge01 } from "./Challenge01";
import type { IChallenge } from "./IChallenge";

const ChallengesIndex: Array<IChallenge> = [Challenge00, Challenge01];

export { ChallengesIndex };
```

**After:**
```typescript
import { Challenge00 } from "./Challenge00";
import { Challenge01 } from "./Challenge01";
import { Challenge_2024_01_1 } from "./Challenge_2024_01_1";
import type { IChallenge } from "./IChallenge";

const ChallengesIndex: Array<IChallenge> = [
	Challenge00,
	Challenge01,
	Challenge_2024_01_1
];

export { ChallengesIndex };
```

## Completion Checklist

Before considering a challenge complete, verify:

- [ ] Created `Challenge_{year}_{day}_{part}.ts` with:
  - Correct filename matching year/day/part
  - Implements `IChallenge` interface
  - `year`, `day`, and `part` properties match the filename
  - `solve` function handles array of strings input and returns a number
  - Named export of the challenge object

- [ ] Created `Challenge_{year}_{day}_{part}.test.ts` with:
  - Correct filename matching the implementation file
  - Imports from Vitest and the challenge file
  - Test case using provided sample data
  - **All tests pass**

- [ ] Updated `index.ts` with:
  - Import statement for the new challenge
  - Challenge added to `ChallengesIndex` array

- [ ] All tests pass (verify before completing)

## Summary

To implement a new challenge:
1. Create `Challenge_{year}_{day}_{part}.ts` implementing `IChallenge`
2. Create `Challenge_{year}_{day}_{part}.test.ts` with passing tests
3. Update `index.ts` with import and array entry
4. Verify all tests pass