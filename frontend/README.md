# Frontend

L'application web **Next.js (React + TypeScript)** de VoiceSurvey AI.

## Rôle

Fournit l'interface interne pour construire les questionnaires, importer les
contacts, lancer et superviser les campagnes, relire les conversations et
explorer statistiques, rapports et exports.

## Contenu (à venir)

Aucun code applicatif n'existe encore — c'est volontaire pendant l'amorçage.

## Conventions

Stylé avec **Tailwind CSS** et **Shadcn UI**, en TypeScript strict, avec une
structure modulaire orientée fonctionnalités. Découpage prévu :

```
frontend/
├── src/
│   ├── app/            # Routes & layouts (App Router de Next.js)
│   ├── components/     # Composants UI réutilisables (basés sur Shadcn)
│   ├── features/       # Modules fonctionnels (campaigns, contacts, surveys…)
│   ├── lib/            # Clients API, utilitaires, hooks
│   ├── styles/         # Configuration Tailwind & styles globaux
│   └── types/          # Types TypeScript partagés
├── public/             # Ressources statiques servies telles quelles
└── package.json        # Dépendances & scripts
```

- Code en **anglais**, ESLint + Prettier, TypeScript strict.
- Voir [`../docs/12_ARCHITECTURE_FRONTEND.md`](../docs/12_ARCHITECTURE_FRONTEND.md).
