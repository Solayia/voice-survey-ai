# 00. Index de la documentation

Point d'entrée de toute la documentation de **VoiceSurvey AI**. Le projet est
piloté par la documentation : chaque décision importante est consignée ici avant
toute implémentation.

> 🟡 **Phase d'amorçage.** Les documents ci-dessous sont des **placeholders**.
> Leur structure existe, mais leur contenu n'est pas encore rédigé.

## 1. Cadrage produit

| #  | Document | Objet |
| -- | -------- | ----- |
| 01 | [Présentation du projet](01_PRÉSENTATION_DU_PROJET.md) | Résumé de haut niveau : quoi, pour qui, pourquoi. |
| 02 | [Vision produit](02_VISION_PRODUIT.md) | Vision à long terme et principes directeurs. |
| 03 | [Objectifs](03_OBJECTIFS.md) | Objectifs de l'application et critères de succès. |
| 04 | [Besoins métier](04_BESOINS_MÉTIER.md) | Besoins, contraintes et exigences métier. |
| 05 | [Personas](05_PERSONAS.md) | Profils des utilisateurs internes. |
| 06 | [Parcours utilisateurs](06_PARCOURS_UTILISATEURS.md) | Parcours et flux des utilisateurs. |
| 07 | [Fonctionnalités](07_FONCTIONNALITÉS.md) | Catalogue des fonctionnalités et leur périmètre. |
| 08 | [Cas d'usages](08_CAS_D_USAGES.md) | Cas d'usage actuels et futurs du moteur. |

## 2. Architecture & technique

| #  | Document | Objet |
| -- | -------- | ----- |
| 09 | [Architecture globale](09_ARCHITECTURE_GLOBALE.md) | Architecture système, composants et frontières. |
| 10 | [Modèle de données](10_MODÈLE_DE_DONNÉES.md) | Modèle de données et décisions de stockage. |
| 11 | [Architecture backend](11_ARCHITECTURE_BACKEND.md) | Structure interne du backend FastAPI. |
| 12 | [Architecture frontend](12_ARCHITECTURE_FRONTEND.md) | Structure interne du frontend Next.js. |
| 13 | [Moteur IA](13_MOTEUR_IA.md) | Moteur de conversation, synthèse et analyse IA. |
| 14 | [Téléphonie](14_TÉLÉPHONIE.md) | Gestion des appels entrants/sortants. |
| 15 | [Workflows](15_WORKFLOWS.md) | Orchestration des campagnes, appels et tâches. |
| 16 | [Authentification](16_AUTHENTIFICATION.md) | Identité, sessions et contrôle d'accès. |
| 17 | [Sécurité](17_SÉCURITÉ.md) | Architecture de sécurité, menaces et contrôles. |
| 18 | [Déploiement](18_DÉPLOIEMENT.md) | Docker, Nginx, environnements et livraison. |
| 19 | [Tests](19_TESTS.md) | Stratégie de tests sur toute la stack. |

## 3. Design & conventions

| #  | Document | Objet |
| -- | -------- | ----- |
| 20 | [Design System](20_DESIGN_SYSTEM.md) | Langage visuel et composants (Tailwind/Shadcn). |
| 21 | [Conventions de code](21_CONVENTIONS_DE_CODE.md) | Conventions backend et frontend. |
| 22 | [Workflow Git](22_WORKFLOW_GIT.md) | Branches, commits, revues et releases. |

## 4. Pilotage

| #  | Document | Objet |
| -- | -------- | ----- |
| 23 | [Plan de développement](23_PLAN_DE_DÉVELOPPEMENT.md) | Plan d'exécution étape par étape. |
| 24 | [Roadmap](24_ROADMAP.md) | Feuille de route et jalons. |
| 25 | [Structure du projet](25_STRUCTURE_DU_PROJET.md) | Explication de l'arborescence du dépôt. |

## Décisions d'architecture (ADR)

Les décisions techniques significatives sont consignées sous forme d'ADR dans
[`adr/`](adr/). Voir le [modèle d'ADR](adr/0000-modele.md).
