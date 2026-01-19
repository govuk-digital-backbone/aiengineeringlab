> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Context Engineering for AI Code Assistants
Techniques for providing effective context to AI code assistants to maximise output quality and relevance.


## Purpose

AI code assistants are only as good as the context they receive. This playbook provides practical techniques for structuring your codebase, crafting prompts, and managing context to get the best results from AI tools.

Use this playbook to:

- Improve the quality and relevance of AI-generated code
- Reduce hallucinations and incorrect suggestions
- Establish team standards for AI-assisted development
- Optimise context window usage across different tools

## Who this applies to

This playbook applies to all technical personnel using AI coding assistants on government projects, including civil servants, contractors, and suppliers with access to government code repositories or development environments.


## What is context engineering?

Context engineering is the practice of deliberately structuring and providing information to AI assistants so they can generate accurate, relevant, and useful outputs.

Unlike simple prompting (asking a question), context engineering considers:

| Aspect | Description |
|--------|-------------|
| **What the AI knows** | Information in its training data |
| **What you provide** | Files, instructions, examples in the current session |
| **How you structure it** | Organisation, prioritisation, format of context |
| **What you exclude** | Irrelevant information that wastes context space |

Good context engineering dramatically improves AI output quality while reducing iterations and corrections.

---

## Context hierarchy

AI assistants receive context from multiple sources. Understanding the hierarchy helps you provide context at the right level.

```
┌─────────────────────────────────────────────────────────┐
│  1. System/Tool Configuration (Most persistent)         │
│     Organisation rules, MCP servers, custom instructions│
├─────────────────────────────────────────────────────────┤
│  2. Repository Context                                  │
│     README, architecture docs, .github/copilot, etc.    │
├─────────────────────────────────────────────────────────┤
│  3. Project/Workspace Context                           │
│     Open files, project structure, dependencies         │
├─────────────────────────────────────────────────────────┤
│  4. File Context                                        │
│     Current file, imports, related files                │
├─────────────────────────────────────────────────────────┤
│  5. Immediate Context (Most specific)                   │
│     Current prompt, cursor position, selection          │
└─────────────────────────────────────────────────────────┘
```

### Level 1: System/tool configuration

**What it is:** Organisation-wide settings and rules configured in the AI tool.

**How to use it:**

- Configure organisation coding standards
- Set up MCP servers for government standards (TCoP, WCAG, NCSC)
- Define prohibited patterns or security rules
- Establish default behaviours

**Example - GitHub Copilot organisation settings:**
```json
{
  "editor.inlineSuggest.enabled": true,
  "github.copilot.enable": {
    "*": true,
    "plaintext": false,
    "markdown": true
  }
}
```

**Example - Claude project instructions:**
```
You are assisting with a UK Government digital service. Always:
- Follow GOV.UK Design System patterns
- Use accessible markup (WCAG 2.2 AA)
- Apply Government Service Standard principles
- Use British English spelling
```

### Level 2: Repository context

**What it is:** Documentation and configuration files that describe your codebase.

**Key files to maintain:**

| File | Purpose | AI Usage |
|------|---------|----------|
| `README.md` | Project overview, setup, architecture | Primary context source |
| `CONTRIBUTING.md` | Coding standards, conventions | Style guidance |
| `ARCHITECTURE.md` | System design, patterns, decisions | Structural understanding |
| `.github/copilot-instructions.md` | Copilot-specific guidance | Tool-specific rules |
| `claude.md` or `CLAUDE.md` | Claude-specific guidance | Tool-specific rules |
| `cursor-rules.md` | Cursor-specific rules | Tool-specific rules |
| `docs/adr/` | Architecture Decision Records | Design rationale |

### Level 3: Project/workspace context

**What it is:** The broader project structure visible to the AI.

**Techniques:**

- Keep related files in logical directories
- Use consistent naming conventions
- Maintain up-to-date dependency files (`package.json`, `requirements.txt`, etc.)
- Include type definitions and interfaces

### Level 4: File context

**What it is:** The current file and its immediate relationships.

**Techniques:**

- Write clear imports at the top of files
- Include JSDoc/docstrings for functions
- Use meaningful variable and function names
- Add inline comments for complex logic

### Level 5: Immediate context

**What it is:** Your current prompt, selected code, and cursor position.

**Techniques:**

- Be specific in your requests
- Select relevant code before prompting
- Provide examples of desired output
- Reference specific functions or files by name

---

## Repository setup for AI assistance

### Essential documentation

#### README.md structure for AI context

