> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Technical lead assessment questionnaire

## Why we are asking for this information

This questionnaire helps us understand your team's technical environment so we can design AI Coding Assistant adoption that works with your existing tools, practices, and constraints. We are gathering information to tailor the right integration approach and guardrails for your specific context.

What happens next: Your responses, along with questionnaires from your delivery manager and team engineers, help us determine how to integrate AI Coding Assistants into your workflows effectively and safely.

Time needed: Approximately 10 to 15 minutes

Confidentiality: Your responses are used only to design your team's adoption plan. No individual team data is shared beyond the programme team.

---

## Technical environment

### 1. Primary programming languages
What languages does your team primarily work in? Select all that apply:
- [ ] python
- [ ] java
- [ ] javascript or typescript
- [ ] c sharp or .NET
- [ ] go
- [ ] ruby
- [ ] php
- [ ] scala
- [ ] kotlin
- [ ] rust
- [ ] legacy languages (COBOL, Fortran, and similar)
- [ ] other (specify): _________________

### 2. Development environments
Where do engineers write code? Select all that apply:
- [ ] local machines with full internet access
- [ ] local machines with restricted internet access
- [ ] virtual desktop infrastructure (VDI)
- [ ] cloud development environments (for example, GitHub Codespaces)
- [ ] secure environments with air-gapped networks
- [ ] mixed depending on project or engineer

### 3. IDEs and editors
What development tools does your team use? Select all that apply:
- [ ] Visual Studio Code
- [ ] IntelliJ IDEA
- [ ] PyCharm
- [ ] Eclipse
- [ ] Visual Studio
- [ ] Vim or Neovim
- [ ] Emacs
- [ ] Sublime Text
- [ ] other (specify): _________________

### 4. Version control
What version control system does your team use?
- [ ] Git (GitHub)
- [ ] Git (GitLab)
- [ ] Git (Bitbucket)
- [ ] Git (Azure DevOps)
- [ ] Git (self-hosted)
- [ ] other version control system (specify): _________________
- [ ] no version control system

---

## Development practices

### 5. Branching strategy
How does your team manage code branches?
- [ ] trunk-based development (frequent small merges to main)
- [ ] feature branching (branches live for days or weeks)
- [ ] GitFlow or similar (release branches, hotfixes, and similar)
- [ ] no formal strategy
- [ ] varies by project

### 6. Code review process
How are code reviews conducted? Select all that apply:
- [ ] pull or merge requests with written review
- [ ] pair programming
- [ ] mob programming
- [ ] asynchronous review using PR comments
- [ ] synchronous review (video calls, in-person)
- [ ] automated review tools only
- [ ] no formal review process

### 7. Automated testing coverage
What is the current state of automated testing in your codebase?
- [ ] comprehensive - most code paths covered
- [ ] good - critical paths well covered
- [ ] moderate - some tests exist but significant gaps
- [ ] limited - minimal test coverage
- [ ] none - no automated tests

### 8. Test types in use
What types of automated tests does your team maintain? Select all that apply:
- [ ] unit tests
- [ ] integration tests
- [ ] end-to-end tests
- [ ] API or contract tests
- [ ] performance tests
- [ ] security tests (SAST or DAST)
- [ ] accessibility tests
- [ ] none currently

### 9. Continuous Integration
How does your team handle CI/CD?
- [ ] full CI/CD pipeline - automated build, test, deploy
- [ ] CI only - automated build and test
- [ ] basic automation - some checks automated
- [ ] manual process - builds and deployments done manually
- [ ] no formal CI/CD

---

## Code quality and standards

### 10. Code quality tools
What automated code quality tools does your team use? Select all that apply:
- [ ] linters (ESLint, Pylint, and similar)
- [ ] static analysis tools (SonarQube, and similar)
- [ ] code formatters (Prettier, Black, and similar)
- [ ] security scanners (Snyk, Dependabot, and similar)
- [ ] complexity analysis tools
- [ ] none currently

### 11. Coding standards
How are coding standards maintained?
- [ ] documented standards with automated enforcement
- [ ] documented standards with manual review
- [ ] informal standards understood by team
- [ ] no formal standards
- [ ] standards exist but not consistently followed

### 12. Documentation practices
How does your team document code?
- [ ] comprehensive inline comments and external documentation
- [ ] inline comments for complex logic
- [ ] README files and high-level architecture docs
- [ ] minimal documentation
- [ ] documentation is a known gap

### 13. Technical debt management
How does your team handle technical debt?
- [ ] tracked and regularly prioritised in sprint planning
- [ ] tracked but rarely addressed (always deprioritised)
- [ ] addressed opportunistically when touching code
- [ ] not formally tracked
- [ ] overwhelmed by technical debt

