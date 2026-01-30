[← Back to Index](./prompt-engineering-index.md)

> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# Foundational prompting techniques

Core techniques for writing effective prompts that produce high-quality, context-aware code from AI assistants.

## Purpose

Understanding foundational prompting techniques is essential for getting consistent, high-quality results from AI code assistants. This guide introduces the core concepts that underpin all effective AI interactions.

## Who this applies to

This guide applies to all engineers using AI code assistants, particularly:

- engineers new to AI-assisted development
- teams establishing AI adoption standards
- anyone looking to improve the quality of AI-generated code


### The Human Test: can someone else do this task

Here is a simple test to check if your prompt has enough context.

Imagine you are going on holiday for 2 weeks. You write down instructions for a colleague to complete a task while you are away. You hand them the note. Could they actually do it?

If the answer is no - if they would need to interrupt your holiday to ask clarifying questions - then your AI prompt will not work either.

#### AI cannot read your mind, just as humans cannot

The better your instructions, the better the output. This applies whether you are delegating to a junior engineer, a contractor or an AI assistant.

Example of the Human Test in action:
```
Fails the Human Test:
"Build the login system"

Questions a human would ask:
- which framework are we using?
- how does authentication work in our other services?
- where should user data be stored?
- what is our password policy?
- do we need 2-factor authentication (2FA)?
- what error messages should we show?
- how should this integrate with the existing system?

Passes the Human Test:
"Build a login endpoint for our FastAPI service that:
- uses PostgreSQL (our existing user database)
- follows the async pattern from our registration endpoint (see example below)
- implements JSON Web Token (JWT) tokens matching our auth service pattern
- enforces our password policy: minimum 12 characters, complexity requirements
- includes rate limiting (5 attempts per 15 minutes)
- returns error codes matching our API standards document
- logs all attempts for audit trail
- integrates with our Redis session store

[paste example of existing auth endpoint]"
```

#### What you need to give someone to complete a task properly

Think about what a human needs:

- the goal: what are they building and why
- the environment: what tools, frameworks, databases are available
- the constraints: what are the limits (performance, security, budget)
- the examples: how have we solved similar problems before
- the standards: what coding style, patterns, naming conventions
- the integration points: what does this connect to
- the edge cases: what special situations need handling
- the success criteria: how will we know it is done correctly

If you give this information to a human, they can complete the task. If you give it to AI, it can too.

#### The delegation principle

Before you write an AI prompt, check if a competent engineer who has never seen your codebase could complete the task successfully with your instructions.

If they could, your prompt is probably good enough.

If they could not, you are missing context. Add it before you prompt the AI.

#### Why this matters for teams

When everyone on your team applies the Human Test before prompting AI:

- code quality becomes consistent
- AI-generated code fits existing patterns
- less time wasted on back-and-forth revisions
- architecture standards are maintained
- knowledge is not siloed (because context is explicit in prompts)

Remember: AI is powerful, but it is not psychic. Treat it like you would treat a very capable colleague who has just joined your team - give them all the context they need to succeed.

### The 5 core techniques

Brief introduction to the techniques we will apply throughout:

- chain of thought reasoning - getting AI to show its working. "Walk me through your thought process step by step..." or "Let's think through this systematically..."
- few-shot prompting - teaching by example. "Reference this good example and make it look like that". Show the pattern you want repeated
- reverse prompting - make the AI ask you questions first. "Before you get started, ask me for any information you need to do a good job". Uncover requirements before coding
- role assignment - "Act as a senior Python engineer...". Changes expertise level and perspective
- emphasis - add context about importance to improve output quality. "This is critical for production code that handles sensitive user data." or "Think carefully about edge cases - this function processes financial transactions." or "This is important for my team's code review - be thorough"

Why this works: just as you would give a colleague more context about why something matters, AI responds to framing that indicates the stakes and required quality level.
### Combining techniques: the power prompt

The most effective prompts combine multiple techniques. Here is the formula:
```
"Help me write a [specific task].

This is critical for [context about importance]. (Emphasis)

Before you get started, ask me for any information you need to do a good job. (Reverse Prompting)

Here is an example of similar code from our codebase that shows our style: (Few-Shot Prompting)
[paste example]

Walk me through your thought process step by step as you design the solution. (Chain of Thought)

Act as a senior [role] with expertise in [domain]. (Role Assignment)"
```

