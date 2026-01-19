# How to Get the Best Out of Your AI Code Assistant: A Complete Playbook

## Introduction

Your colleague asks an AI assistant to build an authentication system and gets production-ready code in minutes. You ask the same assistant for the same thing and get something that barely compiles.

### The AI Adoption Challenge

Many organisations struggle with AI code assistant adoption, facing these common issues:

**Inconsistent Results:** engineers get vastly different quality outputs depending on their prompts and understanding of how LLMs work. Some copy-paste code without understanding what it does or whether it's even correct.

**No Shared Standards:** Each team develops their own approach—some embrace AI assistants, others avoid them entirely, with wildly varying code quality as a result.

**Architecture Drift:** AI-generated code doesn't follow company standards, leading to inconsistent patterns across the codebase.

**Knowledge Silos:** When someone figures out how to get great results, that knowledge stays trapped in their head instead of spreading across teams.

### The Solution

AI code assistants need structure to deliver consistent value. This playbook provides practical techniques to get better results, whether you're working solo or enabling an entire team.

### How to Use This Playbook

**For individual engineers:** Follow the techniques through your development workflow. Start with the foundational techniques, then apply them to your daily work.

**For team leads:** Use this as a training resource. Share relevant sections with your team, establish standards based on these patterns, and create your own examples that match your tech stack.

**For organisations:** Adapt these techniques to your context. Create internal guidelines, build example libraries, and establish review processes that ensure AI-generated code meets your standards.

Throughout this guide, you'll see examples that demonstrate core principles. Whilst the specific technologies may differ from yours, the prompting patterns and techniques apply universally.

## Table of Contents

