# Contributing to llm.cr

Thank you for your interest in contributing to llm.cr!
This document provides guidelines and information to help you get started.

## Table of Contents

- [Development Setup](#development-setup)
- [Project Architecture](#project-architecture)
- [Running Tests](#running-tests)
- [Code Coverage](#code-coverage)
- [Code Style](#code-style)
- [Submitting Changes](#submitting-changes)

## Development Setup

### Prerequisites

- [Crystal](https://crystal-lang.org/install/) >= 1.18.2 (I recommend using [mise](https://github.com/jdx/mise))
- [Hace](https://github.com/ralsina/hace) task runner (could be installed via shards)
- [Lefthook](https://github.com/evilmartians/lefthook#install) - Git hooks manager

### Setup

1. Clone the repository:

```bash
git clone https://github.com/crys-ai/llm.cr.git
cd llm.cr
```

1. Install dependencies and build tools:

```bash
shards install
shards build ameba
shards build hace # currently broken due to upstream bug, better install via yay or copy an older binary to /bin
```

1. Install git hooks:

```bash
lefthook install
```

1. Run tests:

```bash
bin/hace spec
```

## Project Architecture

TBD

### Module Overview

TBD

## Running Tests

```bash
# Run all tests
bin/hace spec

# Run specific test file
crystal spec spec/llm/somefile.cr

# Run with verbose output
crystal spec --verbose
```

## Code Coverage

Code coverage is automatically generated and uploaded to [Codecov](https://codecov.io) on every push to `main`. The CI workflow uses [kcov](https://github.com/SimonKagstrom/kcov) to measure coverage.

View coverage reports at: `https://codecov.io/gh/crys-ai/llm.cr`

### Available Tasks

Run `bin/hace --list` to see all available tasks. Key tasks:

| Task              | Description            |
| ----------------- | ---------------------- |
| `bin/hace spec`   | Run crystal spec       |
| `bin/hace format` | Format code            |
| `bin/hace ameba`  | Run Ameba linter       |
| `bin/hace all`    | Format, lint, and test |
| `bin/hace clean`  | Clean build artifacts  |

### Pre-commit Hooks

The project uses Lefthook for pre-commit hooks. They run automatically on commit:

- `bin/hace format` - Code formatting
- `bin/hace ameba` - Static analysis
- `yamlfmt` - YAML formatting

To run hooks manually:

```bash
lefthook run pre-commit
```

## Code Style

- Follow Crystal's standard formatting (`bin/hace format`)
- Use `bin/hace ameba` for static analysis
- Keep methods focused and small
- Document public methods with Crystal doc comments
- Use meaningful variable and method names

## Submitting Changes

1. **Fork** the repository
2. **Create a branch** for your feature or fix
3. **Write tests** for new functionality
4. **Run `bin/hace all`** to format, lint, and test
5. **Commit** with a clear message
6. **Push** and create a Pull Request

### Commit Message Format

```
Add feature description

- Bullet points for specific changes
- Keep it concise but informative
```

### Pull Request Guidelines

- Reference any related issues
- Describe what changed and why
- Include test coverage for new features
- Update documentation if needed

## Questions?

Open an issue if you have questions or need guidance on a contribution.
