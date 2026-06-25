# Docker

Définitions de conteneurs et orchestration pour VoiceSurvey AI.

## Rôle

Centralise tous les **Dockerfiles** et fichiers **Docker Compose** afin que le
développement local et le déploiement utilisent des définitions de services
identiques et reproductibles.

## Contenu (à venir)

Placeholder uniquement pendant l'amorçage.

## Conventions

```
docker/
├── backend.Dockerfile      # Image du service FastAPI
├── frontend.Dockerfile     # Image du service Next.js
├── docker-compose.yml      # Stack de base : backend, frontend, postgres, redis, nginx
├── docker-compose.dev.yml  # Surcharges de développement (hot reload, montages)
└── docker-compose.prod.yml # Surcharges de production
```

Stack de services prévue : **frontend** (Next.js), **backend** (FastAPI),
**db** (PostgreSQL), **cache** (Redis), **proxy** (Nginx).

Voir [`../docs/18_DÉPLOIEMENT.md`](../docs/18_DÉPLOIEMENT.md).
