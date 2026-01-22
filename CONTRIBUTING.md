> **ALPHA**: This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# Contributing to this repository

This guide outlines how to propose, submit, and review contributions to this repository. We welcome all contributions from across government as they help us to keep these materials current, comprehensive, and useful.

## 1. Before you contribute

### Who can contribute

This repository accepts contributions from:

- civil servants across all government departments
- contractors and suppliers working on government projects
- arm's length bodies and agencies
- forward deployed engineers (FDEs) who are capturing learnings from engagements

### Types of contribution

| Contribution type | Examples | Process |
|-------------------|----------|---------|
| Bug fixes | Typos, broken links, factual errors | Quick fix process |
| Minor improvements | Clarifications, additional examples, formatting | Standard process |
| New content | New playbooks, prompts, case studies | Full review process |
| Structural changes | New sections, reorganisation | Proposal required |
| Tool-specific guides | New AI assistant coverage | Full review and security assessment |

### What you should submit

We're accepting material which includes:

- practical examples from real adoption experiences
- prompts that have proven effective in government contexts
- anonymised case studies
- accessibility improvements
- corrections to outdated information
- integration patterns for government technology stacks
- translations or plain English improvements

### What requires additional review

Some contributions will require security or governance reviews before merging. These include:

- content relating to security controls or guardrails
- tool-specific configuration guidance
- incident response procedures
- any content mentioning specific vulnerabilities
- integration patterns involving authentication or secrets

### Writing style

