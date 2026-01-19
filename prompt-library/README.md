> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Prompt Library

> A curated collection of effective prompts for AI Engineering Labs in government software development.

## Purpose

This library contains tested, reusable prompts that help engineers get better results from AI code assistants. Prompts are organised by task type or language and include context on when and how to use them effectively.

Use this library to:

- Find proven prompts for common development tasks
- Learn effective prompting patterns
- Avoid reinventing prompts others have refined
- Contribute prompts that worked well for you

## How to use this library

### Finding prompts

1. **Browse by category** - Navigate to the relevant folder for your task type
2. **Search** - Use repository search for specific keywords

### Using prompts

1. **Read the full prompt entry** - Understand the context and when to use it
2. **Adapt to your situation** - Replace placeholders, adjust for your codebase
3. **Iterate** - Use the prompt as a starting point, refine based on results
4. **Provide context** - Prompts work best with good surrounding context

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

Contribute a prompt when:
- You've refined a prompt that consistently produces good results
- You've solved a common problem others would benefit from
- You've adapted a prompt for government/public sector context
- You've discovered an effective pattern for a specific tool

### Contribution process

1. **Use the template:** Copy [prompt-template.md](prompt-template.md)
2. **Complete all sections:** Ensure the prompt is well-documented
3. **Test thoroughly:** Verify the prompt works across scenarios
4. **Submit PR:** Follow [contribution guidelines](../CONTRIBUTING.md)
5. **Peer review:** Champions or maintainers review before merge

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

If results aren't what you expected:

1. **Check your context** - Did you provide enough information?
2. **Clarify constraints** - Were requirements explicit?
3. **Try rephrasing** - Different wording may help
4. **Break it down** - Smaller requests may work better
5. **Add examples** - Show what you want
6. **Try a different approach** - Ask differently

---

## Tool-specific notes

### GitHub Copilot

- Inline suggestions work best with clear code context
- Use comments to guide suggestions
- Chat mode for longer explanations and generation
- Copilot Edits for multi-file changes

### Claude Code

- Excels at longer, more complex prompts
- Strong at explaining and documenting
- Good multi-file context awareness
- Use CLAUDE.md for project context

### Amazon Q Engineer

- Strong AWS service integration
- Good for infrastructure as code
- Security scanning built-in
- Effective for Java/.NET modernisation

### Gemini Code Assist

- Good for GCP-related tasks
- Strong code explanation capabilities
- Effective for large codebase understanding
- Use for code customisation with your repos

---

## Related documents

- [Prompt Template](prompt-template.md) - Template for contributing prompts
- [Context Engineering Playbook](../playbooks/context-engineering.md) - Providing effective context
- [AI-SDLC Playbook](../playbooks/ai-sdlc-playbook.md) - Using AI in development workflow
- [Guardrails Base](../governance/guardrails-base.md) - Security boundaries for prompts

## References

- [Anthropic Prompt Engineering Overview](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview)
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)