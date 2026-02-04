---
name: ai-engineering-lab-content-generator
description: Generate documentation, prompts, skills, and reports for the AI Engineering Lab. Ensures British English, GOV.UK compliance, and consistent quality.
metadata:
  version: "1.3"
  last_updated: "2026-01-23"
---

# AI Engineering Lab content generator

Generate high-quality content for the AI Engineering Lab repository that meets government standards.

## Quick start

Seven rules for every piece of content.

1. British English not American spelling, for example, "analyse" not "analyze" and "organise" not "organize".
2. Terminology - "AI Engineering Lab" (not AICA), "REACH framework" (not ADKAR), don't reference our internal workstreams
3. Sentence case everywhere, for example, "How to configure servers" not "How To Configure Servers"
4. Structure [bullet points and and numbered steps](https://www.gov.uk/guidance/style-guide/a-to-z#bullet-points-steps) correctly
5. Spell out acronyms on their first use, for example, "Forward deployed engineer (FDE)" on first use, then "FDE"
6. Audience first - ask "who is reading this?" before writing
7. Be specific, for example, "92% activation in 48 hours" not "good progress"

For full guidance, continue reading. For quick contributions, follow these seven rules and use the relevant template below.

## Questions to ask before creating content

1. "Who is the intended audience for this content?"
   - for FDEs or internal engineers, content should be technical, detailed, implementation-focused
   - for government department stakeholders, content should be accessible, outcome-focused, jargon-explained
   - for external or senior leadership, content should be strategic, concise, impact-driven
   - for a mixed audience, content should layer information with executive summary first

2. "What type of content is being created?"
   - documentation should follow the documentation patterns
   - prompts should follow the prompt template
   - skills should follow the skill template
   - reports should follow the report structure
   - training materials should follow learning design principles

## Core content standards

### Content design principles

Content design puts the user first. On average, people only read 20-28% of words on a page. You must follow the following principles in your content:

- right place - information where users expect it
- right time - when users need it
- right tone - appropriate for context and audience
- right format - whatever meets the users needs whether text, graphic, or video 

Reading age: the average reading age in the UK is 9 years old. Write for this level, considering users who speak English as a second language, have learning disabilities, or have dyslexia.

### Language and spelling

Critical: all content must use British English.

| American (Wrong) | British (Correct) |
|------------------|-------------------|
| analyze | analyse |
| organize | organise |
| customize | customise |
| color | colour |
| favor | favour |
| behavior | behaviour |
| center | centre |
| meter | metre |
| program | programme (except in computing contexts) |
| license (noun) | licence |
| focused | focused (both acceptable in British English) |
| modeling | modelling |
| fill out a form | fill in a form |
| percent | per cent |

Note: American proper nouns keep American spelling (for example, Pearl Harbor, 4th Mechanized Brigade).

### Terminology

Mandatory replacements that apply to all content:

| Old Term | New Term |
|----------|----------|
| AI Code Assistant - AICA | AI Engineering Lab |
| AICA | AI Engineering Lab |
| ADKAR (change model) | REACH framework |

REACH framework components: Readiness, Engagement, Adoption, Capability, Habit

### Do not include

To customers, we are one team. Do not reference internal organisational structures in any documentation, reports, or communications. Specifically, do not include:

- "Layer 1", "Layer 2", "Layer 3" — these are legacy internal terms
- "Workstream A", "Workstream B", "Workstream C" — these are internal team structures
- any reference to internal team divisions or workstream boundaries
- descriptions that suggest the AI Engineering Lab operates as separate sub-teams

This matters because customers engage with the AI Engineering Lab as a unified service. Exposing internal structures creates confusion, suggests fragmentation, and undermines the cohesive service experience we provide.

Instead, you should:

- refer to capabilities or phases of work, not team structures
- describe what gets delivered, not who delivers it
- use "the AI Engineering Lab team" or "our team" when referring to people

Government department names (use these exact forms):

| Department | Abbreviation |
|------------|--------------|
| Department for Science, Innovation and Technology | DSIT |
| Government Digital Service | GDS |
| Department for Work and Pensions | DWP |
| Ministry of Justice | MOJ |
| Home Office | HO |
| Driver and Vehicle Standards Agency | DVSA |
| UK Export Finance | UKEF |
| Cabinet Office | CO |
| HM Treasury | HMT |

Use "and" not "&" in full department names (ampersand only in logos).

### Writing style

| Principle | Application |
|---------|-------------|
| Clarity first | Front-load key information; no hand-waving or vague claims |
| Active voice | "Configure the server" not "The server should be configured" |
| Plain language | Explain jargon; avoid acronyms without definition |
| Actionable | Clear next steps; practical guidance, not just theory |
| Specific | Concrete examples over abstract descriptions |
| Concise | Remove unnecessary words; one idea per sentence |
| Short sentences | Maximum 15-20 words; check any sentence over 25 words |

### GDS style guide essentials

Abbreviations and acronyms

1. Explain them in full at first use, for example, "Personal Independence Payment (PIP)".
2. Do not include full stops, for example, BBC not B.B.C.
3. Do not explain abbreviations if they're well known, for example: UK, NHS, VAT, PDF, HTML, URL.

Addressing users

1. Use "you" as it's direct and personal.
2. Use gender neutral pronouns like "they", "their", "them".
3. Never use gendered pronouns unless necessary.

Contractions

1. Use "cannot" not "can't", "do not" not "don't".
2. This is because many users misread contractions as the opposite meaning.

Numbers 

1. Write "one" in letters, use numerals for 2 and above.
2. Use numerals in steps, lists, and data, for example, "in step 1", "2 developing hazards".
3. Use commas for thousands: 9,000.
4. Use the percentage % sign with numbers: 50%.
5. Spell out fractions: one-half, two-thirds.
6. Use "to" rather than hyphens for ranges: "500 to 900", "Monday to Friday".

Dates

1. Dates should be strutured like this: 4 June 2017 (no comma between month and year).
2. Use "to" in ranges: "tax year 2011 to 2012".
3. Deadlines: "on or before 6 September 2025".
4. Include date with "today": "The minister announced today (14 June 2012)...".

Times

1. Use 5:30pm not 1730hrs.
2. Use "to" in ranges: "10am to 11am" not "10-11am".
3. Use "midnight" and "midday" not "00:00" or "12 noon".
4. For deadlines, use "11:59pm" over "midnight" to avoid ambiguity.

Money

1. Use the pound sterling £ symbol: £75.
2. Don't use decimals unless pence is included: £75.50 but not £75.00.
3. Write out pence: "4 pence per minute".

Capitalisation

1. Sentence case for everything, including titles.
2. Capitalise specific job titles, department names, proper nouns.
3. Use lower case for "government", "minister" (unless specific title), "department" (unless specific).

Bold
Bold should be used sparingly and only for the following purposes:

- interface elements in instructions: Select Start
- use single quotes for interface elements in non-instructional text: "The 'Done' button"
- never for emphasis - use front-loading, headings, or bullets instead

Links

1. Front-load link text with relevant terms.
2. Never use "click here", you should always clearly describe the destination of the link, aligning it to the title of the page where relevant.
3. Link to online services first and offline alternatives after.

Semicolons

Do not use semi-colons as they are often misread. Break the information into separate sentences instead.

### Words to avoid

Replace corporate jargon with plain alternatives:

| Avoid | Use Instead |
|-------|-------------|
| leverage | use, influence |
| utilise | use |
| facilitate | help, run, enable |
| deliver (abstract) | create, provide, build |
| collaborate | work with |
| streamline | simplify |
| robust | comprehensive, thorough |
| going forward | from now on, in the future |
| impact (as verb) | affect, influence |
| key (adjective) | important, main |

## Documentation patterns

### Page structure

Every documentation page should include these sections:

```markdown
# [Page Title in Sentence Case]

[One-paragraph overview — what this is and why it matters]

## Who this is for

[Target audience and prerequisites]

## [Main Content Sections]

[Organised logically with clear headings]

## Next steps

[What to do after reading this]

## Related resources

[Links to relevant documentation]
```

### Code Examples

Always specify the language and include context:

```typescript
// Example: Configuring an MCP server for GOV.UK standards
const server = new MCPServer({
  name: 'govuk-standards',
  version: '1.0.0',
  capabilities: ['formatting', 'accessibility']
});
```

### Tables

Use tables for structured comparisons. Keep them simple:

| Feature | Basic | Advanced |
|---------|-------|----------|
| Code review | Yes | Yes |
| Security scanning | No | Yes |
| Custom rules | No | Yes |

## Prompt Template

Use this structure for all prompts:

```markdown
---
name: [kebab-case-name]
description: [One sentence describing what the prompt does]
category: [code-review | documentation | testing | security | other]
tags: [relevant, tags, here]
---

# [Prompt Name]

## Purpose

[What this prompt accomplishes]

## When to use

[Specific scenarios where this prompt is useful]

## Prompt

[The actual prompt text]

## Example usage

[Show input and expected output]

## Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `{input}` | Description | Yes/No |

## Notes

[Any limitations or considerations]
```

## Skill Template

Use this structure for all skills:

```markdown
---
name: [kebab-case-name]
description: [One sentence describing what the skill does]
---

# [Skill Name]

[Overview paragraph]

## Quick Start

[Minimal steps to use this skill]

## Detailed Usage

[Comprehensive guidance]

## Examples

[Practical examples with inputs and outputs]

## References

[Links to related resources]
```

## Report Structure

### Weekly Status Report

```markdown
# [Team/Project] Weekly Status Report

Week ending: [Date]
Author: [Name]

## Summary

[2-3 sentence executive summary]

## Key metrics

| Metric | This week | Last week | Target |
|--------|-----------|-----------|--------|
| [Metric 1] | [Value] | [Value] | [Value] |

## Accomplishments

- [Specific achievement with measurable outcome]
- [Another achievement]

## Blockers

| Blocker | Impact | Owner | Expected resolution |
|---------|--------|-------|---------------------|
| [Issue] | [Impact] | [Name] | [Date] |

## Next week

- [Planned activity]
- [Another planned activity]

## Risks

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| [Risk] | High/Medium/Low | High/Medium/Low | [Action] |
```

### Assessment Report

```markdown
# [Department] Assessment Report

Date: [Date]
Assessor: [Name]

## Executive summary

[Key findings and recommendations in 3-4 sentences]

## Assessment scope

[What was assessed and methodology]

## Findings

### [Finding 1]

Observation: [What was observed]
Impact: [Why it matters]
Recommendation: [What to do]

### [Finding 2]

[Same structure]

## Recommendations summary

| Priority | Recommendation | Effort | Impact |
|----------|----------------|--------|--------|
| 1 | [Recommendation] | High/Medium/Low | High/Medium/Low |

## Next steps

[Immediate actions required]
```

## Training Materials

### Learning Design Principles

When creating training content, apply these principles:

- Chunking — Break content into digestible pieces (5-7 items per section)
- Scaffolding — Build from simple to complex
- Active learning — Include exercises, not just reading
- Spaced repetition — Reinforce key concepts throughout
- Practical application — Connect to real work scenarios

### Training Module Template

```markdown
# [Module Title]

## Learning Outcomes

By the end of this module, you will be able to:
- [Observable, measurable outcome 1]
- [Observable, measurable outcome 2]

## Prerequisites

- [What learners need to know/have before starting]

## Content

### [Section 1]

[Explanation with examples]

Try it: [Hands-on exercise]

### [Section 2]

[Continue pattern]

## Practice Exercise

[Realistic scenario for application]

## Check Your Understanding

[Questions or self-assessment]

## Summary

[Key takeaways — bullet list]

## Next Steps

[What to do after completing this module]
```

## Compliance Standards

### GOV.UK Service Standard

Content should support teams meeting the 14-point Service Standard:

| Point | Content Implication |
|-------|---------------------|
| 1. Understand users | Include user needs context |
| 4. Simple to use | Write clearly; avoid jargon |
| 5. Everyone can use | Follow accessibility guidelines |
| 12. Open source code | Assume public visibility |

### WCAG 2.2 accessibility

Making content accessible means it can be used by as many people as possible. Remember there are different types of accessibility needs:

- permanent, for example, arm amputee, blind, deaf
- temporary, for example, broken arm, eye infection
- situational, for example, holding a baby, bright sunlight, noisy environment

For content that will appear in digital formats:

| Requirement | Application |
|-------------|-------------|
| Perceivable | Alt text for images; sufficient contrast |
| Operable | Keyboard-navigable structure |
| Understandable | Plain language; consistent formatting |
| Robust | Semantic HTML; valid markup |

Examples of alt text include:

- poor: "image1.png" or "diagram"
- good: "Flowchart showing the department adoption journey: Foundation, Assessment, Engagement, and Community Support stages"

Examples of link text include:

- poor: "Click here" or "Read more"
- good: "Read the MCP security guidance" — always describe the destination

### NCSC Security

When documenting security-related content:

| Principle | Application |
|-----------|-------------|
| Secure by default | Never include credentials in examples |
| Defence in depth | Show multiple security layers |
| Least privilege | Recommend minimal permissions |

## Quality assurance

### Self-review checklist

Before submitting content, verify:

Language:
- [ ] British English spelling throughout
- [ ] Terminology uses AI Engineering Lab (not AICA)
- [ ] No internal workstream or layer references (Layer 1/2/3, Workstream A/B/C)
- [ ] REACH framework (not ADKAR)
- [ ] All acronyms spelled out on first use

GDS formatting:
- [ ] Headings use sentence case (not Title Case)
- [ ] Numbered lists: capital letter start, full stop end
- [ ] Bullet lists: lowercase start, no full stop end
- [ ] All bullet lists have a lead-in line ending with colon
- [ ] Mathematical symbols spelled out in tables (not ≥ or >=)

Structure:
- [ ] Key information front-loaded
- [ ] Appropriate heading hierarchy
- [ ] Tables used for structured comparisons
- [ ] Code examples include language specification
- [ ] Pages over 1500 words split or have contents section
- [ ] Consistent page structure (Purpose, Who this is for, etc.)

Quality:
- [ ] No vague claims without substance
- [ ] Technical content is accurate
- [ ] Actionable next steps provided
- [ ] Audience-appropriate tone
- [ ] No placeholder content ([TBC], [placeholder])

Compliance:
- [ ] Follows relevant template
- [ ] Meets accessibility requirements
- [ ] No sensitive information exposed

### Common issues to avoid

| Issue | Example | Fix |
|-------|---------|-----|
| Vague claims | "This improves productivity" | "Reduces code review time by 30%" |
| Missing context | "Configure the settings" | "Configure the MCP server settings in ~/.claude/settings.json" |
| Passive voice | "The file should be created" | "Create the file" |
| Unexplained jargon | "Use the MCP server" | "Use the MCP (Model Context Protocol) server" |
| American spelling | "utilize", "optimize" | "utilise", "optimise" |
| Wrong terminology | "AICA programme" | "AI Engineering Lab programme" |
| Internal structure references | "Layer 2 will handle...", "Workstream A delivered..." | "The team will handle...", "We delivered..." |
| Title Case headings | "How To Configure Servers" | "How to configure servers" |
| Bullets without lead-in | Starting a list without introduction | Add "You must:" or similar before the list |
| Symbols in tables | ">=80%" or "≥80%" | "greater than or equal to 80%" |
| Undefined acronyms | "The FDE will support..." | "The forward deployed engineer (FDE) will support..." |
| Placeholder content | "[TBC]", "[placeholder]", "[scenario]" | Complete the content or remove the section |
| Overly long pages | 2000+ words single page | Split into multiple pages or add contents section |

## Output format

When generating content, structure the response as:

```markdown
## Generated Content

[The actual content following the appropriate template]

---

## Content metadata

Type: [Documentation / Prompt / Skill / Report / Training]
Audience: [Specified audience]
Compliance: [Standards applied]

## Quality notes

[Any assumptions made or areas that may need human review]
```

## References

Internal (relative to repository root):
- `prompt-template.md` — Standard prompt contribution format
- `mcp-best-practices.md` — Server design principles
- `mcp-gov-uk-standards.md` — Government compliance
- `Department_Adoption_Journey.md` — Process context
- `Content_design_principles_and_style_guide.docx` — Full GDS style reference

External:
- [GDS A-Z Style Guide](https://www.gov.uk/guidance/style-guide/a-to-z-of-gov-uk-style) — Authoritative reference for all formatting
- [GOV.UK Content Design Manual](https://www.gov.uk/guidance/content-design) — Planning, formats, links
- [GOV.UK Service Standard](https://www.gov.uk/service-manual/service-standard)
- [WCAG 2.2 Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/)
- [NCSC Developers Collection](https://www.ncsc.gov.uk/collection/developers-collection)

Note: This skill provides guidance but does not validate compliance automatically. Pair with human review or the `mr-review` skill for quality assurance.

---

## Appendix: good and poor content examples

### Example 1: documentation overview

Poor:
> This document provides information about MCP servers and how they can be used to help with various tasks in the development process.

Good:
> MCP (Model Context Protocol) servers provide persistent, structured context to AI code assistants. They enable AI tools to access and apply GOV.UK standards automatically — without requiring engineers to paste guidelines into every prompt.

Why it's better: Specific, explains value, defines acronym, front-loads the key benefit.

### Example 2: prompt description

Poor:
> A prompt that helps generate tests.

Good:
> Generates comprehensive unit tests including edge cases and error conditions for TypeScript functions using Jest.

Why it's better: Specifies language, framework, and what "comprehensive" means.

### Example 3: status update

Poor:
> We made good progress this week and things are going well. Some teams are adopting the tools.

Good:
> 3 of 5 departments completed initial assessment. GDS achieved 92% licence activation within 48 hours. MoJ blocked pending security review sign-off (expected: Friday).

Why it's better: Specific numbers, clear status, names the blocker and resolution timeline.

---