All content must follow [GOV.UK content design principles](https://www.gov.uk/guidance/content-design/writing-for-gov-uk). In short, this means you must:

- use plain English to avoid jargon, and you should explain technical terms on first use
- use active voice, such as *'review the code'* instead of *'the code should be reviewed'*
- front-load information by putting most important point first
- keep sentences short by aiming for 25 words or fewer per sentence
- use short paragraphs of one idea per paragraph with a maximum of 2 to 3 sentences
- be direct by using *'you'* to address the reader and *'we'* for the repository team

### Formatting standards

**Headings:**  

All headings must:
- use sentence case (capitalise only the first word)
- use heading levels sequentially (don't skip from H2 to H4)
- be descriptive and actionable

**Lists:**  

All lists must:
- use bullet points for unordered items
- use numbered lists only for sequential steps
- if a bullet list, it should:
   - start with a lead-in line which completes a full sentence with each item
   - start with a lowercase letter
   - end with any punctuation (such as full stops or commas)
- if a numbered list item is a complete step in itself, it can:
   - start with an uppercase letter
   - end in punctuation

**Code examples:**  

All code examples must:
- use fenced code blocks with language identifiers
- be concise and focused
- include comments explaining non-obvious elements
- be checked before submitting

**Links:**  

All links must:
- reflect the title of the linked page and not just be *'click here'*
- be relevant for internal repository references
- checked before submission

Detailed guidance on how to write content can be found on the [A to Z Style Guide](https://www.gov.uk/guidance/style-guide/a-to-z).

## 2. Accessibility requirements

All contributions must meet the following accessibility standards.

### Text content  

All text content must:

- use clear, simple language (aim for around a standard reading age of 9)
- include alt text descriptions for all images
- not use colour alone to convey meaning
- define acronyms on first use
- use descriptive link text

### Structure

All content structure must:

- use proper heading hierarchy
- use semantic markup, including lists, tables and headings
- contain only simple tables without merged cells
- include table headers for data tables

### Code examples

All code examples must: 

- not rely on syntax highlighting alone
- include comments for complex logic
- be screen-reader friendly when rendered

### Cognitive accessibility

To meet cognitive accessibilty requirements, you must:

- break complex content into manageable chunks
- use consistent terminology throughout
- provide summaries for long documents
- include practical examples alongside theory

## 3. Contribution process  

If you'd like to contribute to this repo, you must following a set process.

### Quick fixes

A quick fix is something that doesn't change the meaning of the content, such as correcting broken links and typos. To submit a fix, you must:

1. fork the repository
2. make your change in a new branch
3. submit a pull request with a clear description

After submission, one of our team will aim to review and merge your fix within 10 working days.

### Standard contributions

For improvements, clarifications, and new examples, you must:

1. check existing content to ensure that your contribution isn't duplicating existing material
2. open an issue to describe what you're proposing and why
3. wait for feedback, which we aim to provide within 10 working days
4. fork and create a branch with a descriptive name, using this format: *`type/brief-description`*. For example - *`fix/broken-copilot-link`* or *`add/terraform-prompt-examples`*
5. make your changes by following the content standards above
6. self-review by checking against the quality checklist below
7. submit a pull request, ensuring you reference the original issue
8. respond to feedback by making requested changes promptly

After submission, one of our team will aim to approve and merge your fix within 10 working days.

### New content or structural changes

For significant new content or repository changes, you must first submit a proposal by opening an issue which contains:
   - what you're proposing
   - why it's needed
   - who will benefit
   - an outline of the content structure
   - estimated effort
   - any security or governance considerations

Our team will aim to review your proposal within 10 working days. After this you'll receive feedback and approval to proceed, or suggestions for alternative approaches. You can then create your content by following the standard contribution process above.

Finally, your new content will receive additional scrutiny from subject matter experts.

## 4. Quality checklist

Use this checklist to ensure that your contribution is suitable.

### Content quality

- [ ] Follows GOV.UK writing style
- [ ] Accurate and factually correct
- [ ] Provides practical, actionable guidance
- [ ] Includes relevant examples
- [ ] Appropriate for government context
- [ ] Doesn't duplicate existing content

### Technical accuracy

- [ ] Code examples are tested and working
- [ ] Commands and configurations are correct
- [ ] Version numbers and links are current
- [ ] Tool-specific guidance matches current tool versions

### Security and governance

- [ ] Suitable for [OFFICIAL classification](https://www.gov.uk/government/publications/government-security-classifications/government-security-classifications-policy-html#definitions-for-official-secret-and-top-secret)
- [ ] Doesn't expose sensitive information
- [ ] Follows security best practices
- [ ] Doesn't include real credentials, keys, or secrets
- [ ] Aligns with guardrails and compliance requirements

### Accessibility

- [ ] Meets accessibility requirements above
- [ ] Tested with accessibility tools where applicable

### Metadata

- [ ] Document metadata is complete
- [ ] Version number is appropriate
- [ ] Links to related documents are included
- [ ] References are properly cited

### What reviewers check

Our reviewers check contributions for:

- alignment to make sure it fits the repository's purpose and scope
- quality, so that it meets content standards
- technical accuracy
- security, so that it's safe for government use
- meeting accessibility standards
- consistency, so it aligns with existing content

### Review outcomes

**Approved** - merged as submitted.  
**Approved with changes** - minor edits made by reviewer before merge.  
**Changes requested** - feedback provided and you must make updates.  
**Declined** - content doesn't meet requirements. Additional feedback will be provided.  

## 5. Recognition

Contributors are recognised through:

- attribution in document metadata where appropriate
- listing in the repository's contributors file
- acknowledgement in release notes for significant contributions

## 5. Code of conduct

All contributors must adhere to the [Civil Service Code](https://www.gov.uk/government/publications/civil-service-code/the-civil-service-code) principles. These include:

- integrity, by acting with impartiality
- honesty, by being truthful and transparent
- objectivity, where all advice is based on evidence
- impartiality, where there is no bias

Additionally, we ask that you:

- be respectful and constructive in all interactions
- focus feedback on content, not individuals
- assume good intent from other contributors
- maintain confidentiality where required
- Report any concerns

## 6. Getting help

If you need assistance with contributing:

| Need | Contact |
|------|---------|
| Process questions | TBD |
| Technical guidance | TBD |
| Content standards | TBD |
| Accessibility advice | TBD |

## 7. Intellectual property

By contributing to this repository, you confirm that:

1. your contribution is your own original work, or that you have permission to submit it
2. you have the right to grant the licence below
3. your contribution doesn't infringe any third-party intellectual property rights
4. your contribution is suitable for publication under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/)

## 8. Related documents

- [README.md](README.md) - Repository overview
