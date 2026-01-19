> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Contributing to this repository

> How to propose, submit, and review contributions to the AI Engineering Lab Best Practice Repository.

Thank you for your interest in improving this repository. Contributions from across government help keep these materials current, comprehensive, and practically useful.

## Before you contribute

### Who can contribute

This repository welcomes contributions from:

- Civil servants across all government departments
- Contractors and suppliers working on government projects
- Arm's length bodies and agencies
- Forward Deployed Engineers (FDEs) capturing learnings from engagements

### Types of contribution

| Contribution type | Examples | Process |
|-------------------|----------|---------|
| Bug fixes | Typos, broken links, factual errors | Quick fix process |
| Minor improvements | Clarifications, additional examples, formatting | Standard process |
| New content | New playbooks, prompts, case studies | Full review process |
| Structural changes | New sections, reorganisation | Proposal required |
| Tool-specific guides | New AI assistant coverage | Full review + security assessment |

### What we're looking for

We particularly welcome:

- Practical examples from real adoption experiences
- Prompts that have proven effective in government contexts
- Case studies (anonymised where necessary)
- Accessibility improvements
- Corrections to outdated information
- Integration patterns for government technology stacks
- Translations or plain English improvements

### What requires additional review

The following contributions require security or governance review before merging:

- Content relating to security controls or guardrails
- Tool-specific configuration guidance
- Incident response procedures
- Any content mentioning specific vulnerabilities
- Integration patterns involving authentication or secrets

### Writing style

