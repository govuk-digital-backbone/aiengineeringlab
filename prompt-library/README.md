> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Prompt library

> A curated collection of effective prompts for AI Engineering Labs in government software development.

## Purpose

This library contains tested, reusable prompts that help engineers get better results from AI code assistants. Prompts are organised by task type or language and include context on when and how to use them effectively.

Use this library to:

- find proven prompts for common development tasks
- learn effective prompting patterns
- avoid reinventing prompts others have refined
- contribute prompts that worked well for you

## How to use this library

### Finding prompts

1. Browse by category by navigating to the relevant folder for your task type.
2. Use the repository search for specific keywords.

### Using prompts

1. Read the full prompt entry to understand the context and when to use it.
2. Adapt to your situation by replacing placeholders text and adjusting for your codebase.
3. Iterate by using the prompt as a starting point, refine based on results.
4. Provide context as prompts work best with good surrounding context.

### Contributing prompts

We welcome contributions. See [Contributing a prompt](#contributing-a-prompt) below.

---

## Prompt categories

```
prompt-library/
├── README.md                    # This file
├── prompt-template.md           # Template for new prompts
│
├── by-language/             # Language and framework specific prompts
│   ├── angular-best-pracites.md
│   ├── java.md
│   ├── javascript.md
│   └── python.md
│
├── by-task-type/                     # Task specific prompts
│   ├── code-generation.md
│   ├── testing.md
│   ├── refactoring.md
│   ├── documentation.md
│   ├── debugging.md
│   ├── security-review.md
│   ├── accessibility.md
│   └── gov-uk-patterns.md
│
└── workflow/                    # Development workflow prompts
    ├── code-review.md
    ├── git-operations.md
    └── ci-cd.md
```

---

## Contributing a prompt

### When to contribute

Contribute a prompt when you have:

- refined a prompt that consistently produces good results
- solved a common problem others would benefit from
- adapted a prompt for government or public sector context
- discovered an effective pattern for a specific tool

### Contribution process

1. Use the template - Copy [prompt-template.md](prompt-template.md).
2. Complete all sections - Ensure the prompt is well-documented.
3. Test thoroughly - Verify the prompt works across scenarios.
4. Submit PR - Follow [contribution guidelines](../CONTRIBUTING.md).
5. Peer review - Champions or maintainers review before merge.

### Quality criteria

| Criterion | Description |
|-----------|-------------|
| Effective | Consistently produces useful results |
| Documented | Clear explanation of when and how to use |
| Tested | Verified across multiple scenarios |
| Generalised | Useful beyond one specific situation |
| Safe | No security or data concerns |

---

## Prompt effectiveness tips

### What makes prompts effective

| Factor | Guidance |
|--------|----------|
| Specificity | Be precise about what you want |
| Context | Provide relevant background information |
| Constraints | State boundaries and requirements clearly |
| Examples | Show what good output looks like |
| Format | Specify desired output structure |
| Iteration | Refine based on initial results |

### Iterating on prompts

If results are not what you expected:

1. Check your context, did you provide enough information?
2. Clarify constraints, were requirements explicit?
3. Try rephrasing, different wording may help.
4. Break it down, smaller requests may work better.
5. Add examples, show what you want.
6. Try a different approach, ask differently.

---

## Tool-specific notes

### GitHub Copilot
You should use:
- inline suggestions work best with clear code context
- comments to guide suggestions
- chat mode for longer explanations and generation
- Copilot Edits for multi-file changes

### Claude Code
Claude Code:
- excels at longer, more complex prompts
- is strong at explaining and documenting
- has good multi-file context awareness
- can use CLAUDE.md for project context

### Amazon Q Engineer:
Amazon Q Engineer:
- provides strong AWS service integration
- is good for infrastructure as code
- has security scanning built-in
- is effective for Java/.NET modernisation

### Gemini Code Assist:
Gemini Code Assist:
- is good for GCP-related tasks
- has strong code explanation capabilities
- is effective for large codebase understanding
- works well for code customisation with your repos

---

## Related documents
Related documents include:
- [prompt template](prompt-template.md) - template for contributing prompts
- [context engineering playbook](../playbooks/context-engineering.md) - provides effective context
- [AI-SDLC playbook](../playbooks/ai-sdlc-playbook.md) - using AI in development workflow
- [guardrails base](../governance/guardrails-base.md) - security boundaries for prompts

## References

- [Anthropic prompt engineering overview](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview)
- [GitHub Copilot documentation](https://docs.github.com/en/copilot)