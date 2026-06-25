# Scripts

Developer and operations automation for VoiceSurvey AI.

## Purpose

Holds small, well-documented helper scripts that automate repetitive tasks so
they are consistent and reproducible across the team.

## Examples of what will live here

- Environment bootstrap / first-time setup
- Database migration and seeding helpers
- Local stack start/stop wrappers
- Linting, formatting, and test convenience runners
- Data import/export utilities

## Conventions

- Prefer POSIX `sh`/`bash`; keep scripts idempotent where possible.
- Every script begins with a short header comment explaining what it does and
  how to run it.
- Scripts must never contain secrets — read them from the environment.

> ⚠️ Placeholder only during bootstrap.
