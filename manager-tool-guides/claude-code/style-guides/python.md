# Python style guide for CLAUDE.md

Paste the relevant sections of this file into your project's `CLAUDE.md` to enforce Python coding standards aligned with the [GDS Way Python guidance](https://gds-way.digital.cabinet-office.gov.uk/manuals/programming-languages/python.html).

---

## Python coding standards

Follow [PEP 8](https://peps.python.org/pep-0008/) enforced by [flake8](https://flake8.pycqa.org) or [ruff](https://docs.astral.sh/ruff/). Use [black](https://black.readthedocs.io) for automatic formatting.

### Formatting

You should:

- use 4-space indentation - never use tabs
- limit lines to 79 characters for code, 72 for docstrings and comments
- use `black` for automatic formatting with default settings
- use UTF-8 file encoding - add `# -*- coding: utf-8 -*-` only if required by tooling
- add a newline at the end of every file

### Naming

You should:

- use `snake_case` for functions, methods, variables, and module names
- use `PascalCase` for class names
- use `UPPER_SNAKE_CASE` for module-level constants
- prefix private attributes and methods with a single underscore (`_`)
- avoid double-underscore names except for Python dunder methods

### Imports

You should:

- order imports: standard library, then third-party packages, then local modules - separate each group with a blank line
- use absolute imports - avoid relative imports except within packages
- never use wildcard imports (`from module import *`)
- use `isort` to sort imports automatically

### Strings

You should:

- use double quotes for strings unless the string contains a double quote
- use f-strings for string interpolation (`f"Hello, {name}"`) in preference to `.format()` or `%` formatting
- use triple double-quoted strings for docstrings (`"""`)

### Type hints

You should:

- add type hints to all public functions and methods
- use `from __future__ import annotations` for forward references
- use `Optional[T]` or `T | None` for nullable types
- run [mypy](https://mypy-lang.org) in strict mode for new code

### Functions and classes

You should:

- keep functions under 20 lines where possible
- write a docstring for every public module, class, function, and method
- use dataclasses or Pydantic models for structured data instead of plain dicts
- prefer composition over inheritance

### Error handling

You should:

- catch specific exception classes, not bare `except Exception` or `except:`
- always include a message when raising exceptions
- use `logging` for error reporting, not `print`
- do not use exceptions for flow control

### Testing

You should:

- write tests using [pytest](https://pytest.org)
- place tests in a `tests/` directory mirroring the source structure
- name test files `test_*.py` and test functions `test_*`
- use fixtures for shared setup - avoid global test state
- aim for 80% or higher code coverage on new code using `pytest-cov`

### Tooling

You should:

- use a virtual environment (`venv` or `poetry`) - never install packages globally
- pin dependencies in `requirements.txt` or `pyproject.toml`
- run `flake8` or `ruff`, `black --check`, and `mypy` in your CI pipeline

### Security

You should:

- never hardcode secrets, API keys, or credentials - use environment variables or a secrets manager
- use `secrets` module for cryptographic random values, not `random`
- sanitise all user-supplied input before use in SQL queries or shell commands
- use parameterised queries with your database driver, never string concatenation
