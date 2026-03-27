# Java style guide for CLAUDE.md

Paste the relevant sections of this file into your project's `CLAUDE.md` to enforce Java coding standards aligned with the [GDS Way Java guidance](https://gds-way.digital.cabinet-office.gov.uk/manuals/programming-languages/java.html).

---

## Java coding standards

Follow the [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html) with the adaptations below. Use [Checkstyle](https://checkstyle.org) or [Spotless](https://github.com/diffplug/spotless) for automated formatting.

### Formatting

You should:

- use 4-space indentation - never use tabs
- limit lines to 120 characters
- use [google-java-format](https://github.com/google/google-java-format) for automatic formatting
- place opening braces on the same line as the statement (K&R style) - do not use Allman style
- always use braces for `if`, `else`, `for`, `while`, and `do` bodies, even single-line ones

### Naming

You should:

- use `camelCase` for variable and method names
- use `PascalCase` for class and interface names
- use `UPPER_SNAKE_CASE` for constants (`static final` fields)
- use `camelCase` for package names in a single lowercase word per segment (for example `gov.uk.department.service`)
- interface names should describe a capability or role, not start with `I` (for example `UserRepository` not `IUserRepository`)

### Classes and methods

You should:

- keep classes and methods small and focused on a single responsibility
- prefer composition over inheritance
- favour interfaces over abstract classes for defining contracts
- mark classes `final` unless they are designed for inheritance
- use `@Override` on all overriding methods
- minimise the scope of local variables - declare them as close to use as possible
- use `final` for local variables and parameters that are not reassigned

### Modern Java features

You should:

- target Java 17 or later for new services (LTS release)
- use records for simple data carriers
- use sealed classes and pattern matching where appropriate
- use `Optional` for return types that may be absent - do not use `null` as a return value from public APIs
- use the Stream API and lambdas for collection processing, but favour readability over conciseness
- use `var` for local variables where the type is obvious from the right-hand side

### Error handling

You should:

- use checked exceptions only for recoverable conditions that callers are expected to handle
- use unchecked exceptions (extending `RuntimeException`) for programming errors
- do not catch and swallow exceptions silently
- log exceptions at the appropriate level with enough context to debug
- use try-with-resources for all `Closeable` and `AutoCloseable` resources

### Dependency injection and frameworks

You should:

- use [Spring Boot](https://spring.io/projects/spring-boot) as the standard framework for new services, following GDS Way guidance
- prefer constructor injection over field injection for mandatory dependencies
- annotate Spring components with the narrowest applicable stereotype (`@Repository`, `@Service`, `@Controller`)

### Testing

You should:

- write unit tests using [JUnit 5](https://junit.org/junit5/) and [Mockito](https://site.mockito.org)
- write integration tests using Spring Boot Test (`@SpringBootTest`) or [Testcontainers](https://testcontainers.com) for database and external service dependencies
- name test methods to describe the scenario and expected outcome (for example `shouldReturnNotFoundWhenUserDoesNotExist`)
- aim for 80% or higher code coverage on new code
- run [ArchUnit](https://www.archunit.org) tests to enforce architectural rules

### Tooling

You should:

- use [Maven](https://maven.apache.org) or [Gradle](https://gradle.org) - pick one and apply it consistently across your service
- pin dependency versions in `pom.xml` or `build.gradle`. Do not use version ranges in production code
- run Checkstyle, SpotBugs, and OWASP Dependency Check in your CI pipeline

### Security

You should:

- never hardcode secrets, API keys, or credentials - use environment variables or a secrets manager
- use parameterised queries or an ORM with parameterised queries - never build SQL from user input
- validate all user-supplied input at the boundary of the application
- use the Spring Security framework for authentication and authorisation
- run [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/) to identify known vulnerabilities in dependencies
