> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Prompt Template

> Use this template when contributing new prompts to the library.

## Instructions

1. Copy this template to the appropriate category folder
2. Name the file descriptively (e.g., `unit-test-generation.md`, `sql-query-optimisation.md`)
3. Complete all required sections
4. Delete the instructions and optional sections you don't use
5. Submit via pull request following [contribution guidelines](../CONTRIBUTING.md)

---

## Template

Copy everything below this line:

---

# [Prompt Name]

> [One-line description of what this prompt does]

## Overview

| Attribute | Value |
|-----------|-------|
| **Category** | [code-generation / testing / refactoring / documentation / debugging / security-review / accessibility / gov-uk-patterns / workflow] |
| **Tools** | [All / GitHub Copilot / Claude / Amazon Q / Gemini / specific combinations] |
| **Languages** | [Language-agnostic / specific languages] |
| **Difficulty** | [Beginner / Intermediate / Advanced] |
| **Last updated** | [Date] |

## When to use

[Describe the situations where this prompt is most effective. Be specific about the problem it solves.]

**Use this prompt when:**
- [Situation 1]
- [Situation 2]
- [Situation 3]

**Don't use this prompt when:**
- [Situation where it's not appropriate]
- [Alternative approach might be better]

## The prompt

```
[The actual prompt text goes here]

[Use placeholders in square brackets for variable parts, e.g.:]
[language]
[framework]
[paste code here]
[describe requirements]
```

## Placeholders

| Placeholder | Description | Example |
|-------------|-------------|---------|
| `[placeholder1]` | [What to replace it with] | [Example value] |
| `[placeholder2]` | [What to replace it with] | [Example value] |

## Example usage

### Input

**Context:** [Describe the scenario]

**Placeholder values:**
- [placeholder1]: [actual value used]
- [placeholder2]: [actual value used]

**Code/content provided:**

```[language]
[The actual code or content that was provided to the AI]
```

### Output

[What the AI produced - can be abbreviated if long]

```[language]
[Example output from the AI]
```

### Why this worked

[Explain what made this prompt effective in this example]

## Tips for best results

- [Tip 1: Specific advice for getting good results]
- [Tip 2: Common adjustments that help]
- [Tip 3: Context that improves output]

## Common issues and fixes

| Issue | Cause | Fix |
|-------|-------|-----|
| [Problem you might encounter] | [Why it happens] | [How to fix it] |
| [Another common issue] | [Why it happens] | [How to fix it] |

## Related prompts

- [Link to related prompt 1] - [Brief description of relationship]
- [Link to related prompt 2] - [Brief description of relationship]

## Tags

`[tag1]` `[tag2]` `[tag3]` `[tag4]`

**Suggested tags:**
- Tool: `copilot` `claude` `amazon-q` `gemini`
- Language: `java` `python` `typescript` `csharp` `go`
- Framework: `spring` `react` `dotnet` `express`
- Task: `testing` `refactoring` `documentation` `security`
- Level: `beginner` `intermediate` `advanced`
- Context: `gov-uk` `legacy` `greenfield` `api`

---

## Template ends above

---

## Example completed prompt

Below is an example of a completed prompt using this template:

---

# Generate Unit Tests with Edge Cases

> Generate comprehensive unit tests including edge cases and error conditions

## Overview

| Attribute | Value |
|-----------|-------|
| **Category** | testing |
| **Tools** | All |
| **Languages** | Language-agnostic (examples in TypeScript) |
| **Difficulty** | Beginner |
| **Contributed by** | AI Engineering Lab Programme Team |
| **Last updated** | Jan 2026 |

## When to use

Use this prompt when you need to create unit tests for existing functions and want comprehensive coverage including edge cases.

**Use this prompt when:**
- You have a function without tests
- You want to ensure edge cases are covered
- You need tests that document expected behaviour

**Don't use this prompt when:**
- You need integration tests (use integration test prompt)
- The function has complex external dependencies (mock first)
- You're testing UI components (use component testing prompt)

## The prompt

```
Generate unit tests for the following function.

Requirements:
- Test the happy path with typical inputs
- Test edge cases: null/undefined, empty values, boundary conditions
- Test error cases: invalid inputs, exception scenarios
- Use descriptive test names following the pattern: "should [expected behaviour] when [condition]"
- Follow Arrange-Act-Assert pattern
- Include comments explaining non-obvious test cases

Testing framework: [framework]
Language: [language]

Function to test:
[paste code here]
```

## Placeholders

| Placeholder | Description | Example |
|-------------|-------------|---------|
| `[framework]` | Your testing framework | Jest, JUnit 5, pytest, xUnit |
| `[language]` | Programming language | TypeScript, Java, Python |
| `[paste code here]` | The function to test | Your function code |

## Example usage

### Input

**Context:** Testing a utility function that validates UK postcodes

**Placeholder values:**
- [framework]: Jest
- [language]: TypeScript

**Code provided:**

```typescript
function isValidUKPostcode(postcode: string): boolean {
  if (!postcode) return false;
  const cleaned = postcode.replace(/\s/g, '').toUpperCase();
  const regex = /^[A-Z]{1,2}\d[A-Z\d]?\s?\d[A-Z]{2}$/;
  return regex.test(cleaned);
}
```

### Output

```typescript
describe('isValidUKPostcode', () => {
  describe('valid postcodes', () => {
    it('should return true when given a valid postcode with space', () => {
      expect(isValidUKPostcode('SW1A 1AA')).toBe(true);
    });

    it('should return true when given a valid postcode without space', () => {
      expect(isValidUKPostcode('SW1A1AA')).toBe(true);
    });

    it('should return true when given lowercase postcode', () => {
      expect(isValidUKPostcode('sw1a 1aa')).toBe(true);
    });
  });

  describe('edge cases', () => {
    it('should return false when given empty string', () => {
      expect(isValidUKPostcode('')).toBe(false);
    });

    it('should return false when given null', () => {
      expect(isValidUKPostcode(null as any)).toBe(false);
    });

    it('should return false when given undefined', () => {
      expect(isValidUKPostcode(undefined as any)).toBe(false);
    });

    it('should handle extra whitespace', () => {
      expect(isValidUKPostcode('  SW1A  1AA  ')).toBe(true);
    });
  });

  describe('invalid postcodes', () => {
    it('should return false when given incomplete postcode', () => {
      expect(isValidUKPostcode('SW1A')).toBe(false);
    });

    it('should return false when given invalid format', () => {
      expect(isValidUKPostcode('12345')).toBe(false);
    });

    it('should return false when given US zipcode', () => {
      expect(isValidUKPostcode('90210')).toBe(false);
    });
  });
});
```

### Why this worked

- Specific requirements guided comprehensive coverage
- Framework specification ensured correct syntax
- The function was self-contained with clear inputs/outputs

## Variations

### Variation 1: With mocking requirements

**Use when:** Function has dependencies that need mocking

```
Generate unit tests for the following function.

Requirements:
- Test the happy path with typical inputs
- Test edge cases and error cases
- Mock the following dependencies: [list dependencies]
- Verify mock interactions where appropriate

Testing framework: [framework]
Mocking library: [mock library]

Function to test:
[paste code here]
```

### Variation 2: Minimal tests

**Use when:** You need quick coverage, not comprehensive tests

```
Generate essential unit tests for this function.
Focus on: 1 happy path, 1 edge case, 1 error case.
Keep tests concise.

Testing framework: [framework]

Function:
[paste code here]
```

## Tips for best results

- Include the function's imports and type definitions for better context
- Specify your team's test naming conventions if different from standard
- Mention any specific edge cases you know are important
- If the function is part of a class, include relevant class context

## Common issues and fixes

| Issue | Cause | Fix |
|-------|-------|-----|
| Tests use wrong assertion syntax | Framework not specified clearly | Explicitly state framework and version |
| Missing edge cases for your domain | AI doesn't know domain specifics | Add "Also test for: [specific cases]" |
| Tests are too verbose | Default style is comprehensive | Add "Keep tests concise" to prompt |
| Mock syntax incorrect | Mocking library not specified | Specify both test framework and mock library |

## Related prompts

- [Integration test generation](testing/integration-tests.md) - For testing component interactions
- [Test data generation](testing/test-data-generation.md) - For creating test fixtures
- [BDD scenario generation](testing/bdd-scenarios.md) - For behaviour-driven tests

## Tags

`testing` `unit-tests` `beginner` `language-agnostic`

---

## Contribution checklist

Before submitting your prompt, verify:

- [ ] Prompt tested with at least 2 different inputs
- [ ] All placeholders documented
- [ ] Example usage included with real output
- [ ] Tips section includes practical advice
- [ ] Tags added for discoverability
- [ ] File placed in correct category folder
- [ ] File name is descriptive and kebab-case