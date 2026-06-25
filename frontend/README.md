# Frontend

The **Next.js (React + TypeScript)** web application for VoiceSurvey AI.

## Purpose

Provides the internal UI for building questionnaires, importing contacts,
launching and monitoring campaigns, reviewing conversations, and exploring
summaries, reports, and analytics.

## Design intent

Styled with **Tailwind CSS** and **Shadcn UI**, using strict TypeScript and a
modular, feature-oriented structure. Intended layout (to be implemented later):

```
frontend/
├── src/
│   ├── app/            # Next.js App Router routes & layouts
│   ├── components/     # Reusable UI (Shadcn-based) components
│   ├── features/       # Feature modules (campaigns, contacts, surveys, …)
│   ├── lib/            # API clients, utilities, hooks
│   ├── styles/         # Tailwind config & global styles
│   └── types/          # Shared TypeScript types
├── public/             # Static assets served as-is
└── package.json        # Dependencies & scripts
```

> ⚠️ No application code exists yet — intentional during bootstrap.
> See [`../docs/12_FRONTEND_ARCHITECTURE.md`](../docs/12_FRONTEND_ARCHITECTURE.md).