```markdown
# Project Name

## Overview
[2-3 sentences describing what this project does and its purpose]

## Technology Stack
- **Language:** [e.g., Java 17, TypeScript 5.x]
- **Framework:** [e.g., Spring Boot 3.2, Next.js 14]
- **Database:** [e.g., PostgreSQL 15]
- **Cloud:** [e.g., AWS, Azure, GCP]

## Architecture
[Brief description of architecture pattern - e.g., microservices, monolith, serverless]

See [ARCHITECTURE.md](./ARCHITECTURE.md) for detailed documentation.

## Project Structure
```
src/
├── controllers/    # HTTP request handlers
├── services/       # Business logic
├── repositories/   # Data access
├── models/         # Domain entities
├── utils/          # Shared utilities
└── config/         # Configuration
```

## Coding Standards
- [Link to or summary of coding standards]
- [Key patterns used in this project]
- [Testing requirements]

## Getting Started
[Setup instructions]

## Key Patterns
- We use [pattern] for [purpose]
- All services follow [convention]
- Error handling uses [approach]
```

#### ARCHITECTURE.md for complex projects

```markdown
# Architecture Documentation

## System Overview
[Diagram or description of system components]

## Design Decisions

### Why [Decision]
- **Context:** [What situation led to this]
- **Decision:** [What we chose]
- **Consequences:** [Trade-offs accepted]

## Component Responsibilities

### [Component Name]
- **Purpose:** [What it does]
- **Interfaces:** [How other components interact]
- **Patterns:** [Design patterns used]

## Data Flow
[Description of how data moves through the system]

## Integration Points
[External systems and how we integrate]
```

### Tool-specific configuration files

#### GitHub Copilot instructions

Create `.github/copilot-instructions.md`:

```markdown
# Copilot Instructions for [Project Name]

## Code Style
- Use 2-space indentation for JavaScript/TypeScript
- Use 4-space indentation for Java/Python
- Prefer async/await over callbacks
- Use meaningful variable names (no single letters except loop indices)

## Patterns to Follow
- Repository pattern for data access
- Dependency injection for services
- Factory pattern for complex object creation

## Patterns to Avoid
- Do not use `var` in JavaScript
- Do not use raw SQL queries (use ORM)
- Do not hardcode configuration values

## Testing
- All new functions require unit tests
- Use [testing framework] for tests
- Mock external dependencies

## Government Standards
- All user-facing content must meet WCAG 2.2 AA
- Follow GOV.UK Design System components
- Use GOV.UK Frontend for styling
```

#### Claude project instructions

Create `CLAUDE.md` in repository root:

```markdown
# Claude Context for [Project Name]

## Project Overview
This is a [type] service for [department/purpose]. It handles [main functions].

## Key Conventions
- British English for all user-facing text
- ISO 8601 dates (YYYY-MM-DD)
- Metric units throughout

## Architecture Notes
- Monorepo structure with packages in `/packages`
- Shared types in `/packages/common`
- API follows REST conventions with HATEOAS

## Important Context
- This service processes [data type] - never log PII
- All endpoints require authentication except /health
- Rate limiting is handled at API gateway level

## Common Tasks
When asked to create a new endpoint:
1. Add route in `/src/routes`
2. Create controller in `/src/controllers`
3. Add service logic in `/src/services`
4. Write tests in `/__tests__`
5. Update OpenAPI spec in `/docs/api`

## What Not To Do
- Never disable TypeScript strict mode
- Never commit secrets or API keys
- Never bypass input validation
```

---

## Prompt engineering techniques

### Technique 1: Be specific and explicit

**Poor prompt:**
```
Write a function to validate input
```

**Better prompt:**
```
Write a TypeScript function that validates a UK National Insurance number.
- Accept a string parameter
- Return { valid: boolean, formatted: string | null }
- Valid format: Two letters, six digits, one letter (e.g., AB123456C)
- Handle lowercase input
- Trim whitespace
```

### Technique 2: Provide examples

**Prompt with examples:**
```
Convert this function to use async/await instead of callbacks.

Example of what I want:
// Before
function getData(callback) {
  fetch(url).then(res => callback(null, res)).catch(err => callback(err));
}

// After
async function getData() {
  const res = await fetch(url);
  return res;
}

Now convert this function:
[paste function]
```

### Technique 3: Specify constraints

```
Create a React component for a date picker with these constraints:
- Must work without JavaScript (progressive enhancement)
- Must be accessible (WCAG 2.2 AA)
- Must use GOV.UK Design System styling
- No external dependencies beyond React
- Support date range: 1900-01-01 to today
- Locale: en-GB
```

### Technique 4: Request specific output format

```
Analyse this code for security vulnerabilities.

Output format:
## Vulnerability: [Name]
- **Severity:** [Critical/High/Medium/Low]
- **Location:** [File:Line]
- **Description:** [What the issue is]
- **Fix:** [How to remediate]

Code to analyse:
[paste code]
```

### Technique 5: Chain-of-thought prompting

