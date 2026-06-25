# Docker

Container definitions and orchestration for VoiceSurvey AI.

## Purpose

Centralizes all **Dockerfiles** and **Docker Compose** files so local
development and deployment use the same, reproducible service definitions.

## Intended layout

```
docker/
├── backend.Dockerfile      # FastAPI service image
├── frontend.Dockerfile     # Next.js service image
├── docker-compose.yml      # Base stack: backend, frontend, postgres, redis, nginx
├── docker-compose.dev.yml  # Development overrides (hot reload, mounts)
└── docker-compose.prod.yml # Production overrides
```

## Service stack (planned)

- **frontend** — Next.js
- **backend** — FastAPI
- **db** — PostgreSQL
- **cache** — Redis
- **proxy** — Nginx

> ⚠️ Placeholder only during bootstrap.
> See [`../docs/18_DEPLOYMENT.md`](../docs/18_DEPLOYMENT.md).
