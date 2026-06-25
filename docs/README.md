# Documentation

This folder is the **source of truth** for VoiceSurvey AI. The project is
documentation-driven: every important decision is documented *before* it is
implemented.

> 🟡 **Bootstrap phase.** The documents below are **placeholders**. Their
> structure exists, but the content is intentionally not written yet.

## Index

| #  | Document | Purpose |
| -- | -------- | ------- |
| 01 | [PROJECT_OVERVIEW](01_PROJECT_OVERVIEW.md) | High-level summary of what the project is and why it exists. |
| 02 | [PRODUCT_VISION](02_PRODUCT_VISION.md) | Long-term vision, goals, and guiding principles. |
| 03 | [BUSINESS_REQUIREMENTS](03_BUSINESS_REQUIREMENTS.md) | Business needs, constraints, and success criteria. |
| 04 | [USER_PERSONAS](04_USER_PERSONAS.md) | Profiles of the internal users of the application. |
| 05 | [USER_STORIES](05_USER_STORIES.md) | User stories capturing required behavior. |
| 06 | [FEATURES](06_FEATURES.md) | Catalog of product features and their scope. |
| 07 | [ROADMAP](07_ROADMAP.md) | Phased plan of delivery over time. |
| 08 | [TECH_STACK](08_TECH_STACK.md) | Chosen technologies and the rationale behind them. |
| 09 | [ARCHITECTURE](09_ARCHITECTURE.md) | System-level architecture and component boundaries. |
| 10 | [DATABASE_DESIGN](10_DATABASE_DESIGN.md) | Data model, schema, and storage decisions. |
| 11 | [BACKEND_ARCHITECTURE](11_BACKEND_ARCHITECTURE.md) | Internal structure of the FastAPI backend. |
| 12 | [FRONTEND_ARCHITECTURE](12_FRONTEND_ARCHITECTURE.md) | Internal structure of the Next.js frontend. |
| 13 | [AI_ENGINE](13_AI_ENGINE.md) | The AI conversation, summarization, and analysis engine. |
| 14 | [TELEPHONY](14_TELEPHONY.md) | Inbound/outbound call handling and provider integration. |
| 15 | [WORKFLOW_ENGINE](15_WORKFLOW_ENGINE.md) | Orchestration of campaigns, calls, and tasks. |
| 16 | [AUTHENTICATION](16_AUTHENTICATION.md) | Identity, sessions, and access control. |
| 17 | [SECURITY](17_SECURITY.md) | Security architecture, threats, and controls. |
| 18 | [DEPLOYMENT](18_DEPLOYMENT.md) | Docker, Nginx, environments, and release process. |
| 19 | [TESTING](19_TESTING.md) | Testing strategy across the stack. |
| 20 | [UI_UX](20_UI_UX.md) | UX principles, flows, and interaction patterns. |
| 21 | [DESIGN_SYSTEM](21_DESIGN_SYSTEM.md) | Visual language, components, and Tailwind/Shadcn usage. |
| 22 | [CODING_STANDARDS](22_CODING_STANDARDS.md) | Coding conventions for backend and frontend. |
| 23 | [GIT_WORKFLOW](23_GIT_WORKFLOW.md) | Branching, commits, reviews, and releases. |
| 24 | [API_STRATEGY](24_API_STRATEGY.md) | API design conventions and versioning strategy. |
| 25 | [PROJECT_STRUCTURE](25_PROJECT_STRUCTURE.md) | Explanation of the repository layout. |

## Architecture Decision Records

Significant technical decisions are recorded as ADRs in [`adr/`](adr/).
See the [ADR template](adr/0000-template.md).