```
I need to refactor this database query for performance. 

Please:
1. First, explain what the current query does step by step
2. Identify the performance bottlenecks
3. Propose optimisations with reasoning
4. Show the refactored query
5. Explain how to verify the improvement

Current query:
[paste query]
```

### Technique 6: Role-based prompting

```
You are a senior security engineer reviewing code for a government service 
that handles sensitive personal data.

Review this authentication code and identify:
- Security vulnerabilities
- OWASP Top 10 violations
- Compliance issues for UK government systems

Be thorough and assume hostile users.

[paste code]
```

---

## Context window management

### Understanding context limits

Each AI tool has a context window limit - the maximum amount of text it can consider.

| Tool | Approximate Context Window |
|------|---------------------------|
| GitHub Copilot | Varies by model |
| Claude Code | 200K tokens |
| Amazon Q | Varies by feature |
| Gemini Code Assist | 1M tokens (Gemini 1.5) |

**Rule of thumb:** 1 token ≈ 4 characters in English, or roughly 3/4 of a word.

### Strategies for large codebases

#### Strategy 1: Selective file inclusion

Instead of opening entire codebase, explicitly include relevant files:

```
# In chat interfaces
I'm working on the UserService. Here are the relevant files:

1. UserService.ts (the file I'm modifying):
[paste content]

2. UserRepository.ts (data access):
[paste content]

3. User.ts (domain model):
[paste content]

Question: How should I add soft delete functionality?
```

#### Strategy 2: Summarise distant context

For large systems, provide summaries rather than full code:

```
System context:
- This is an order processing system with 50+ microservices
- Services communicate via Apache Kafka events
- Current service: payment-processor
- Upstream: order-service (sends OrderCreated events)
- Downstream: notification-service (expects PaymentProcessed events)

I need to add retry logic for failed payments. Here's the current handler:
[paste specific code]
```

#### Strategy 3: Use reference files

Create context files that summarise key information:

```markdown
<!-- .ai-context/payment-domain.md -->
# Payment Domain Context

## Events
- OrderCreated: { orderId, amount, currency, customerId }
- PaymentProcessed: { orderId, paymentId, status, timestamp }
- PaymentFailed: { orderId, reason, retryable }

## Business Rules
- Maximum 3 retry attempts for retryable failures
- Exponential backoff: 1min, 5min, 30min
- Non-retryable: CARD_DECLINED, FRAUD_DETECTED
- Retryable: TIMEOUT, SERVICE_UNAVAILABLE

## Current Integrations
- Stripe for card payments
- GoCardless for Direct Debit
```

#### Strategy 4: Progressive disclosure

Start with high-level context, then drill down:

```
Prompt 1: "I'm adding a new payment provider. Here's our current architecture:
[paste architecture summary]. What integration points do I need?"

Prompt 2: "Good. Now here's the PaymentGateway interface we use:
[paste interface]. Can you suggest the implementation structure?"

Prompt 3: "Here's my first attempt at the implementation:
[paste code]. Please review and suggest improvements."
```

---

## Team context standards

### Establishing team conventions

Create a shared document defining how your team uses AI context:

```markdown
# AI Assistant Usage Standards

## Required Documentation
All repositories must include:
- [ ] README.md with project overview and structure
- [ ] Tool-specific instructions file (.github/copilot-instructions.md, CLAUDE.md)
- [ ] ARCHITECTURE.md for services with 3+ components

## Prompt Standards
When asking AI for code generation:
- Always specify the language and version
- Reference our coding standards document
- Include relevant interface/type definitions
- Specify testing requirements

## Context Hygiene
- Review AI context files quarterly
- Update tool instructions when patterns change
- Remove outdated architectural decisions
- Keep examples current with latest conventions

## Security
- Never paste code containing credentials
- Use placeholders for sensitive values
- Review AI output for accidental secret inclusion
```

### Code review checklist for AI-assisted code

```markdown
## AI-Generated Code Review Checklist

### Context Verification
- [ ] Was appropriate context provided to the AI?
- [ ] Does the code match our project patterns?
- [ ] Are there signs of hallucinated APIs or methods?

### Quality Checks
- [ ] Does the code compile/run without errors?
- [ ] Are all dependencies valid and approved?
- [ ] Do tests pass and cover key paths?
- [ ] Is the code readable and maintainable?

### Security Checks
- [ ] No hardcoded credentials or secrets?
- [ ] Input validation present where needed?
- [ ] No obvious security vulnerabilities?
- [ ] Follows secure coding standards?

### Standards Compliance
- [ ] Follows team coding conventions?
- [ ] Meets accessibility requirements (if UI)?
- [ ] Documentation is adequate?
```

---

## MCP servers for government standards

Model Context Protocol (MCP) servers provide persistent context about standards and guidelines. The programme maintains MCP servers for key government standards.

### Available MCP servers