Real example:
```
"Help me write a user authentication endpoint.

This is critical for production - we handle 10,000+ logins daily.

Before you get started, ask me for any information you need to do a good job about security requirements, rate limiting, session management, and error handling.

Here is an example of another endpoint from our codebase:
[paste example showing async patterns, error handling, response format]

Once you understand the requirements, walk me through your design approach step by step before writing the code.

Act as a senior backend engineer with FastAPI and security expertise."
```

What happens when you use the power prompt.

1. AI understands the stakes (emphasis).
2. AI asks clarifying questions (reverse prompting).
3. You answer, filling in requirement gaps.
4. AI references your example (few-shot).
5. AI explains its design approach (chain of thought).
6. You catch issues before any code is written.
7. AI writes code with appropriate expertise level (role).
8. Code matches your existing patterns.

Why this works:

- emphasis ensures appropriate attention to quality
- reverse prompting ensures you do not miss critical requirements
- few-shot examples maintain consistency with your codebase
- chain of thought catches logical errors early
- role assignment gets appropriate expertise level and terminology
- you spend 2 minutes setting up the prompt, save 30 minutes in revisions

#### When to use which techniques

You do not need all techniques every time. Here is a quick guide:

- simple, well-defined tasks: role and context is enough
- new features with unknowns: reverse prompting and chain of thought
- maintaining consistency: few-shot and context
- complex logic: chain of thought and role assignment
- critical code: all techniques combined

### Context: the secret weapon

The single biggest factor in getting quality output from AI assistants? Context.

The difference between mediocre and excellent AI output is not which technique you use - it is how much relevant context you provide. The more context and clarity you provide, the more accurate and relevant the output will be.

Think of context as all the information in your prompt that helps the Large Language Model (LLM) understand not just what you want, but how it should fit into your existing project. This includes your tech stack, coding standards, dependencies, constraints and the patterns you are already using.

By providing clear and detailed instructions, you can get the model to generate functional, ready-to-use code. Use your domain expertise to make specific requests, mention the packages and dependencies you want, reference your existing patterns and be explicit about requirements.

What to include in every prompt:

- tech stack: languages, frameworks, versions
- architecture: how this fits into your system
- constraints: performance, security, scalability requirements
- standards: your team's coding style, naming conventions, accessibility requirements
- dependencies: existing packages or libraries you are using
- integration points: what this code needs to connect with
- examples: existing code that demonstrates your patterns
- compliance requirements: Government Digital Service (GDS) standards, Web Content Accessibility Guidelines (WCAG) guidelines, security classifications

Template for context-rich prompts:
```
Project Context:
- Language and Framework: [Python 3.11, FastAPI 0.104]
- Database: [PostgreSQL with SQLAlchemy ORM]
- Patterns we use: [async and await, dependency injection, Pydantic models]
- Standards to follow: [GDS design patterns, WCAG 2.1 AA compliance]
- This component will: [handle user authentication]
- Must integrate with: [existing Redis session store, GOV.UK Verify]
- Performance requirements: [less than 100ms response time]
- Security requirements: [rate limiting, password hashing with bcrypt, audit logging]

Here is an example of our existing code structure:
[paste example]

Task: [specific request]

Before proceeding, ask me any clarifying questions about requirements, edge cases, or constraints.
```

Why this transforms output quality:

- reduces back-and-forth iterations by 70% or more
- produces code that fits your codebase immediately
- avoids deprecated or incompatible solutions
- gets you production-ready code faster
- the AI makes fewer assumptions
- you catch requirement gaps early
- code meets compliance requirements from the start

#### The context hierarchy

Must have:

- what you are building
- tech stack and versions
- how it integrates with existing code
- critical compliance requirements

Should have:

- example code demonstrating patterns
- constraints and requirements
- known edge cases
- security and accessibility standards

Nice to have:

- team conventions and style preferences
- performance benchmarks
- testing requirements
- documentation standards

For government projects, also include:

- security classification level
- data handling requirements
- accessibility standards (WCAG level)
- GDS service standards compliance
- audit and logging requirements
- user research findings that inform the feature

Remember: 5 minutes spent providing context saves hours of revision. Code never comes without bugs, whether it is AI-generated or human-written, but good context dramatically improves the starting point.

---

Next: [Different ways to use your AI assistant](./prompt-engineering-ai-roles.md)