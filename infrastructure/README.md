# Infrastructure

Configuration des environnements, du reverse-proxy et du déploiement.

## Rôle

Regroupe la configuration d'infrastructure qui n'est **pas** la définition des
images Docker (celles-ci vivent dans [`../docker/`](../docker)) :

- Configuration **Nginx** (terminaison TLS, routage frontend/backend, montée en
  WebSocket pour l'audio et les événements d'appels en temps réel).
- **Modèles d'environnement** (`.env.example`) par service.
- **Déploiement** : manifestes et runbooks pour staging et production.

## Contenu (à venir)

Placeholder uniquement pendant l'amorçage.

## Conventions

```
infrastructure/
├── nginx/              # Configuration des sites & du proxy Nginx
├── env/                # Modèles de variables d'environnement (.env.example)
└── deploy/            # Configuration de déploiement & runbooks
```

Voir [`../docs/18_DÉPLOIEMENT.md`](../docs/18_DÉPLOIEMENT.md).
