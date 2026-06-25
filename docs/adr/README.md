# Architecture Decision Records (ADRs)

This folder captures **significant technical decisions** and the context behind
them, so future maintainers understand *why* the system is the way it is.

## What is an ADR?

A short Markdown document recording a single architectural decision: the
context, the decision, the alternatives considered, and the consequences.

## Conventions

- One decision per file.
- Filename: `NNNN-short-title.md` (e.g. `0001-use-clean-architecture.md`),
  using a zero-padded incrementing number.
- Start from [`0000-template.md`](0000-template.md).
- ADRs are **immutable** once accepted. To change a decision, add a new ADR that
  supersedes the old one and update the old one's status.

## Index

| #    | Title    | Status |
| ---- | -------- | ------ |
| 0000 | [Template](0000-template.md) | — |

> 🟡 No decisions recorded yet. The first ADRs will be added as architecture
> documents (`docs/09`–`docs/15`) are written.