| MCP Server | Standards Covered | Use Case |
|------------|-------------------|----------|
| GOV.UK Standards | TCoP, Service Standard, Design System | Service development |
| Accessibility | WCAG 2.2, GOV.UK accessibility guidance | UI/UX development |
| Security | NCSC principles, secure coding | Security review |
| API Standards | GDS API technical standards | API development |

### Configuring MCP servers

For Claude Code, add to your configuration:

```json
{
  "mcpServers": {
    "gov-uk-standards": {
      "command": "npx",
      "args": ["-y", "@aieng/mcp-gov-uk-standards"]
    },
    "wcag": {
      "command": "npx",
      "args": ["-y", "@aieng/mcp-wcag"]
    }
  }
}
```

### Using MCP context in prompts

Once configured, reference standards naturally:

```
Create a form component for collecting user addresses.
Follow GOV.UK Design System patterns and ensure WCAG 2.2 AA compliance.
```

The MCP server provides relevant standards context automatically.

---

## Common context patterns

### Pattern 1: The interface-first approach

Provide interfaces before requesting implementations:

```typescript
// Give the AI this context first:
interface PaymentProcessor {
  processPayment(payment: Payment): Promise<PaymentResult>;
  refund(paymentId: string, amount: Money): Promise<RefundResult>;
  getStatus(paymentId: string): Promise<PaymentStatus>;
}

interface Payment {
  amount: Money;
  currency: Currency;
  method: PaymentMethod;
  metadata?: Record<string, string>;
}

// Then ask:
// "Implement PaymentProcessor for Stripe integration, following our 
// error handling patterns from the existing OrderService."
```

### Pattern 2: The test-first approach

Provide tests as specification:

```typescript
// Give the AI the tests:
describe('NationalInsuranceValidator', () => {
  it('accepts valid NI numbers', () => {
    expect(validate('AB123456C')).toEqual({ valid: true, formatted: 'AB 12 34 56 C' });
  });
  
  it('handles lowercase', () => {
    expect(validate('ab123456c')).toEqual({ valid: true, formatted: 'AB 12 34 56 C' });
  });
  
  it('rejects invalid formats', () => {
    expect(validate('invalid')).toEqual({ valid: false, formatted: null });
  });
  
  it('rejects administrative prefixes', () => {
    // BG, GB, KN, NK, NT, TN, ZZ are not valid prefixes
    expect(validate('BG123456A')).toEqual({ valid: false, formatted: null });
  });
});

// Then ask:
// "Implement the validate function to pass these tests"
```

### Pattern 3: The example-driven approach

Provide concrete examples of similar patterns:

```
Here's how we implement repositories in this project:

// UserRepository.ts
@Injectable()
export class UserRepository {
  constructor(private prisma: PrismaService) {}

  async findById(id: string): Promise<User | null> {
    return this.prisma.user.findUnique({ where: { id } });
  }

  async create(data: CreateUserDto): Promise<User> {
    return this.prisma.user.create({ data });
  }
}

Now create OrderRepository following the same pattern, with these methods:
- findById
- findByCustomerId (returns array)
- create
- updateStatus
```

### Pattern 4: The constraint-driven approach

Specify what NOT to do:

```
Refactor this function to improve performance.

Constraints:
- DO NOT change the function signature
- DO NOT add new dependencies
- DO NOT use recursion (call stack limits)
- MUST maintain backward compatibility
- MUST keep existing error messages (used by monitoring)

Current function:
[paste code]
```

---

## Troubleshooting poor AI output

| Problem | Likely Cause | Solution |
|---------|--------------|----------|
| Wrong language/framework | Insufficient project context | Add README with tech stack |
| Outdated APIs | AI training data age | Provide current API documentation |
| Wrong patterns | No coding standards context | Add tool instruction files |
| Incomplete code | Context window exhaustion | Reduce context, be more specific |
| Hallucinated methods | Unfamiliar library | Provide interface/type definitions |
| Inconsistent style | No style guidance | Add coding standards to context |
| Security issues | No security context | Use security-focused prompting |

---

## Related documents

- [AI-SDLC Playbook](ai-sdlc-playbook.md) - Integrating AI into development lifecycle
- [Model Selection Playbook](model-selection.md) - Choosing the right model for tasks
- [Prompt Library](../prompt-library/README.md) - Reusable prompt patterns
- [Guardrails Base](../governance/guardrails-base.md) - Security boundaries

## References

- [Anthropic Prompt Engineering Guide](https://docs.anthropic.com/claude/docs/prompt-engineering)
- [GitHub Copilot Best Practices](https://docs.github.com/en/copilot)
- [GOV.UK Design System](https://design-system.service.gov.uk/)
- [GDS Way - Coding Standards](https://gds-way.cloudapps.digital/)
