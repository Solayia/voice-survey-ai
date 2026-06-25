# Contributing to VoiceSurvey AI

Thank you for contributing. This guide explains how we work so the codebase
stays clean, modular, and maintainable for years.

> 📌 This is an **internal** project. Contributions come from authorized team
> members and contractors only.

---

## Core principles

We follow these principles in every change:

- **Design first.** Never start coding immediately — document the decision first.
- **Clean Architecture** — keep domain logic independent of frameworks.
- **SOLID, DRY, KISS** — favor simple, single-responsibility, reusable code.
- **Separation of Concerns** — clear boundaries between layers and modules.
- **Documentation is part of the product** — update docs with every change.

---

## Workflow at a glance

1. **Open an issue** describing the problem or feature (use the templates).
2. **Discuss & document** — update or add the relevant doc in `docs/` first.
3. **Create a branch** from the latest default branch.
4. **Implement** the change in small, focused commits.
5. **Open a Pull Request** using the PR template.
6. **Pass CI** and request review from the appropriate `CODEOWNERS`.
7. **Merge** once approved and green.

See [`docs/23_GIT_WORKFLOW.md`](docs/23_GIT_WORKFLOW.md) for full details.

---

## Branch naming

Use short, descriptive, kebab-case branches with a type prefix:

```
feat/<short-description>      # new feature
fix/<short-description>       # bug fix
docs/<short-description>      # documentation only
refactor/<short-description>  # internal refactor
chore/<short-description>     # tooling, deps, housekeeping
```

---

## Commit messages

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<optional scope>): <short summary>

<optional body explaining what and why>
```

Examples:

```
feat(campaigns): add outbound campaign scheduler
fix(telephony): handle dropped-call retry logic
docs(architecture): document workflow engine boundaries
```

---

## Coding standards

- **Backend (Python/FastAPI):** PEP 8, type hints, formatted with the project
  formatter and linter. See [`docs/22_CODING_STANDARDS.md`](docs/22_CODING_STANDARDS.md).
- **Frontend (Next.js/TS):** strict TypeScript, ESLint + Prettier, Tailwind +
  Shadcn UI conventions.

Details live in [`docs/22_CODING_STANDARDS.md`](docs/22_CODING_STANDARDS.md).

---

## Pull Requests

- Keep PRs small and focused on a single concern.
- Fill out the PR template completely.
- Link the related issue(s).
- Ensure documentation is updated.
- All CI checks must pass before review.

---

## Code of Conduct

By participating you agree to uphold our
[Code of Conduct](CODE_OF_CONDUCT.md).
