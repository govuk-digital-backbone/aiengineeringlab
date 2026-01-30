[← Back to Index](./prompt-engineering-index.md)

> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# Prompt engineering for different AI assistant roles

How to write effective prompts to use AI assistants as a coach, design consultant and onboarding accelerator.

## Purpose

AI assistants can serve multiple roles in your development workflow beyond just generating code. This guide shows you how to write effective prompts to use AI as a learning tool, design consultant and onboarding accelerator.

Use this guide to learn how to prompt AI for:

- learning new concepts and frameworks through structured AI interactions
- exploring architectural options and design decisions
- accelerating onboarding to unfamiliar codebases
- setting up project context through instruction files

## Who this applies to

This guide applies to anyone using AI assistants for:

- learning new technologies and frameworks
- exploring architectural and design decisions
- onboarding to unfamiliar codebases
- establishing team standards for AI usage

### As a coach and mentor

The scenario: you are looking at unfamiliar code or trying to understand a complex concept. Instead of spending hours reading documentation or searching Stack Overflow, use the AI as your personal tutor.

#### A simple learning workflow (explain, demonstrate, imitate, practise)

This is a straightforward way to learn a new concept with an AI assistant.

Explain: ask the AI to explain the concept.

Example prompt:
```
"Explain how to stream audio responses from an API in Angular.

What is the difference between returning a blob vs a ReadableStream?
When would I use each approach?"
```

Demonstrate: ask for a concrete example.

Example prompt:
```
"Show me a simple example of an Angular service method that streams audio.

Include:
- HTTP POST to API
- handling the stream response
- basic error handling"
```

Imitate: create something similar with guidance.

Example prompt:
```
"Now help me write a streaming method for our audio service.

Context:
[paste existing non-streaming method for reference]

Requirements:
- stream audio from Azure Speech API
- use fetch API (not HttpClient) for streaming support
- include authentication token handling
- follow our existing service patterns"
```

Practise: apply it independently with review.

Example prompt:
```
"Review this streaming method I wrote:
[paste implementation]

Does it follow best practices?
How is the error handling?
Any potential issues with memory or performance?"
```

Why this works: it mirrors how we naturally learn - understand the concept, see it in action, try it yourself, then refine through practice. It also naturally combines the prompting techniques in this playbook (for example: reverse prompting when asking for explanations, few-shot prompting when requesting examples and step-by-step reasoning when reviewing your attempt).

#### Understanding complex code

Example prompt:
```
"Explain what this function does in simple terms:

[paste complex function]

Then explain:
1. What design pattern is being used here?
2. Why would someone choose this approach?
3. What are the potential downsides?
4. Can you suggest a simpler alternative for a beginner?"
```

#### Learning new concepts

Example prompt:
```
"I am new to async and await in Python. 

Explain:
1. What problem does it solve?
2. When should I use it vs regular functions?
3. Show me a simple example.
4. Then show me a more realistic example with error handling.
5. What are common mistakes beginners make?"
```

#### Understanding frameworks

Example prompt:
```
"I need to understand how FastAPI's dependency injection works.

Explain it like I am coming from Flask background:
1. What is different from Flask?
2. Show me a simple example.
3. Show me a realistic example with database connections.
4. What are the benefits of this approach?"
```

### As a design consultant

The scenario: you are at a decision point. Should you use pattern A or pattern B? Which library? Which architecture? Use the AI to explore options before committing.

#### Comparing approaches

Example prompt:
```
"I need to implement a notification system that handles email, SMS, and push notifications.

Give me 3 different architectural approaches:
1. For each approach, explain the design.
2. List pros and cons.
3. Consider: scalability, maintainability, testing ease.
4. Recommend which approach for a team of 5 engineers.
5. Highlight the trade-offs I am making with each choice."
```

This same approach works for any decision: comparing libraries, choosing design patterns, evaluating architectural styles. The AI gives you expert-level analysis without the bias of "we have always done it this way."

#### Understanding design patterns

The Gang of Four patterns are fundamental design tools. Here is a quick reference.

Creational patterns (how objects are created):

- singleton: ensure only one instance exists
- factory: create objects without specifying exact class
- builder: construct complex objects step by step

Structural patterns (how objects are composed):

- adapter: make incompatible interfaces work together
- decorator: add behaviour to objects dynamically
- facade: provide simple interface to complex system

Behavioural patterns (how objects communicate):

- strategy: select algorithm at runtime
- template method: define skeleton, let subclasses fill details
- observer: notify multiple objects of changes
- command: encapsulate requests as objects

When you are unsure which pattern fits your problem, describe your use case to the AI and ask it to recommend appropriate patterns with reasoning.

### For fast-track onboarding

The scenario: you have just joined a team with an unfamiliar codebase. Instead of spending weeks building up context, use AI to accelerate your understanding.

Using instruction files for consistency: rather than providing context in every prompt, many teams create instruction files that AI assistants automatically read. These files contain your project's standards, patterns and requirements, ensuring every AI interaction follows your team's conventions. For detailed guidance, see the dedicated instruction-files playbook in this repository.

#### Understanding the codebase

Example prompt:
```
"I am new to this codebase. Here is the main application file:

[paste code]

Help me understand:
1. What does this application do at a high level?
2. What are the main components and their responsibilities?
3. What frameworks and libraries is it using?
4. What are the patterns I should understand?
5. What would be a good starting point to make my first contribution?"
```

#### Tracing through flows

Example prompt:
```
"I need to understand how user authentication works in this system.

Here are the relevant files:
- auth.py: [paste]
- models.py: [paste]
- middleware.py: [paste]

Walk me through:
1. What happens when a user logs in? (step by step)
2. How are sessions managed?
3. Where is authentication checked?
4. How would I add a new authentication method (for example, OAuth)?
5. What are the security considerations in this implementation?"
```

#### Understanding architectural decisions

Example prompt:
```
"This codebase uses [specific pattern or approach].

Explain:
1. Why might the previous engineers have chosen this approach?
2. What problem does it solve?
3. What are the downsides?
4. How does this affect how I should write new features?
5. What should I be careful about when modifying this code?"
```

#### Learning team conventions

Example prompt:
```
"Looking at these 3 files from the codebase:

[paste examples]

Help me identify:
1. What naming conventions are used?
2. How is error handling done?
3. What is the logging pattern?
4. How are tests structured?
5. What should my code look like to fit in?"
```

### Using instruction files (project context)

The scenario: you want the AI to automatically follow your project's standards every time, without having to repeat context in every prompt.

This topic is covered in its own playbook in this repository.

---

Previous: [Foundational prompting techniques](./prompt-engineering-foundations.md)

Next: [Prompt engineering for common development tasks](./prompt-engineering-use-cases.md)