All content must follow [GOV.UK content design principles](https://www.gov.uk/guidance/content-design/writing-for-gov-uk):

1. **Use plain English** - Avoid jargon; explain technical terms on first use
2. **Use active voice** - Write "Review the code" not "The code should be reviewed"
3. **Front-load information** - Put the most important point first
4. **Keep sentences short** - Aim for 25 words or fewer per sentence
5. **Use short paragraphs** - One idea per paragraph; 2-3 sentences maximum
6. **Be direct** - Use "you" to address the reader; use "we" for the repository team

### Formatting standards

**Headings:**
- Use sentence case (capitalise first word only)
- Use heading levels sequentially (don't skip from H2 to H4)
- Keep headings descriptive and actionable

**Lists:**
- Use bullet points for unordered items
- Use numbered lists only for sequential steps
- Start each item with a capital letter
- Don't use full stops at the end of list items unless they're complete sentences

**Code examples:**
- Use fenced code blocks with language identifiers
- Keep examples concise and focused
- Include comments explaining non-obvious elements
- Test all code examples before submitting

**Links:**
- Use descriptive link text (not "click here")
- Use relative links for internal repository references
- Check all links work before submitting

## Accessibility requirements

All contributions must meet accessibility standards. Before submitting:

### Text content

- [ ] Use clear, simple language (aim for reading age 9)
- [ ] Provide alt text descriptions for any images
- [ ] Don't use colour alone to convey meaning
- [ ] Define acronyms on first use
- [ ] Use descriptive link text

### Structure

- [ ] Use proper heading hierarchy
- [ ] Use semantic markup (lists, tables, headings)
- [ ] Keep tables simple; avoid merged cells
- [ ] Provide table headers for data tables

### Code examples

- [ ] Don't rely on syntax highlighting alone
- [ ] Include comments for complex logic
- [ ] Ensure examples are screen-reader friendly when rendered

### Cognitive accessibility

- [ ] Break complex content into manageable chunks
- [ ] Use consistent terminology throughout
- [ ] Provide summaries for long documents
- [ ] Include practical examples alongside theory

For detailed guidance, see the repository's accessibility documentation.

## Contribution process

### Quick fixes (typos, broken links)

For simple corrections that don't change meaning:

1. Fork the repository
2. Make your change in a new branch
3. Submit a pull request with a clear description
4. A maintainer will review and merge within [PLACEHOLDER: X] working days

### Standard contributions

For improvements, clarifications, and new examples:

1. **Check existing content** - Ensure your contribution isn't duplicating existing material
2. **Open an issue first** - Describe what you're proposing and why
3. **Wait for feedback** - A maintainer will respond within [PLACEHOLDER: X] working days
4. **Fork and branch** - Create a branch with a descriptive name
   - Use format: `type/brief-description`
   - Examples: `fix/broken-copilot-link`, `add/terraform-prompt-examples`
5. **Make your changes** - Follow content standards above
6. **Self-review** - Check against the quality checklist below
7. **Submit pull request** - Reference the original issue
8. **Respond to feedback** - Make requested changes promptly
9. **Approval and merge** - Maintainers will merge approved contributions

### New content or structural changes

For significant new content or repository changes:

1. **Submit a proposal** - Open an issue using the "Content Proposal" template
2. **Include in your proposal:**
   - What you're proposing
   - Why it's needed
   - Who will benefit
   - Outline of content structure
   - Estimated effort
   - Any security or governance considerations
3. **Proposal review** - The team will review within [PLACEHOLDER: X] working days
4. **Approval to proceed** - You'll receive feedback and approval (or suggestions for alternative approaches)
5. **Create content** - Follow the standard contribution process above
6. **Enhanced review** - New content receives additional scrutiny from subject matter experts

## Quality checklist

Before submitting, verify your contribution against this checklist:

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

- [ ] Suitable for OFFICIAL classification
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

Maintainers review contributions for:

1. **Alignment** - Does it fit the repository's purpose and scope?
2. **Quality** - Does it meet content standards?
3. **Accuracy** - Is the technical content correct?
4. **Security** - Is it safe for government use?
5. **Accessibility** - Does it meet accessibility standards?
6. **Consistency** - Does it align with existing content?

### Review outcomes

- **Approved** - Merged as submitted
- **Approved with changes** - Minor edits made by maintainer before merge
- **Changes requested** - Feedback provided; contributor makes updates
- **Declined** - Doesn't meet requirements; feedback provided

## Recognition

Contributors are recognised through:

- Attribution in document metadata where appropriate
- Listing in the repository's contributors file
- Acknowledgement in release notes for significant contributions

## Code of conduct

All contributors must adhere to the [Civil Service Code](https://www.gov.uk/government/publications/civil-service-code/the-civil-service-code) principles:

- **Integrity** - Act with honesty and impartiality
- **Honesty** - Be truthful and transparent
- **Objectivity** - Base advice on evidence
- **Impartiality** - Act without bias

Additionally:

- Be respectful and constructive in all interactions
- Focus feedback on content, not individuals
- Assume good intent from other contributors
- Maintain confidentiality where required
- Report concerns to [PLACEHOLDER: contact for reporting concerns]

## Getting help

If you need assistance with contributing:

| Need | Contact |
|------|---------|
| Process questions | [PLACEHOLDER: team email] |
| Technical guidance | [PLACEHOLDER: technical contact] |
| Content standards | [PLACEHOLDER: content contact] |
| Accessibility advice | [PLACEHOLDER: accessibility contact] |

[PLACEHOLDER: Add Slack/Teams channels if available]

## Intellectual property

By contributing to this repository, you confirm that:

1. Your contribution is your own original work, or you have permission to submit it
2. You have the right to grant the licence below
3. Your contribution doesn't infringe any third-party intellectual property rights
4. Your contribution is suitable for publication under the Open Government Licence

Contributions are published under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).

## Related documents

- [README.md](README.md) - Repository overview

## References

- [GOV.UK Content Design Guide](https://www.gov.uk/guidance/content-design)
- [GOV.UK Writing for GOV.UK](https://www.gov.uk/guidance/content-design/writing-for-gov-uk)
- [Civil Service Code](https://www.gov.uk/government/publications/civil-service-code/the-civil-service-code)
- [Open Government Licence](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/)
