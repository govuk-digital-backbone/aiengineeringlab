# Go style guide for CLAUDE.md

Paste the relevant sections of this file into your project's `CLAUDE.md` to enforce Go coding standards aligned with the [GDS Way Go guidance](https://gds-way.digital.cabinet-office.gov.uk/manuals/programming-languages/go.html).

---

## Go coding standards

Follow [Effective Go](https://go.dev/doc/effective_go), the [Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments), and the [Uber Go Style Guide](https://github.com/uber-go/guide/blob/master/style.md). Use `gofmt` and `goimports` for automatic formatting.

### Formatting

You should:

- always run `gofmt` before committing, never commit unformatted Go code
- use `goimports` to manage import grouping and removal of unused imports automatically
- follow the standard Go import order: standard library, then external packages, then internal packages - separate groups with blank lines

### Naming

You should:

- use short, descriptive names - prefer `r` for an `http.Request`, `w` for an `http.ResponseWriter`
- use `camelCase` for unexported identifiers and `PascalCase` for exported identifiers
- use `UPPER_SNAKE_CASE` only for `cgo` constants where required by convention
- acronyms in names should be consistently cased: `userID` not `userId`, `HTTPServer` not `HttpServer`
- package names should be lowercase, single words without underscores or mixed case
- avoid redundant package prefixes in names (use `http.Server` not `http.HTTPServer`)

### Error handling

You should:

- always handle errors explicitly - never use `_` to discard an error unless the reason is clearly commented
- return errors as the last return value
- wrap errors with context using `fmt.Errorf("doing X: %w", err)` so callers can inspect them
- define custom error types for errors that callers need to act on
- do not use `panic` for normal error handling, reserve it for truly unrecoverable states

### Functions and packages

You should:

- keep functions focused on a single responsibility
- limit function parameters, if a function takes more than 4 parameters, consider grouping them in a struct
- use interfaces to describe behaviour, not data
- define interfaces in the package that uses them, not the package that implements them
- keep package scope small and unexport anything that does not need to be public

### Concurrency

You should:

- use goroutines and channels as described in [Share Memory by Communicating](https://go.dev/blog/codelab-share)
- always document whether a type or function is safe for concurrent use
- use `context.Context` as the first argument to functions that perform I/O or can be cancelled
- cancel contexts when they are no longer needed to avoid goroutine leaks
- use `sync.WaitGroup`, `sync.Mutex`, or channels rather than busy-waiting

### Testing

You should:

- write tests using the standard `testing` package
- use [testify](https://github.com/stretchr/testify) for assertions where the team agrees on it
- name test files `*_test.go` in the same package as the code under test
- use table-driven tests for functions with multiple input/output combinations
- use `t.Helper()` in test helper functions
- aim for good coverage of error paths, not just the happy path

### Tooling

You should:

- use Go modules (`go.mod` and `go.sum`) and commit both files to source control
- run `go vet` and [staticcheck](https://staticcheck.io) in your CI pipeline
- use [golangci-lint](https://golangci-lint.run) with a project-level `.golangci.yml` configuration
- pin external dependencies to specific versions in `go.mod`

### Security

You should:

- never hardcode secrets, API keys, or credentials - use environment variables or a secrets manager
- validate and sanitise all user-supplied input
- use `crypto/rand` for cryptographically secure random values, not `math/rand`
- use parameterised queries with your database driver - never build SQL strings from user input
- run [govulncheck](https://pkg.go.dev/golang.org/x/vuln/cmd/govulncheck) to identify known vulnerabilities in dependencies
