[← Back to Index](./prompt-engineering-index.md)

> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# Prompt engineering for AI coding agents

Understanding the differences between chat-based and agentic AI systems, and how to prompt autonomous coding agents safely and effectively.

## Purpose

AI coding agents can autonomously make changes across your codebase, offering powerful productivity gains but requiring careful prompting and oversight. This guide helps you understand how to prompt agents effectively and safely.

Use this guide to:

- understand how prompting agents differs from prompting chat systems
- apply the human-in-the-loop principle when prompting for safe agent usage
- write effective prompts for agents on repetitive tasks while maintaining code quality
- prevent technical debt from accumulating through poorly prompted AI-generated code

## Who this applies to

This guide applies to engineers working with advanced AI tools:

- engineers using agentic coding tools (GitHub Copilot Workspace, Cursor Composer and similar)
- team leads evaluating agent-based tools
- anyone responsible for code quality and maintainability


### Chat vs agentic systems: how to prompt each

Understanding the difference and how your prompting approach should change:

#### Chat-based assistants:
- you paste code snippets
- AI suggests changes
- you apply changes manually
- full control over every modification

#### Agentic systems:
- AI can read and write multiple files
- makes changes directly
- greater automation
- sees more project context

#### When to use each:

Use chat-based for:
- learning and exploration
- complex business logic
- security-critical code
- novel algorithms
- architecture decisions
- when you need to understand every change

Use agents for:
- renaming across codebase
- formatting and linting fixes
- repetitive refactoring
- adding logging throughout
- updating imports
- migration tasks

### The human-in-the-loop principle

Never blindly accept agentic changes.

Before accepting agentic code changes, review the following:

1. Read through every file changed.
2. Understand why each change was made.
3. Check for unintended side effects.
4. Verify tests still pass.
5. Look for introduced bugs.
6. Check if it follows your patterns.
7. Ensure it does not add tech debt.

Agents struggle in these areas:
- context beyond code - business logic, domain knowledge, user intent
- non-obvious dependencies - implicit contracts, external integrations
- style consistency - your team's specific preferences
- testing implications - what additional tests are now needed

Common agent mistakes include:
- over-abstracting code
- adding unnecessary complexity
- breaking existing behaviour
- inconsistent error handling
- mixing coding styles

### How to prompt agents safely

1. Start with specific instructions. For example, instead of "Improve this codebase", write "Add type hints to all functions in the auth/ directory using Python 3.11 syntax".

2. Review changes incrementally by asking the agent to make changes one file at a time, stopping after each file for your review before proceeding.

3. Test between changes by instructing the agent to ensure all tests pass after each refactoring before moving to the next change.

4. Understand changes before accepting them. If you see a change you do not understand, ask "Why did you change [specific code]? What problem does this solve? Are there any risks or trade-offs with this approach?".

5. Preserve important context by providing constraints upfront. For example, tell the agent "Before refactoring, note that: [Important business rule], [Performance requirement], [Integration constraint]. Ensure your changes respect these constraints.".

### Tech debt from AI

Tech debt accumulates through:
- accepting code without understanding
- letting AI make decisions without guidance
- not reviewing for consistency
- allowing quick fixes without proper solutions

To prevent tech debt from AI-generated code, complete these steps after the agent makes changes:

1. Run your linter and formatter.
2. Check for new TODO comments.
3. Look for duplicated code.
4. Verify error handling is consistent.
5. Ensure documentation is updated.
6. Check if new tests are needed.

The rule: If you do not understand code well enough to maintain it, do not merge it.

---

Previous: [Prompt engineering for code documentation](./prompt-engineering-documentation.md)

Next: [Prompt engineering for AI coding agents](./prompt-engineering-agents.md)

[Return to index](./prompt-engineering-index.md)