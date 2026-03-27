# Shell and Bash style guide for CLAUDE.md

Paste the relevant sections of this file into your project's `CLAUDE.md` to enforce Shell and Bash coding standards aligned with the [GDS Way Bash guidance](https://gds-way.digital.cabinet-office.gov.uk/manuals/programming-languages/bash.html).

---

## Shell and Bash coding standards

Follow the [Google Shell Style Guide](https://google.github.io/styleguide/shellguide.html). Use [ShellCheck](https://www.shellcheck.net) for automated linting.

### When to use Bash

You should:

- use Bash for scripts that glue together other tools, automate workflows, or run in CI pipelines
- if a script exceeds approximately 100 lines or requires complex data structures, consider rewriting it in Python or another scripting language
- bash is not appropriate for scripts that need to be portable across shells (use `#!/bin/sh` and POSIX syntax, or switch to Python)

### File structure

You should:

- always start scripts with a shebang: `#!/usr/bin/env bash`
- add a brief comment block after the shebang describing what the script does, its inputs, and its outputs
- make scripts executable: `chmod +x script.sh`
- name script files with a `.sh` extension

### Error handling and safety

You should:

- always start scripts with the following options unless you have a specific reason not to:

  ```bash
  set -euo pipefail
  ```

  - `set -e` exits immediately on error
  - `set -u` treats unset variables as errors
  - `set -o pipefail` returns the exit code of the first failed command in a pipeline

- clean up temporary files using a `trap` on `EXIT`:

  ```bash
  trap 'rm -f "$TMPFILE"' EXIT
  ```

- check whether required external commands exist before calling them:

  ```bash
  command -v jq >/dev/null 2>&1 || { echo "jq is required but not installed." >&2; exit 1; }
  ```

### Variables and quoting

You should:

- quote all variable expansions: `"$variable"` not `$variable`
- quote command substitutions: `"$(command)"` not `` `command` ``
- use `local` for variables inside functions to limit their scope
- use `readonly` for variables that should not be reassigned
- use uppercase names for environment variables and constants exported to child processes
- use lowercase names for local variables within scripts

### Functions

You should:

- define functions using the `function_name()` syntax without the `function` keyword
- place all function definitions before the main script body
- document each function with a comment block describing its purpose, arguments, and return value
- keep functions short and focused on a single task

### Control flow

You should:

- use `[[` instead of `[` for conditionals in Bash scripts
- use `$(command)` instead of backticks for command substitution
- use `(( ))` for arithmetic evaluation
- avoid `eval` - if it is unavoidable, validate and sanitise the input first

### Output and logging

You should:

- send diagnostic and error messages to stderr: `echo "Error: something went wrong" >&2`
- use consistent log level prefixes such as `INFO:`, `WARN:`, and `ERROR:` for scripts that produce output
- do not produce output unless it is meaningful - suppress noisy command output with `>/dev/null 2>&1` where appropriate

### Tooling

You should:

- run [ShellCheck](https://www.shellcheck.net) on all shell scripts in your CI pipeline - fix all warnings
- use `shellcheck -x` to follow `source` statements
- format scripts consistently - consider [shfmt](https://github.com/mvdan/sh) for automatic formatting with a 2-space indent

### Security

You should:

- never hardcode secrets, API keys, or passwords in scripts - use environment variables or a secrets manager
- avoid constructing commands from user input - if unavoidable, validate and sanitise rigorously
- do not run scripts as root unless absolutely necessary - use `sudo` for individual privileged commands
- avoid world-writable temporary files - use `mktemp` to create temporary files safely
- review scripts from external sources before running them - do not pipe `curl` output directly into `bash` in production
