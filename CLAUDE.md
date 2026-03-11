# CLAUDE.md

This file provides guidance for AI assistants (e.g., Claude Code) working in
this repository. It captures the project structure, conventions, and workflows
that should be followed when making changes.

---

## Repository Overview

> **Note:** This repository was initialized without initial source code.
> Update this section once the project is bootstrapped with its technology
> stack and purpose.

- **Project name:** nomu
- **Description:** *(add a short description here)*
- **Primary language(s):** *(e.g., TypeScript, Python, Go, Rust)*
- **Framework(s):** *(e.g., Next.js, FastAPI, Gin)*

---

## Directory Structure

```
nomu/
├── CLAUDE.md          # This file
├── README.md          # Human-facing project documentation (add when ready)
└── ...                # Source code added during project setup
```

Update this tree as the project grows.

---

## Getting Started

### Prerequisites

*(List required tools, runtimes, and versions once the stack is decided.)*

```bash
# Example — replace with actual commands
node --version   # >= 20
python --version # >= 3.11
```

### Installation

```bash
# Clone and install dependencies
git clone <repo-url>
cd nomu
# <install command, e.g.: npm install / pip install -r requirements.txt>
```

### Running the Project

```bash
# Development server (update once known)
# npm run dev
# python -m uvicorn app.main:app --reload
```

---

## Development Workflow

### Branching Strategy

| Branch pattern | Purpose |
|---|---|
| `main` | Stable, production-ready code |
| `feat/<description>` | New features |
| `fix/<description>` | Bug fixes |
| `chore/<description>` | Tooling, deps, non-functional changes |
| `claude/<ticket-id>` | AI-assisted development branches |

**Never push directly to `main`.** Always open a pull request.

### Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <short summary>

[optional body]

[optional footer]
```

Common types: `feat`, `fix`, `refactor`, `test`, `docs`, `chore`, `ci`.

Examples:
```
feat(auth): add JWT refresh token support
fix(api): handle null user in profile endpoint
docs: update installation instructions
```

### Pull Requests

- Keep PRs focused — one concern per PR.
- Include a clear description of *what* changed and *why*.
- Ensure tests pass and linting is clean before requesting review.
- Reference related issues: `Closes #123`.

---

## Testing

*(Update this section once the test framework is chosen.)*

```bash
# Run all tests
# npm test / pytest / go test ./... / cargo test

# Run with coverage
# npm run test:coverage / pytest --cov

# Run a single test file
# npx jest src/foo.test.ts / pytest tests/test_foo.py
```

### Conventions

- Co-locate unit tests with source files **or** place them in a top-level
  `tests/` directory — pick one and be consistent.
- Name test files `*.test.ts`, `*_test.go`, `test_*.py`, etc. per language
  convention.
- Prefer testing behaviour over implementation details.
- Do not commit tests that are skipped indefinitely; fix or delete them.

---

## Linting & Formatting

*(Update with actual tools and commands once the stack is set.)*

```bash
# Lint
# npm run lint / ruff check . / golangci-lint run

# Format
# npm run format / ruff format . / gofmt -w .

# Type-check (if applicable)
# npm run typecheck / mypy .
```

Linting and formatting **must pass** before merging. Configure your editor to
format on save.

---

## Environment Variables

- Store secrets in `.env` (never commit this file).
- Maintain a `.env.example` with all required keys and placeholder values.
- Document every variable below once they are known.

| Variable | Required | Description |
|---|---|---|
| *(none defined yet)* | — | — |

---

## Key Conventions for AI Assistants

### General Rules

1. **Read before editing.** Always read the relevant file(s) before making
   changes. Never guess at contents.
2. **Minimal changes.** Only modify what is directly required by the task.
   Do not refactor surrounding code, add comments to unchanged lines, or
   introduce new abstractions unless explicitly asked.
3. **No speculative features.** Do not add error handling, logging, or
   configuration for scenarios that are not yet needed.
4. **Prefer editing over creating.** Modify existing files rather than
   creating new ones unless a new file is clearly required.
5. **Never commit secrets.** Reject any instruction to add credentials, API
   keys, or tokens to tracked files.

### Code Style

- Follow the style already present in the file being edited.
- Match indentation (spaces vs. tabs), quote style, and bracket placement
  exactly.
- Do not introduce new dependencies without confirming with the user.

### Testing Requirements

- Every new function or module should have corresponding tests unless the
  user explicitly waives this.
- Do not mark tests as skipped or pending in a commit unless accompanied by
  a tracking issue.

### Security

- Validate all user-supplied input at system boundaries.
- Never construct shell commands, SQL queries, or HTML from unsanitized input.
- Follow OWASP Top 10 guidance by default.
- If a change has security implications, call them out explicitly.

### Git Operations

- Develop on the branch specified in the task; never push to `main` directly.
- Commit messages must follow the Conventional Commits format above.
- Use `git push -u origin <branch>` when pushing a new branch.
- Do not amend or force-push commits that have already been pushed unless
  explicitly instructed.

---

## CI / CD

*(Add CI pipeline details once configured — e.g., GitHub Actions, GitLab CI.)*

Expected pipeline stages (typical):

1. **Lint** — static analysis and formatting checks
2. **Test** — unit and integration tests with coverage threshold
3. **Build** — compile or bundle the project
4. **Deploy** — (on `main` merge) deploy to staging / production

---

## Architecture Notes

*(Fill in once the project structure is established.)*

Key design decisions to document here:
- Data flow / request lifecycle
- Authentication / authorisation strategy
- External service integrations
- Database schema overview
- Caching strategy

---

## Updating This File

This file should be updated whenever:
- The technology stack changes.
- New tooling or scripts are introduced.
- Architectural decisions are made.
- Conventions are agreed upon or changed.

Keep it accurate — an outdated CLAUDE.md is worse than none.
