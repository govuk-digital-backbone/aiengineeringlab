# Ruby style guide for CLAUDE.md

Paste the relevant sections of this file into your project's `CLAUDE.md` to enforce Ruby coding standards aligned with the [GDS Way Ruby guidance](https://gds-way.digital.cabinet-office.gov.uk/manuals/programming-languages/ruby.html).

---

## Ruby coding standards

Follow the [Ruby Style Guide](https://rubystyle.guide) enforced by [RuboCop](https://rubocop.org) with the GDS RuboCop configuration.

### Formatting

You should:

- use 2-space indentation - never use tabs
- limit lines to 120 characters
- use UTF-8 file encoding
- add a newline at the end of every file
- add `# frozen_string_literal: true` at the top of every Ruby file

### Naming

You should:

- use `snake_case` for methods, variables, and file names
- use `CamelCase` for classes and modules
- use `SCREAMING_SNAKE_CASE` for constants
- use `?` suffix for predicate methods that return a boolean
- use `!` suffix for methods that raise an exception or mutate the receiver
- prefix unused variables with `_`

### Strings

You should:

- prefer single-quoted strings unless interpolation or special characters are needed
- use string interpolation (`"Hello, #{name}"`) over concatenation
- avoid `%q` and `%Q` string literals unless the string contains many quotes

### Collections

You should:

- use symbols as hash keys (`:key` not `'key'`)
- use the new hash syntax (`{ key: value }` not `{ :key => value }`)
- use `[]` and `{}` for array and hash literals, not `Array.new` or `Hash.new`
- prefer `map`, `select`, `reject`, and `find` over `each` with mutation

### Methods and classes

You should:

- keep methods under 10 lines where possible
- avoid more than 3 levels of nesting
- use `attr_reader`, `attr_writer`, and `attr_accessor` instead of manual getter/setter methods
- prefer `protected` over `private` when subclasses need access
- avoid `self.` prefix on instance methods unless required for disambiguation

### Error handling

You should:

- rescue specific exception classes, not bare `rescue Exception`
- always log rescued exceptions with enough context to debug
- do not use exceptions for flow control

### Testing

You should:

- write tests using RSpec
- use `describe` for classes, `context` for scenarios, and `it` for behaviour
- use `let` and `let!` over instance variables in tests
- use `expect(...).to` not `....should`
- name test files `*_spec.rb` mirroring the path of the file under test

### Tooling

You should:

- run `rubocop` before committing - fix all offences or add justified inline disables with a comment explaining why
- use `bundle exec` to run commands within a Bundler context
- pin gem versions in `Gemfile.lock` and commit it to source control

### Security

You should:

- never hardcode secrets, API keys, or credentials - use environment variables
- use `strong_parameters` in Rails controllers to prevent mass assignment
- sanitise all user-supplied input before use in SQL queries or shell commands