---

## System architecture and constraints

### 14. System architecture
What architectural patterns does your team primarily work with? Select all that apply:
- [ ] microservices
- [ ] monolithic applications
- [ ] serverless or functions
- [ ] event-driven architecture
- [ ] service-oriented architecture (SOA)
- [ ] legacy mainframe systems
- [ ] mixed or hybrid architecture

### 15. Cloud and infrastructure
Where do your systems run? Select all that apply:
- [ ] public cloud (AWS, Azure, GCP)
- [ ] private cloud
- [ ] on-premises data centres
- [ ] hybrid (mix of cloud and on-premises)
- [ ] legacy infrastructure
- [ ] unsure

### 16. Data handling constraints
What data handling constraints does your team work within? Select all that apply:
- [ ] cannot send code to external AI services
- [ ] cannot send data samples to external services
- [ ] must anonymise any data before using external tools
- [ ] all development work on air-gapped systems
- [ ] standard internet-connected development allowed
- [ ] specific approved tools only (allowlist approach)
- [ ] unsure what constraints apply

### 17. Compliance requirements
What compliance frameworks does your team work within? Select all that apply:
- [ ] Government Security Classifications (OFFICIAL, and similar)
- [ ] GDPR data protection requirements
- [ ] PCI DSS (payment card data)
- [ ] ISO 27001
- [ ] Cyber Essentials or Cyber Essentials Plus
- [ ] no specific compliance requirements
- [ ] other (specify): _________________

---

## Integration and tooling

### 18. Development workflow
Describe a typical workflow from starting a task to deploying code:

_________________

### 19. Tool integration challenges
What would make integrating a new tool into your workflow difficult? Select all that apply:
- [ ] security approval process is lengthy
- [ ] tools must integrate with specific corporate systems
- [ ] network restrictions limit what tools can be used
- [ ] engineers use diverse development setups
- [ ] limited time to learn new tools
- [ ] resistance to changing established workflows
- [ ] budget or procurement constraints
- [ ] other (specify): _________________

### 20. Existing AI tool integration
If engineers currently use AI coding tools (Q15 from delivery manager questionnaire), how are they integrated?
- [ ] not currently using any AI tools
- [ ] standalone tools (browser-based, not IDE-integrated)
- [ ] IDE extensions or plugins
- [ ] API integrations in custom tooling
- [ ] mix of approaches
- [ ] unsure

---

## Technical team capability

### 21. Team's technical practices maturity
How would you characterise your team's development practices?
- [ ] mature - strong practices, well automated, continuously improving
- [ ] developing - good practices in place, some automation, room to improve
- [ ] basic - fundamental practices exist but inconsistently applied
- [ ] ad-hoc - practices vary significantly by engineer or project
- [ ] evolving - practices adapting to delivery demands

### 22. Knowledge sharing
How does technical knowledge spread within your team?
- [ ] structured approaches (docs, tech talks, pair programming)
- [ ] informal but effective (ad-hoc conversations work well)
- [ ] inconsistent (knowledge siloed with specific individuals)
- [ ] developing (building better knowledge sharing practices)

### 23. Legacy system constraints
Do legacy systems or technical constraints significantly limit what your team can do?
- [ ] yes, major constraints (old languages, platforms, limited tooling)
- [ ] yes, moderate constraints (some limitations but workarounds exist)
- [ ] minor constraints (mostly modern stack with some legacy elements)
- [ ] no significant constraints (modern tech stack)

---

## AI Coding Assistant integration

### 24. Anticipated integration challenges
What technical challenges do you anticipate with AI Coding Assistant adoption? Select all that apply:
- [ ] ensuring AI suggestions meet our security requirements
- [ ] integrating with existing code review processes
- [ ] maintaining code quality standards
- [ ] working with legacy codebases
- [ ] network restrictions preventing tool access
- [ ] tool compatibility with our tech stack
- [ ] training AI tools on our specific codebase patterns
- [ ] cost of API usage or token limits
- [ ] other (specify): _________________

### 25. Success criteria
From a technical perspective, what would indicate successful AI Coding Assistant adoption? (Open text)

_________________

### 26. Technical context
Is there anything else about your technical environment that would help us design the right integration approach? (Open text - optional)

_________________

---

#### Thank you for completing this questionnaire.

Your assessment lead will review your responses alongside the delivery manager and individual engineer questionnaires to design your team's adoption approach.

If you have any questions, contact [Assessment Lead contact details].