# Backend

L'application **FastAPI (Python)** qui propulse VoiceSurvey AI.

## Rôle

Héberge les API HTTP/WebSocket, la logique métier et les services d'arrière-plan :
questionnaires, contacts, campagnes, appels, intégration du moteur IA, réponses
et rapports.

## Contenu (à venir)

Aucun code applicatif n'existe encore — c'est volontaire pendant l'amorçage.

## Conventions

Ce paquet suivra la **Clean Architecture**. Le découpage interne prévu est :

```
backend/
├── app/
│   ├── api/            # Routers HTTP & WebSocket (couche de présentation)
│   ├── core/           # Configuration, logging, primitives de sécurité
│   ├── domain/         # Entités & règles métier (indépendantes du framework)
│   ├── services/       # Cas d'usage / services applicatifs
│   ├── repositories/   # Abstractions d'accès aux données (Repository Pattern)
│   ├── infrastructure/ # Adaptateurs DB, Redis, téléphonie, fournisseurs IA
│   ├── schemas/        # Modèles Pydantic de requêtes/réponses
│   └── workers/        # Tâches d'arrière-plan & runtime du moteur de workflows
├── tests/              # Tests unitaires & d'intégration
└── pyproject.toml      # Dépendances & configuration de l'outillage
```

- Code en **anglais**, PEP 8, annotations de types obligatoires.
- Voir [`../docs/11_ARCHITECTURE_BACKEND.md`](../docs/11_ARCHITECTURE_BACKEND.md).
