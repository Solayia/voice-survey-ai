# Backend

The **FastAPI (Python)** application powering VoiceSurvey AI.

## Purpose

Hosts the HTTP/WebSocket APIs, domain logic, and background services for
questionnaires, contacts, campaigns, calls, the AI conversation engine
integration, results, and reporting.

## Design intent

This package follows **Clean Architecture**. The intended internal layering
(to be implemented later) is:

```
backend/
├── app/
│   ├── api/            # HTTP & WebSocket routers (delivery layer)
│   ├── core/           # Config, settings, logging, security primitives
│   ├── domain/         # Entities & business rules (framework-agnostic)
│   ├── services/       # Use cases / application services
│   ├── repositories/   # Data-access abstractions
│   ├── infrastructure/ # DB, Redis, telephony & AI provider adapters
│   ├── schemas/        # Pydantic request/response models
│   └── workers/        # Background jobs & the workflow engine runtime
├── tests/              # Unit & integration tests
└── pyproject.toml      # Dependencies & tooling config
```

> ⚠️ No application code exists yet — this is intentional during the bootstrap
> phase. See [`../docs/11_BACKEND_ARCHITECTURE.md`](../docs/11_BACKEND_ARCHITECTURE.md).
