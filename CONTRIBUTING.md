# Contributing to Dust

Thank you for your interest in contributing to Dust! This document outlines the process for contributing to this project and helps ensure a smooth experience for everyone involved.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Branching Strategy](#branching-strategy)
- [Commit Message Guidelines](#commit-message-guidelines)
- [Pull Request Process](#pull-request-process)
- [Code Style](#code-style)
- [Testing](#testing)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Features](#suggesting-features)

---

## Code of Conduct

This project adheres to a standard code of conduct. By participating, you are expected to uphold a respectful, inclusive, and collaborative environment. Please report any unacceptable behavior to the maintainers.

---

## Getting Started

1. **Fork** the repository on GitHub.
2. **Clone** your fork locally:
   ```bash
   git clone https://github.com/<your-username>/dust.git
   cd dust
   ```
3. Add the upstream remote so you can keep your fork in sync:
   ```bash
   git remote add upstream https://github.com/dust-tt/dust.git
   ```

---

## Development Setup

### Prerequisites

- **Node.js** >= 18 (we recommend using [nvm](https://github.com/nvm-sh/nvm))
- **pnpm** >= 8 (install via `npm install -g pnpm`)
- **Docker** & **Docker Compose** for running local services

### Install Dependencies

```bash
pnpm install
```

### Environment Variables

Copy the example env file and fill in the required values:

```bash
cp .env.example .env
```

Refer to the project README and individual package READMEs for the full list of required environment variables.

### Run Local Services

```bash
docker-compose up -d
```

### Start the Development Server

```bash
pnpm dev
```

---

## Branching Strategy

- `main` — production-ready code. Direct pushes are restricted.
- `feat/<short-description>` — new features.
- `fix/<short-description>` — bug fixes.
- `chore/<short-description>` — maintenance tasks (deps updates, tooling).
- `docs/<short-description>` — documentation-only changes.

Always branch off `main` unless a maintainer specifically instructs otherwise.

---

## Commit Message Guidelines

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>(<scope>): <short summary>

[optional body]

[optional footer]
```

### Types

| Type       | When to use                                          |
| ---------- | ---------------------------------------------------- |
| `feat`     | A new feature                                        |
| `fix`      | A bug fix                                            |
| `docs`     | Documentation only changes                          |
| `style`    | Formatting, missing semicolons, etc. (no logic)     |
| `refactor` | Code change that neither fixes a bug nor adds a feature |
| `test`     | Adding or correcting tests                          |
| `chore`    | Build process, dependency, or tooling changes       |
| `perf`     | Performance improvement                              |
| `ci`       | CI/CD configuration changes                         |

### Examples

```
feat(front): add dark mode toggle to settings page
fix(connectors): handle rate-limit retries for Slack connector
docs: add contributing guide
chore(deps): bump next from 14.1.0 to 14.2.3
```

---

## Pull Request Process

1. **Keep PRs focused** — one logical change per PR. Large PRs are harder to review and more likely to introduce conflicts.
2. **Fill out the PR template** — describe *what* changed and *why*.
3. **Link issues** — use `Closes #<issue>` or `Fixes #<issue>` in the PR body when applicable.
4. **Ensure CI passes** — all status checks must be green before a PR can be merged.
5. **Request a review** — at least one maintainer approval is required.
6. **Resolve review comments** — address all requested changes or discuss them directly in the thread.
7. **Do not force-push** to a branch that is under active review — it makes the review history harder to follow.

---

## Code Style

This project uses ESLint and Prettier to enforce consistent code style. Before pushing:

```bash
# Lint all packages
pnpm lint

# Auto-fix lint issues
pnpm lint --fix

# Format with Prettier
pnpm format
```

Configuration files live at the root (`.eslintrc.*`, `.prettierrc`) and may be overridden in individual packages.

---

## Testing

```bash
# Run all tests
pnpm test

# Run tests for a specific package
pnpm --filter <package-name> test

# Run tests in watch mode
pnpm --filter <package-name> test -- --watch
```

Please add or update tests for any code you change. PRs that reduce test coverage without justification will not be merged.

---

## Reporting Bugs

1. Search [existing issues](https://github.com/dust-tt/dust/issues) to avoid duplicates.
2. Open a new issue using the **Bug Report** template.
3. Include:
   - A clear title and description.
   - Steps to reproduce.
   - Expected vs. actual behavior.
   - Environment details (OS, Node.js version, browser if applicable).
   - Relevant logs or screenshots.

---

## Suggesting Features

1. Search [existing issues](https://github.com/dust-tt/dust/issues) to avoid duplicates.
2. Open a new issue using the **Feature Request** template.
3. Describe the problem the feature solves and your proposed solution.
4. Maintainers will triage and prioritize feature requests during regular planning cycles.

---

Thanks again for contributing — we appreciate your time and effort! 🎉
