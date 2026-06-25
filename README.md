# VoiceSurvey AI

> Internal enterprise application for AI-powered automated phone conversations.

VoiceSurvey AI lets our team design questionnaires, import contact lists, run
outbound calling campaigns, answer inbound calls, let an AI agent conduct
natural conversations, collect answers, and automatically generate summaries,
reports, and analytics.

The first business use case is **Market Research**.

---

## What this is (and is not)

- ✅ An **internal business application** used by a single company.
- ❌ Not a SaaS platform.
- ❌ No billing, no subscriptions, no multi-tenant architecture.

The architecture is intentionally **modular** so the product can keep evolving
for years without accumulating structural debt.

---

## Repository layout

| Path              | Purpose                                                            |
| ----------------- | ----------------------------------------------------------------- |
| `docs/`           | All project documentation (the source of truth for the product).  |
| `backend/`        | FastAPI (Python) application — APIs, domain logic, services.       |
| `frontend/`       | Next.js (React + TypeScript) web application.                      |
| `infrastructure/` | Nginx, environment, and deployment configuration.                 |
| `docker/`         | Dockerfiles and Docker Compose definitions.                       |
| `scripts/`        | Developer and operations automation scripts.                      |
| `assets/`         | Brand assets, logos, and shared static media.                     |
| `templates/`      | Reusable content templates (questionnaires, emails, reports).     |
| `prompts/`        | AI prompt library powering the conversation engine.               |
| `.github/`        | GitHub automation: templates, workflows, CODEOWNERS.              |

Each top-level folder contains a `README.md` describing its purpose in detail.

---

## Documentation-driven development

This repository is **driven by Markdown documentation**. Every important
decision is documented *before* it is implemented. Start with
[`docs/README.md`](docs/README.md) and the numbered documents in `docs/`.

---

## Technology

**Frontend:** Next.js · React · TypeScript · Tailwind CSS · Shadcn UI
**Backend:** Python · FastAPI
**Database:** PostgreSQL · **Cache:** Redis
**Infrastructure:** Docker · Docker Compose · Nginx

---

## Project status

🟡 **Bootstrap phase.** The repository structure and documentation skeleton are
being established. No application code has been written yet — by design.

See [`CHANGELOG.md`](CHANGELOG.md) for history and
[`CONTRIBUTING.md`](CONTRIBUTING.md) to get started.

---

## License

Proprietary and confidential. See [`LICENSE.md`](LICENSE.md).
