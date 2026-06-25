# Infrastructure

Environment, reverse-proxy, and deployment configuration for VoiceSurvey AI.

## Purpose

Holds infrastructure-as-configuration that is **not** Docker image definitions
(those live in [`../docker/`](../docker)). This includes:

- **Nginx** reverse-proxy configuration (TLS termination, routing to frontend
  and backend, WebSocket upgrades for live call audio/events).
- **Environment templates** (`.env.example` files) per service.
- **Deployment** manifests / runbooks for staging and production.

## Intended layout

```
infrastructure/
├── nginx/              # Nginx site & proxy configuration
├── env/                # Environment variable templates (.env.example)
└── deploy/             # Deployment configuration & runbooks
```

> ⚠️ Placeholder only during bootstrap.
> See [`../docs/18_DEPLOYMENT.md`](../docs/18_DEPLOYMENT.md).