- [Introduction](#introduction)
  - [The AI Adoption Challenge](#the-ai-adoption-challenge)
  - [The Solution](#the-solution)
  - [How to Use This Playbook](#how-to-use-this-playbook)
- [Part 1: Foundational Prompting Techniques](#part-1-foundational-prompting-techniques)
  - [The Human Test: Can Someone Else Do This Task?](#the-human-test-can-someone-else-do-this-task)
  - [The Five Core Techniques](#the-five-core-techniques)
  - [Combining Techniques: The Power Prompt](#combining-techniques-the-power-prompt)
  - [Context: The Secret Weapon](#context-the-secret-weapon)
- [Part 2: Different Ways to Use Your AI Assistant](#part-2-different-ways-to-use-your-ai-assistant)
  - [As a Coach and Mentor](#as-a-coach-and-mentor)
  - [As a Design Consultant](#as-a-design-consultant)
  - [For Fast-Track Onboarding](#for-fast-track-onboarding)
  - [Using Instruction Files (Project Context)](#using-instruction-files-project-context)
- [Part 3: Practical Use Cases](#part-3-practical-use-cases)
  - [Use Case 1: "I Need to Write a New Function"](#use-case-1-i-need-to-write-a-new-function)
  - [Use Case 2: "This Code is a Mess—Help Me Refactor"](#use-case-2-this-code-is-a-messhelpme-refactor)
  - [Use Case 3: "Something's Broken—Help Me Debug"](#use-case-3-somethings-brokenhelpme-debug)
  - [When AI Gets It Wrong (And What to Do About It)](#when-ai-gets-it-wrong-and-what-to-do-about-it)
- [Part 4: Testing - Getting Comprehensive Coverage](#part-4-testing---getting-comprehensive-coverage)
  - [Types of Tests to Generate](#types-of-tests-to-generate)
  - [Security Testing—Critical for Government Projects](#security-testingcritical-for-government-projects)
  - [Accessibility Testing—Meeting WCAG Standards](#accessibility-testingmeeting-wcag-standards)
  - [Performance Testing](#performance-testing)
  - [Edge Case Discovery](#edge-case-discovery)
  - [Maintaining Test Suites](#maintaining-test-suites)
  - [Common Testing Mistakes](#common-testing-mistakes)
- [Part 5: Documentation - Making Code Maintainable](#part-5-documentation---making-code-maintainable)
  - [The Documentation Hierarchy](#the-documentation-hierarchy)
  - [Level 2: Docstrings—The Primary Documentation](#level-2-docstringsthe-primary-documentation)
  - [Level 3: README Files—Project Overview](#level-3-readme-filesproject-overview)
  - [Level 4: API Documentation](#level-4-api-documentation)
  - [Maintaining Documentation](#maintaining-documentation)
  - [Automating Documentation with Sphinx](#automating-documentation-with-sphinx)
  - [Common Documentation Mistakes](#common-documentation-mistakes)
- [Part 6: Working with AI Coding Agents](#part-6-working-with-ai-coding-agents)
  - [Chat vs Agentic Systems](#chat-vs-agentic-systems)
  - [The Human-in-the-Loop Principle](#the-human-in-the-loop-principle)
  - [How to Work with Agents Safely](#how-to-work-with-agents-safely)
  - [Tech Debt from AI](#tech-debt-from-ai)
- [Conclusion: The Professional's AI Workflow](#conclusion-the-professionals-ai-workflow)
  - [Key Principles Revisited](#key-principles-revisited)
  - [Solving the Adoption Challenges](#solving-the-adoption-challenges)
  - [The Competitive Advantage](#the-competitive-advantage)
  - [Your Next Steps](#your-next-steps)
- [Useful Resources](#useful-resources)

---

## Part 1: Foundational Prompting Techniques

### The Human Test: Can Someone Else Do This Task?

**Here's a simple test to check if your prompt has enough context:**

Imagine you're going on holiday for two weeks. You write down instructions for a colleague to complete a task whilst you're away. You hand them the note. Could they actually do it?

If the answer is no—if they'd need to interrupt your holiday to ask clarifying questions—then your AI prompt won't work either.

**AI cannot read your mind, just as humans cannot.**

The better your instructions, the better the output. This applies whether you're delegating to a junior engineer, a contractor, or an AI assistant.

**Example of the human test in action:**

```
❌ Fails the human test:
"Build the login system"

Questions a human would ask:
- Which framework are we using?
- How does authentication work in our other services?
- Where should user data be stored?
- What's our password policy?
- Do we need 2FA?
- What error messages should we show?
- How should this integrate with the existing system?

✓ Passes the human test:
"Build a login endpoint for our FastAPI service that:
- Uses PostgreSQL (our existing user database)
- Follows the async pattern from our registration endpoint (see example below)
- Implements JWT tokens matching our auth service pattern
- Enforces our password policy: min 12 chars, complexity requirements
- Includes rate limiting (5 attempts per 15 minutes)
- Returns error codes matching our API standards doc
- Logs all attempts for audit trail
- Integrates with our Redis session store

[paste example of existing auth endpoint]"
```

**What you need to give someone to complete a task properly:**

Think about what a human needs:
- **The goal:** What are they building and why?
- **The environment:** What tools, frameworks, databases are available?
- **The constraints:** What are the limits (performance, security, budget)?
- **The examples:** How have we solved similar problems before?
- **The standards:** What coding style, patterns, naming conventions?
- **The integration points:** What does this connect to?
- **The edge cases:** What special situations need handling?
- **The success criteria:** How will we know it's done correctly?

If you give this information to a human, they can complete the task. If you give it to AI, it can too.

**The delegation principle:**

Before you write an AI prompt, ask yourself:
> "If I handed these instructions to a competent engineer who's never seen our codebase, could they complete this task successfully?"

If the answer is yes, your prompt is probably good enough.

If the answer is no, you're missing context. Add it before you prompt the AI.

**Why this matters for teams:**

When everyone on your team applies "the human test" before prompting AI:
- Code quality becomes consistent
- AI-generated code fits existing patterns
- Less time wasted on back-and-forth revisions
- Architecture standards are maintained
- Knowledge isn't siloed (because context is explicit in prompts)

**Remember:** AI is powerful, but it's not psychic. Treat it like you'd treat a very capable colleague who's just joined your team—give them all the context they need to succeed.

### The Five Core Techniques

Brief introduction to the techniques we'll apply throughout:

**1. Chain of Thought Reasoning**
- Getting AI to show its working
- "Walk me through your thought process step by step..."
- "Let's think through this systematically..."

**2. Few-Shot Prompting**
- Teaching by example
- "Reference this good example and make it look like that"
- Show the pattern you want repeated

**3. Reverse Prompting**
- Make the AI ask YOU questions first
- "Before you get started, ask me for any information you need to do a good job"
- Uncover requirements before coding

**4. Role Assignment**
- "Act as a senior Python engineer..."
- Changes expertise level and perspective

**5. Emphasis/Emotional Manipulation**
- Add context about importance to improve output quality
- "This is critical for production code that handles sensitive user data."
- "Think carefully about edge cases—this function processes financial transactions."
- "This is important for my team's code review—please be thorough."

**Why this works:** Just as you'd give a colleague more context about why something matters, AI responds to framing that indicates the stakes and required quality level.

### Combining Techniques: The Power Prompt

The most effective prompts combine multiple techniques. Here's the formula:

```
"Help me write a [specific task].

This is critical for [context about importance]. (Emphasis)

Before you get started, ask me for any information you need to 
do a good job. (Reverse Prompting)

Here's an example of similar code from our codebase that shows 
our style: (Few-Shot Prompting)
[paste example]

Please walk me through your thought process step by step as you 
design the solution. (Chain of Thought)

Act as a senior [role] with expertise in [domain]. (Role Assignment)"
```

**Real example:**
```
"Help me write a user authentication endpoint.

This is critical for production—we handle 10,000+ logins daily.

Before you get started, ask me for any information you need to 
do a good job about security requirements, rate limiting, session 
management, and error handling.

Here's an example of another endpoint from our codebase:
[paste example showing async patterns, error handling, response format]

Once you understand the requirements, walk me through your design 
approach step by step before writing the code.

Act as a senior backend engineer with FastAPI and security expertise."
```

**What happens:**
1. AI understands the stakes (emphasis)
2. AI asks clarifying questions (reverse prompting)
3. You answer, filling in requirement gaps
4. AI references your example (few-shot)
5. AI explains its design approach (chain of thought)
6. You catch issues before any code is written
7. AI writes code with appropriate expertise level (role)
8. Code matches your existing patterns

**Why this works:**
- Emphasis ensures appropriate attention to quality
- Reverse prompting ensures you don't miss critical requirements
- Few-shot examples maintain consistency with your codebase
- Chain of thought catches logical errors early
- Role assignment gets appropriate expertise level and terminology
- You spend 2 minutes setting up the prompt, save 30 minutes in revisions

**When to use which techniques:**

You don't need all techniques every time. Here's a quick guide:

- **Simple, well-defined tasks:** Role + Context is enough
- **New features with unknowns:** Reverse Prompting + Chain of Thought
- **Maintaining consistency:** Few-Shot + Context
- **Complex logic:** Chain of Thought + Role Assignment
- **Critical code:** All techniques combined

### Context: The Secret Weapon

**The single biggest factor in getting quality output from AI assistants? Context.**

The difference between mediocre and excellent AI output isn't which technique you use—it's how much relevant context you provide. The more context and clarity you provide, the more accurate and relevant the output will be.

Think of context as all the information in your prompt that helps the LLM understand not just what you want, but how it should fit into your existing project. This includes your tech stack, coding standards, dependencies, constraints, and the patterns you're already using.

By providing clear and detailed instructions, you can get the model to generate functional, ready-to-use code. Use your domain expertise to make specific requests, mention the packages and dependencies you want, reference your existing patterns, and be explicit about requirements.

**What to include in every prompt:**
- **Tech stack:** Languages, frameworks, versions
- **Architecture:** How this fits into your system
- **Constraints:** Performance, security, scalability requirements
- **Standards:** Your team's coding style, naming conventions, accessibility requirements
- **Dependencies:** Existing packages/libraries you're using
- **Integration points:** What this code needs to connect with
- **Examples:** Existing code that demonstrates your patterns
- **Compliance requirements:** Government Digital Service (GDS) standards, WCAG guidelines, security classifications

**Template for context-rich prompts:**
```
Project Context:
- Language/Framework: [Python 3.11, FastAPI 0.104]
- Database: [PostgreSQL with SQLAlchemy ORM]
- Key patterns we use: [async/await, dependency injection, Pydantic models]
- Standards to follow: [GDS design patterns, WCAG 2.1 AA compliance]
- This component will: [handle user authentication]
- Must integrate with: [existing Redis session store, GOV.UK Verify]
- Performance requirements: [<100ms response time]
- Security requirements: [rate limiting, password hashing with bcrypt, audit logging]

Here's an example of our existing code structure:
[paste example]

Task: [specific request]

Before proceeding, ask me any clarifying questions about requirements, 
edge cases, or constraints.
```

**Why this transforms output quality:**
- Reduces back-and-forth iterations by 70%+
- Produces code that fits your codebase immediately
- Avoids deprecated or incompatible solutions
- Gets you production-ready code faster
- The AI makes fewer assumptions
- You catch requirement gaps early
- Code meets compliance requirements from the start

**The context hierarchy:**

**Must have:**
- What you're building
- Tech stack and versions
- How it integrates with existing code
- Critical compliance requirements

**Should have:**
- Example code demonstrating patterns
- Constraints and requirements
- Known edge cases
- Security and accessibility standards

**Nice to have:**
- Team conventions and style preferences
- Performance benchmarks
- Testing requirements
- Documentation standards

**For government projects, also include:**
- Security classification level
- Data handling requirements
- Accessibility standards (WCAG level)
- GDS service standards compliance
- Audit and logging requirements
- User research findings that inform the feature

**Remember:** Five minutes spent providing context saves hours of revision. Code never comes without bugs, whether it's AI-generated or human-written, but good context dramatically improves the starting point.

---

## Part 2: Different Ways to Use Your AI Assistant

Beyond just generating code, AI assistants can serve multiple roles in your development workflow. Understanding these different modes helps you get more value from the tool.

### As a Coach and Mentor

**The scenario:** You're looking at unfamiliar code or trying to understand a complex concept. Instead of spending hours reading documentation or searching Stack Overflow, use the AI as your personal tutor.

**A simple learning workflow (Explain → Demonstrate → Imitate → Practise):**

This is a straightforward way to learn a new concept with an AI assistant:

**E - Explain:** Ask the AI to explain the concept
```
"Explain how to stream audio responses from an API in Angular.

What's the difference between returning a blob vs a ReadableStream?
When would I use each approach?"
```

**D - Demonstrate:** Ask for a concrete example
```
"Show me a simple example of an Angular service method that streams audio.

Include:
- HTTP POST to API
- Handling the stream response
- Basic error handling"
```

**I - Imitate:** Create something similar with guidance
```
"Now help me write a streaming method for our audio service.

Context:
[paste existing non-streaming method for reference]

Requirements:
- Stream audio from Azure Speech API
- Use fetch API (not HttpClient) for streaming support
- Include authentication token handling
- Follow our existing service patterns"
```

**P - Practice:** Apply it independently with review
```
"Review this streaming method I wrote:
[paste implementation]

Does it follow best practices?
How's the error handling?
Any potential issues with memory or performance?"
```

**Why this works:** It mirrors how we naturally learn—understand the concept, see it in action, try it yourself, then refine through practice. It also naturally combines the prompting techniques in this playbook (for example: reverse prompting when asking for explanations, few-shot prompting when requesting examples, and step-by-step reasoning when reviewing your attempt).

**Understanding complex code:**

```
"Explain what this function does in simple terms:

[paste complex function]

Then explain:
1. What design pattern is being used here?
2. Why would someone choose this approach?
3. What are the potential downsides?
4. Can you suggest a simpler alternative for a beginner?"
```

**Learning new concepts:**

```
"I'm new to async/await in Python. 

Explain:
1. What problem does it solve?
2. When should I use it vs regular functions?
3. Show me a simple example
4. Then show me a more realistic example with error handling
5. What are common mistakes beginners make?"
```

**Understanding frameworks:**

```
"I need to understand how FastAPI's dependency injection works.

Explain it like I'm coming from Flask background:
1. What's different from Flask?
2. Show me a simple example
3. Show me a realistic example with database connections
4. What are the benefits of this approach?"
```

### As a Design Consultant

**The scenario:** You're at a decision point. Should you use pattern A or pattern B? Which library? Which architecture? Use the AI to explore options before committing.

**Comparing approaches:**

```
"I need to implement a notification system that handles email, SMS, and push notifications.

Give me 3 different architectural approaches:
1. For each approach, explain the design
2. List pros and cons
3. Consider: scalability, maintainability, testing ease
4. Recommend which approach for a team of 5 engineers
5. Highlight the trade-offs I'm making with each choice"
```

This same approach works for any decision: comparing libraries, choosing design patterns, evaluating architectural styles. The AI gives you expert-level analysis without the bias of "we've always done it this way."

**Understanding design patterns:**

The Gang of Four patterns are fundamental design tools. Here's a quick reference:

**Creational patterns** (how objects are created):
- **Singleton:** Ensure only one instance exists
- **Factory:** Create objects without specifying exact class
- **Builder:** Construct complex objects step by step

**Structural patterns** (how objects are composed):
- **Adapter:** Make incompatible interfaces work together
- **Decorator:** Add behaviour to objects dynamically
- **Facade:** Provide simple interface to complex system

**Behavioural patterns** (how objects communicate):
- **Strategy:** Select algorithm at runtime
- **Template Method:** Define skeleton, let subclasses fill details
- **Observer:** Notify multiple objects of changes
- **Command:** Encapsulate requests as objects

When you're unsure which pattern fits your problem, describe your use case to the AI and ask it to recommend appropriate patterns with reasoning.

### For Fast-Track Onboarding

**The scenario:** You've just joined a team with an unfamiliar codebase. Instead of spending weeks building up context, use AI to accelerate your understanding.

**Using instruction files for consistency:** Rather than providing context in every prompt, many teams create instruction files that AI assistants automatically read. These files contain your project's standards, patterns, and requirements, ensuring every AI interaction follows your team's conventions. For detailed guidance, see the dedicated instruction-files playbook in this repository.

**Understanding the codebase:**

```
"I'm new to this codebase. Here's the main application file:

[paste code]

Help me understand:
1. What does this application do at a high level?
2. What are the main components and their responsibilities?
3. What frameworks/libraries is it using?
4. What are the key patterns I should understand?
5. What would be a good starting point to make my first contribution?"
```

**Tracing through flows:**

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
4. How would I add a new authentication method (e.g., OAuth)?
5. What are the security considerations in this implementation?"
```

**Understanding architectural decisions:**

```
"This codebase uses [specific pattern/approach].

Explain:
1. Why might the previous engineers have chosen this approach?
2. What problem does it solve?
3. What are the downsides?
4. How does this affect how I should write new features?
5. What should I be careful about when modifying this code?"
```

**Learning team conventions:**

```
"Looking at these three files from the codebase:

[paste examples]

Help me identify:
1. What naming conventions are used?
2. How is error handling done?
3. What's the logging pattern?
4. How are tests structured?
5. What should my code look like to fit in?"
```

### Using Instruction Files (Project Context)

**The scenario:** You want the AI to automatically follow your project's standards every time, without having to repeat context in every prompt.

This topic is covered in its own playbook in this repository.

---

## Part 3: Practical Use Cases

### Use Case 1: "I Need to Write a New Function"

**The scenario:** You're building a new feature. The requirements are clear-ish, but you know from experience that "clear-ish" means you'll discover edge cases as you go.

This is where the iterative approach shines. Don't try to get perfect code in one prompt. Instead, build it up systematically, switching roles to get different perspectives.

#### The Iterative Refinement Workflow

**Round 1: Get the basics working**

Start with reverse prompting to uncover what you might have missed:

```
"Help me write an async function to update user profile information 
including email, phone, and address.

This is critical for production code that handles sensitive user data.

Before you start, ask me questions about:
- Validation requirements
- Error handling expectations  
- Integration points
- Performance constraints
- Security considerations

Context:
- Python 3.11 with FastAPI
- PostgreSQL with SQLAlchemy ORM
- We use async/await patterns throughout
- Here's an example of our existing user creation endpoint:
[paste example showing your patterns]

Act as a senior backend engineer."
```

**What happens:**
The AI asks clarifying questions. You answer them. This surfaces requirements you hadn't explicitly thought about—rate limiting, audit logging, what happens if the email is already taken by another user.

Now you get a basic implementation that actually addresses real requirements.

**Round 2: Layer on validation**

Don't try to do everything at once. Now that the basic logic works, add validation:

```
"Now add comprehensive input validation using Pydantic models:
- Email: valid format, deliverability check
- Phone: international format (E.164), optional field
- Address: structured fields (line1, line2, city, postcode)
- Required vs optional fields

Return clear validation errors with field-level detail."
```

**Round 3: Add proper error handling**

```
"Add comprehensive error handling for:
- Database connection failures
- Duplicate email addresses (unique constraint violation)
- Invalid data formats
- Transaction rollbacks

Use specific exception types and meaningful error messages that 
don't expose internal implementation details."
```

**Round 4: Security review—switch roles**

Here's where changing roles becomes powerful:

```
"Act as a security expert reviewing this function.

Identify vulnerabilities:
- Input sanitisation issues
- SQL injection risks
- Data exposure in error messages
- Authentication/authorisation gaps

Rate each by severity and provide secure refactored code."
```

**Note:** The AI might flag things you missed. A security expert role often catches that you're returning too much information in error messages, or that you're not properly sanitising inputs even though Pydantic is handling validation.

#### Using Few-Shot for Consistency

If you've got existing code that follows your team's patterns, use it:

```
"Here are two existing endpoints from our codebase:

[Example 1: User creation endpoint]
[Example 2: Password update endpoint]

Notice our patterns:
- Async/await style
- Error handling with custom exceptions
- Structured logging format
- Docstring style (Google format)
- Response format

Now write the profile update function following these same patterns."
```

**Why this works:** You get code that looks like it was written by your team, not generic AI code. It uses your error handling patterns, your logging approach, your response structure.

#### Common Mistakes to Avoid

**❌ Trying to get everything in one prompt**
"Write a complete, production-ready, secure, well-tested, documented function that does X"
Result: Generic code that doesn't fit your context

**❌ Not providing examples**
Result: Code that doesn't match your style and needs extensive refactoring

**❌ Accepting code without understanding it**
If you can't explain what every line does, iterate until you can

**✓ The iterative approach**
- Build basics first
- Layer on complexity
- Switch roles for different perspectives
- Understand before moving to the next round

---

### Use Case 2: "This Code is a Mess—Help Me Refactor"

**The scenario:** You've inherited a 300-line function that does everything. It's untested, undocumented, and somehow critical to production. Sound familiar?

AI excels at systematic refactoring, but you need to guide it through the process methodically.

#### The Three-Step Refactoring Approach

**Step 1: Analyse (Don't touch the code yet)**

```
"Act as a code reviewer analysing this function:

[paste the monolithic function]

Context:
- This handles user authentication and session creation
- It's been in production for 3 years
- We have basic integration tests but no unit tests
- Performance has degraded as traffic increased

Identify:
- Code smells and anti-patterns
- Responsibilities this function has (it should have one)
- Complexity issues
- Testability problems
- Performance concerns

Don't refactor yet—just analyse and explain what's wrong."
```

**Why analyse first:** You need to understand what you're dealing with before you start changing it. The AI will spot things like:
- This function does 5 different things
- It's mixing business logic with data access
- Error handling is inconsistent
- It's making synchronous calls that could be async
- There's duplicated logic that could be extracted

**Step 2: Plan (Create a refactoring strategy)**

```
"Based on your analysis, create a refactoring plan:

1. What patterns should we apply? (e.g., repository pattern, dependency injection)
2. What's the order of changes? (safest to riskiest)
3. How do we maintain backwards compatibility?
4. What new tests do we need?
5. What are the risks at each step?

We need to do this incrementally—we can't break production."
```

The AI gives you a step-by-step plan. Maybe:
1. Extract database operations into a repository class
2. Extract validation into separate validator
3. Extract session management into a service
4. Add dependency injection
5. Make database operations async
6. Add comprehensive error handling

**Step 3: Execute (One step at a time)**

Now refactor incrementally:

```
"Let's implement step 1 from your plan: Extract database operations 
into a repository class.

Show me:
- The new repository class
- The refactored function using the repository
- What changed and why
- How to test this in isolation
- How this maintains backwards compatibility with existing callers"
```

After implementing step 1, test it. Make sure nothing broke. Then move to step 2.

#### Using Chain of Thought for Complex Refactoring

```
"I want to refactor this class [paste code]. Let's think through it step by step:

1. What are all the responsibilities of this class?
2. Which responsibilities violate single responsibility principle?
3. How could we separate these into focused classes?
4. What design patterns would help?
5. How would dependency injection work here?
6. What's the migration path from old to new?

Walk me through your reasoning, then show the refactored architecture."
```

This surfaces the thought process, helping you understand not just the "what" but the "why" of the refactoring.

#### Common Refactoring Mistakes

**❌ Refactoring without tests**
You don't know if you broke something

**❌ Trying to refactor everything at once**
High risk of introducing bugs

**❌ Refactoring without understanding the original behaviour**
You might change functionality unintentionally

**✓ The safe approach:**
- Analyse first
- Plan incrementally
- Test after each step
- Keep backwards compatibility
- Deploy gradually

---

### Use Case 3: "Something's Broken—Help Me Debug"

**The scenario:** Your code worked yesterday. Now it doesn't. The error message is cryptic. You've been staring at it for 30 minutes. Time to bring in a systematic debugging partner.

#### The Systematic Debugging Approach

**Provide complete context—don't just paste the error:**

```
"I'm getting this error:

[full error message and stack trace]

In this code:
[relevant code—not your entire codebase, but enough context]

Expected behaviour: User submits form, gets confirmation email
Actual behaviour: Form submits but no email, logs show this error

Environment:
- Python 3.11, FastAPI, Celery for background tasks
- Redis for task queue
- GOV.UK Notify for email sending
- This worked yesterday, broke after we updated Celery version

Recent changes:
- Updated Celery from 5.2.7 to 5.3.4
- Added rate limiting to email sending
- Changed Redis connection pool settings

Act as a senior debugger. What's likely causing this?"
```

**Why this works:** You've given the AI the symptoms, context, timeline, and expected vs actual behaviour—exactly what you'd tell a human colleague.

The AI will think through possibilities systematically, suggest tests for each hypothesis, and help you identify the root cause. For complex issues, ask it to use chain of thought reasoning: "Walk me through 5 possible causes and how to test each one."

#### The Exploratory Testing Approach

Before bugs happen, find them:

```
"Act as a QA engineer trying to break this function:

[function code]

List edge cases and error conditions that could cause problems:
- Boundary values
- Null/empty inputs
- Type mismatches
- Concurrent access
- Resource exhaustion  
- Network failures
- Invalid data combinations

For each, explain how it would fail and how to handle it."
```

**Note:** Run this BEFORE deployment. The AI will find edge cases you missed.

#### Common Debugging Mistakes

**❌ Jumping to solutions without understanding the problem**
"Just make it work" leads to band-aid fixes

**❌ Not providing enough context**
"Why doesn't this work?" [pastes one line]

**❌ Ignoring the AI's questions**
If it asks for logs, there's a reason

**✓ The systematic approach:**
- Provide complete context
- Use chain of thought to explore hypotheses
- Test each hypothesis
- Understand the fix before applying it
- Add tests to prevent recurrence

---

### When AI Gets It Wrong (And What to Do About It)

AI-generated code isn't automatically good code. Understanding when and how AI fails helps you catch problems early and know when to step away.

#### Security Vulnerabilities

**The problem:** AI might suggest code that works perfectly in testing but contains security vulnerabilities only visible with proper security scanning.

**Example scenario:** AI suggests using regex for input validation. The code works perfectly in testing, but when run through OWASP and SonarQube security checks, it flags a ReDoS (Regular Expression Denial of Service) vulnerability.

**The lesson:** AI doesn't know your security standards. Always run generated code through your organisation's security checks:
- SonarCloud for code quality
- OWASP Dependency-Check for CVE vulnerabilities
- Your organisation's standard security scanning tools

Treat AI-generated code the same way you'd treat code from any new team member: review it, test it, scan it.

#### The Loop of Despair

**The problem:** AI suggests a fix. It doesn't work. You ask for another fix. That makes it worse. You keep iterating, and suddenly you're 20 minutes into solving what should have been a 2-minute problem.

**Warning signs you're in the loop:**
- The AI's suggestions are getting increasingly complex
- You're not understanding the changes anymore
- The code is drifting further from your codebase patterns
- You've been iterating for more than 3 or 4 rounds

**What to do:** Stop. Step away from the AI. Look at the actual problem with fresh eyes. Often, you'll spot a simple solution you missed because you were too focused on making the AI's approach work.

**The principle:** If the AI isn't helping after a few iterations, it's not going to. Reset your approach.

#### When to Skip AI Entirely

Some tasks are faster without AI:

**Quick tasks your IDE handles better:**
- Simple variable renames (use IDE refactoring)
- Basic formatting (use your formatter)
- Obvious typo fixes

**Tasks requiring deep understanding:**
- Hotfixes where you need to understand every character
- Authentication or payment processing logic
- Anything touching sensitive data handling
- Critical security-related code

**When you already know exactly what to do:**
- Simple logic you've written dozens of times
- Standard patterns you know by heart
- Quick bug fixes in familiar code

**Remember:** AI is a tool, not a requirement. Sometimes the simple approach is better than the AI-powered one. Use your judgment about when AI adds value and when it's just adding overhead.

#### Quality Gate Integration

**Best practice:** Integrate AI usage with your existing quality processes:

```markdown
## AI-Generated Code Checklist

Before committing AI-generated code:

□ Code passes all unit tests
□ Security scan shows no new vulnerabilities
□ Code follows team style guidelines
□ You understand every line
□ Documentation is updated
□ New tests added for new functionality
□ Performance impact assessed
□ Accessibility requirements met (if UI code)
```

**The principle:** AI-generated code goes through the same quality gates as human-written code. No shortcuts.

---

## Part 4: Testing - Getting Comprehensive Coverage

**The scenario:** You've written the code. It works on your machine. But you know from painful experience that "it works on my machine" is where production incidents begin.

This is where AI really shines—generating comprehensive test suites that consider edge cases humans often miss.

### Types of Tests to Generate

**Unit tests—isolating individual components:**

```
"Write unit tests for this user profile update function:

[paste function]

Include:
- Happy path: successful update
- Boundary conditions: empty strings, max length fields
- Error cases: 
  - Duplicate email (unique constraint)
  - Invalid email format
  - Database connection failure
  - Transaction rollback scenarios
  
Mock external dependencies:
- Database session
- Email validation service  
- Audit logger

Use pytest fixtures for:
- Test database session
- Sample user objects
- Mock email validator

Follow AAA pattern (Arrange, Act, Assert) and include descriptive test names."
```

**Integration tests—testing components working together:**

```
"This API endpoint interacts with multiple systems:

[paste endpoint code]

Write integration tests that verify:

End-to-end flow:
- Submit valid application
- Verify database record created
- Verify file uploaded to S3
- Verify notification queued
- Verify audit log entry

Error scenarios:
- Database transaction rollback on S3 failure
- Notification failure doesn't block application
- Concurrent submission attempts

Cache behaviour:
- Cache invalidation after update
- Cache warming for frequently accessed data

Use pytest-asyncio for async testing and real test database 
(not mocks—we're testing integration)."
```

### Security Testing—Critical for Government Projects

```
"Act as a security tester. Write tests that attempt to exploit this 
form submission endpoint:

[paste endpoint code]

Test for:

Input validation:
- SQL injection in text fields
- XSS payloads in description
- Path traversal in file names
- Script injection in uploaded files

Authentication/Authorisation:
- Accessing without valid session
- CSRF token bypass attempts
- Accessing other users' submissions
- Privilege escalation attempts

Rate limiting:
- Submitting faster than allowed rate
- Distributed rate limit bypass (multiple IPs)

File upload security:
- Malicious file types (.exe disguised as .pdf)
- Files exceeding size limit
- Zip bombs
- Files with malicious content

For each test:
- Attempt the attack
- Verify it's blocked
- Check that security event is logged
- Verify user sees appropriate error message (not internal details)

Use pytest with requests library for HTTP tests."
```

**Why this matters:** Government services handle sensitive citizen data. Security testing isn't optional.

### Accessibility Testing—Meeting WCAG Standards

```
"Write automated accessibility tests for this citizen-facing form:

[paste form HTML/code]

Test for WCAG 2.1 AA compliance:

Form structure:
- All inputs have associated labels
- Labels use for/id correctly
- Required fields marked with aria-required
- Error messages linked with aria-describedby

Error handling:
- Error summary at top has role="alert"
- Focus moves to error summary on validation failure
- Individual field errors visible and screen-reader accessible
- Error messages are clear and helpful

Keyboard navigation:
- All interactive elements accessible via keyboard
- Tab order is logical
- Focus indicators visible
- No keyboard traps

Contrast:
- Text meets 4.5:1 contrast ratio
- Interactive elements meet 3:1 contrast ratio
- Error states clearly visible

Use pytest with playwright for browser testing and axe-core for 
automated accessibility scanning."
```

### Performance Testing

```
"Write performance tests for this public-facing endpoint:

[paste endpoint code]

Context:
- Typical load: 100 requests/second
- Peak load: 500 requests/second (Monday mornings)
- SLA: 95th percentile response time < 200ms

Test scenarios:

Normal load:
- 100 concurrent users
- Verify response time < 200ms for 95% of requests
- Verify no memory leaks over 5 minute test
- Monitor database connection pool usage

Peak load:
- 500 concurrent users  
- Verify system remains responsive
- Verify error rate stays below 1%
- Verify graceful degradation if overwhelmed

Stress test:
- Gradually increase load until system breaks
- Identify breaking point
- Verify system recovers after load decreases

Use locust for load testing and include:
- Realistic user behaviour (think time between requests)
- Mix of successful and error scenarios
- Monitoring hooks for metrics collection"
```

### Edge Case Discovery

This is where AI really excels:

```
"Act as an expert QA engineer. For this function:

[paste function that processes citizen applications]

List every edge case you can think of. Consider:

Data validity:
- Boundary values (minimum/maximum lengths)
- Empty, null, undefined inputs
- Whitespace-only inputs
- Special characters, unicode, emojis
- Very long inputs (buffer overflow attempts)

Business logic:
- Applications submitted outside business hours
- Duplicate submissions (same user, same data)
- Partial submissions (timeout mid-process)
- Applications that exactly match disqualification criteria

System state:
- Database connection lost mid-transaction
- Cache unavailable
- External API (GOV.UK Notify) down
- Disk full (can't write files)
- Rate limit already exceeded

Concurrency:
- Two users submitting at exact same time
- User submission whilst admin processing
- Cache invalidation during read

Then write tests for the 10 most critical edge cases."
```

**What you get:** Edge cases you never thought of. The AI combines:
- Common software failure modes
- Domain-specific issues (government applications)
- Concurrency problems
- Resource exhaustion scenarios

### Maintaining Test Suites

Tests rot as code evolves. Keep them fresh:

**Updating tests after code changes:**

```
"I've refactored this function:

Old version:
[paste old code]

New version:
[paste new code]

Update the existing test suite:
[paste existing tests]

Changes needed:
- Remove tests for deleted functionality
- Update tests for changed behaviour
- Add tests for new functionality
- Ensure test names still match what they test
- Update fixtures if data structures changed

Mark obsolete tests clearly with comments explaining why they were removed."
```

**Test coverage analysis:**

```
"Here's my function and its tests:

Function:
[paste code]

Tests:
[paste tests]

Analyse test coverage:
1. What code paths aren't being tested?
2. What error conditions are missing?
3. What edge cases aren't covered?
4. Are there any untestable sections? (If so, they need refactoring)

Write additional tests to achieve >90% coverage of meaningful code paths.

Don't chase 100% coverage—some code (like __repr__ or logging statements) 
doesn't need tests. Focus on business logic and error handling."
```

### Common Testing Mistakes

**❌ Only testing the happy path**
Real users find the unhappy paths

**❌ Mocking everything in integration tests**
Then you're not actually testing integration

**❌ Tests that depend on external services**
Tests should be reliable and fast

**❌ Not testing accessibility**
Accessibility violations often surface in production

**✓ The comprehensive approach:**
- Test happy path AND error cases
- Test edge cases exhaustively
- Test security implications
- Test accessibility requirements
- Keep tests maintainable and fast
- Update tests as code evolves

---

## Part 5: Documentation - Making Code Maintainable

**The scenario:** You've built something clever. It works beautifully. Six months from now, you (or worse, someone else) will need to modify it. Will they understand how it works?

Good documentation is the difference between code that lives and code that gets rewritten because nobody dares touch it.

### The Documentation Hierarchy

Documentation exists at multiple levels. Each serves a different purpose.

**Level 1: Inline Comments—Use Sparingly**

The first rule of comments: Your code should explain WHAT it does. Comments explain WHY.

```
"Review this function and add inline comments ONLY where the logic 
is not self-evident:

[paste function with complex business logic]

Follow these principles:
- Don't comment what's obvious from the code
- Explain WHY decisions were made, not WHAT the code does
- Comment complex algorithms or non-obvious business rules
- Highlight gotchas or behaviour that might surprise
- Explain workarounds for known issues

Remove any existing comments that just restate the code."
```

**Good vs bad comments:**

```python
# ❌ Bad: States the obvious
user_count = len(users)  # Get the count of users
total = sum(prices)      # Sum the prices

# ✓ Good: Explains why
user_count = len(users)  # Batch size limited to 1000 per API constraint
total = sum(prices)      # VAT calculated separately to match legacy system

# ❌ Bad: Explains what (code already does this)
# Loop through users and send email to each
for user in users:
    send_email(user)

# ✓ Good: Explains why/how it handles edge cases
# Process users in batches to avoid overwhelming email service
# If any batch fails, we continue with next (failures logged for retry)
for batch in chunk(users, size=100):
    try:
        send_batch_emails(batch)
    except EmailServiceError:
        log_for_retry(batch)
        continue
```

**Prompt for comment review:**

```
"Analyse the comments in this code:

[paste code with comments]

Identify:
- Comments that add no value (just restate code)
- Missing comments where logic is unclear
- Outdated comments that don't match the current code
- Comments that should be moved to docstrings
- Places where refactoring would eliminate need for comments

Provide specific suggestions for improvements."
```

### Level 2: Docstrings—The Primary Documentation

Docstrings are how engineers understand your functions without reading the implementation.

**Generate comprehensive docstrings:**

```
"Add Google-style docstrings to all functions and classes in this module:

[paste code]

For each function, include:
- One-line summary (imperative mood: 'Calculate', not 'Calculates')
- Detailed description of what it does and why it exists
- Args with types and clear descriptions
- Returns with type and description
- Raises listing all exceptions (when/why they're raised)
- Examples showing typical usage
- Notes for important behaviour or gotchas

For classes, include:
- Class purpose and responsibility
- Attributes with types
- Usage example
- Any important lifecycle considerations"
```

**Converting between docstring formats:**

```
"Convert these docstrings from Google style to NumPy style:

[paste code with Google-style docstrings]

Maintain all information whilst following NumPy conventions.
Ensure compatibility with Sphinx autodoc."
```

### Level 3: README Files—Project Overview

```
"Create a comprehensive README for this module:

[describe module purpose and key components]

The module handles:
- User authentication and session management
- Integration with GOV.UK Verify
- OAuth2 for API access
- Audit logging for security events

Include sections for:
- Clear description of what the module does (2-3 sentences)
- Why it exists (the problem it solves)
- Installation instructions (dependencies, setup steps)
- Quick start example (get something working in 5 minutes)
- Common use cases with code examples (3-4 scenarios)
- Configuration options (environment variables, config files)
- Troubleshooting section (common issues and solutions)
- Testing instructions (how to run tests locally)
- Contributing guidelines (for team members)
- Security considerations (for government service context)

Use GFM (GitHub Flavoured Markdown) with appropriate headings, code blocks,
and badges where relevant."
```

### Level 4: API Documentation

For APIs, documentation is part of the product:

```
"Generate OpenAPI/Swagger documentation for these FastAPI endpoints:

[paste endpoint code]

Ensure the documentation includes:
- Clear endpoint descriptions (what it does, why it exists)
- Request schema with example payloads
- Response schemas for success (200, 201) and all error cases (400, 401, 403, 404, 500)
- Example requests showing typical usage
- Authentication requirements
- Rate limiting information
- Deprecation warnings if applicable

Write descriptions in plain English suitable for both technical and
non-technical stakeholders."
```

### Maintaining Documentation

Documentation rots faster than code. Keep it current:

**Auditing documentation:**

```
"Review these docstrings against the current code:

Code:
[paste current code]

Docstrings:
[paste existing docstrings]

Identify:
- Parameters that were added/removed/renamed
- Changed return types
- New exceptions being raised
- Changed behaviour not reflected in description
- Examples that no longer work
- Outdated notes or warnings

Provide updated docstrings that match the current implementation."
```

**Batch updates after refactoring:**

```
"After refactoring, update all documentation in this module:

[paste refactored code with old docstrings]

Update:
- Function signatures (parameter names, types, defaults)
- Parameter descriptions (reflect new behaviour)
- Return value descriptions
- Examples (ensure they work with new implementation)
- Notes about changed behaviour
- Cross-references to renamed functions

Maintain the same docstring style (Google format).
Flag any examples that are now invalid."
```

### Automating Documentation with Sphinx

```
"I want to generate HTML documentation from my code using Sphinx.

Current setup:
- Python 3.11 project with Google-style docstrings
- Multiple modules: auth, applications, notifications
- FastAPI for API endpoints

Help me:
1. Review my docstrings for Sphinx compatibility
2. Create a Sphinx configuration (conf.py)
3. Set up the documentation structure (index.rst, module pages)
4. Configure autodoc to generate API documentation
5. Add a Makefile for building docs
6. Provide commands to generate and serve the documentation locally

Include extensions for:
- Autodoc (API documentation from docstrings)
- Napoleon (Google/NumPy style support)
- Mermaid (for diagrams)
- OpenAPI (for FastAPI endpoint documentation)"
```

### Common Documentation Mistakes

**❌ Documenting obvious things**
```python
# Bad
def add(a, b):
    """Add two numbers together."""
    return a + b
```

**❌ Missing critical context**
```python
# Bad—no mention of side effects
def process_payment(amount):
    """Process a payment."""
```

**❌ Outdated examples**
Documentation says one thing, code does another

**❌ No examples**
Engineers learn by example, not just descriptions

**✓ The good documentation approach:**
- Explain WHY and WHEN, not just WHAT
- Include realistic examples
- Document edge cases and gotchas
- Keep it current as code evolves
- Add context about system integration
- Warn about security/PII considerations

---

## Part 6: Working with AI Coding Agents

### Chat vs Agentic Systems

**Understanding the difference:**

**Chat-based assistants:**
- You paste code snippets
- AI suggests changes
- You apply changes manually
- Full control over every modification

**Agentic systems:**
- AI can read/write multiple files
- Makes changes directly
- Greater automation
- Sees more project context

**When to use each:**

**Use chat-based for:**
- Learning and exploration
- Complex business logic
- Security-critical code
- Novel algorithms
- Architecture decisions
- When you need to understand every change

**Use agents for:**
- Renaming across codebase
- Formatting/linting fixes
- Repetitive refactoring
- Adding logging throughout
- Updating imports
- Migration tasks

### The Human-in-the-Loop Principle

**Never blindly accept agentic changes.**

**Review checklist:**
```
Before accepting agentic code changes:

□ Read through every file changed
□ Understand WHY each change was made
□ Check for unintended side effects
□ Verify tests still pass
□ Look for introduced bugs
□ Check if it follows your patterns
□ Ensure it doesn't add tech debt
```

**The danger zones:**

**Where agents struggle:**
- **Context beyond code:** Business logic, domain knowledge, user intent
- **Non-obvious dependencies:** Implicit contracts, external integrations
- **Style consistency:** Your team's specific preferences
- **Testing implications:** What additional tests are now needed

**Common agent mistakes:**
- Over-abstracting code
- Adding unnecessary complexity
- Breaking existing behaviour
- Inconsistent error handling
- Mixing coding styles

### How to Work with Agents Safely

**1. Start specific:**
```
Bad: "Improve this codebase"
Good: "Add type hints to all functions in the auth/ directory 
      using Python 3.11 syntax"
```

**2. Review incrementally:**
```
"Make these changes one file at a time. After each file, stop and 
let me review before proceeding."
```

**3. Test between changes:**
```
"After each refactoring, ensure all tests pass before moving to 
the next change."
```

**4. Understand before accepting:**
```
If you see a change you don't understand:

"Why did you change [specific code]? What problem does this solve? 
Are there any risks or trade-offs with this approach?"
```

**5. Preserve important context:**
```
"Before refactoring, note that:
- [Important business rule]
- [Performance requirement]
- [Integration constraint]

Ensure your changes respect these constraints."
```

### Tech Debt from AI

**How it accumulates:**
- Accepting code without understanding
- Letting AI make decisions without guidance
- Not reviewing for consistency
- Allowing quick fixes without proper solutions

**Prevention:**
```
After agent makes changes:

1. Run your linter/formatter
2. Check for new TODO comments
3. Look for duplicated code
4. Verify error handling is consistent
5. Ensure documentation is updated
6. Check if new tests are needed
```

**The rule:** If you don't understand code well enough to maintain it, don't merge it.

---

## Conclusion: The Professional's AI Workflow

### Key Principles Revisited

**1. Context is everything**
- More context = better code
- Include tech stack, constraints, patterns
- Apply the human test: could a colleague complete this task with your instructions?

**2. Iterate, don't expect perfection**
- Build up functionality in layers
- Switch roles to get different perspectives
- Refine through multiple passes
- Code never comes without bugs—iterative refinement helps you understand each piece

**3. Use the right technique for the task**
- **New features with unknowns:** Reverse Prompting + Chain of Thought
- **Maintaining consistency:** Few-Shot + Context
- **Complex logic:** Chain of Thought + Role Assignment
- **Critical code:** All techniques combined

**4. Know when to use agents vs chat**
- Chat for learning and critical code
- Agents for repetitive, mechanical tasks
- Always review what agents do

**5. Never blindly accept**
- Understand every change
- Test everything
- Keep humans in the loop
- You're the architect, AI is the assistant

**6. Know when AI isn't helping**
- Watch for the loop of despair
- Some tasks are faster without AI
- Security-critical code deserves extra scrutiny
- Step away if not making progress

### Solving the Adoption Challenges

Remember the problems we started with? Here's how these techniques solve them:

**Inconsistent Results?** 
Fixed by establishing standard prompting patterns. When everyone uses the human test and provides rich context, output quality becomes consistent.

**No Shared Standards?**
Create a team prompting guide based on these techniques. Share example prompts that work well. Review AI-generated code in PRs just like human code.

**Architecture Drift?**
Use few-shot prompting with your existing patterns. AI matches your team's style when you show it examples.

**Knowledge Silos?**
Document your effective prompts. When someone discovers a great technique, add it to your team's playbook.

### The Competitive Advantage

Engineers who thrive aren't those who avoid AI or blindly trust it—they're the ones who:

- Communicate clearly and specifically
- Provide rich context
- Apply the right prompting technique for the task
- Review with domain expertise
- Test everything
- Understand before accepting
- Use AI to handle the tedious work whilst they focus on architecture, design, and critical thinking

AI coding assistants don't replace the need for skill—they amplify it. The better you understand software development, the better you can direct AI to help you.

### Your Next Steps

1. **Pick one technique** from this guide to try this week
2. **Apply it** to your current work
3. **Compare results** before and after using the technique
4. **Share what works** with your team
5. **Build your own examples** that match your tech stack

The future belongs to engineers who can think clearly, communicate precisely, and leverage AI effectively. 

---

## Useful Resources

This playbook works best when combined with the wider resources in this repository:

### Start here
- [Maturity Assessment Framework](../assessment/maturity-assessment-framework.md) - Understand your starting point
- [AI Tool Comparative Guidance](../manager-tool-guides/comparative-guidance.md) - Choose an assistant and rollout approach

### Prompts and reuse
- [Prompt Library](../prompt-library/README.md) - Reusable prompts by task and language
- [Prompt Template](../prompt-library/prompt-template.md) - Standard structure for new prompts

### Quality and governance
- [Measurement Playbook](../quality-metrics/measurement-playbook.md) - Track progress and demonstrate value
- [Compliance Checklist](../governance/compliance-checklist.md) - Check usage against government standards

### Next playbooks
- [AI SDLC Playbook](./ai-sdlc-playbook.md) - Embed AI into delivery practices
- [Context Engineering](./context-engineering.md) - Advanced context techniques

### Tool guides (pick the one you use)
- [GitHub Copilot Guide](../manager-tool-guides/copilot/README.md)
- [Claude Code Guide](../manager-tool-guides/claude/README.md)

Note: The instruction-files playbook link target needs confirming (it appears to have been renamed or moved). Tell me the correct filename and I’ll wire up the link.

---
