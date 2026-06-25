# VoiceSurvey AI

> Application interne d'entreprise pour automatiser les conversations
> téléphoniques grâce à des agents vocaux propulsés par l'intelligence
> artificielle.

VoiceSurvey AI permet à nos équipes de concevoir des questionnaires, d'importer
des contacts, de lancer des campagnes d'appels, de gérer les appels entrants et
sortants, de laisser une IA mener des conversations naturelles, d'enregistrer
les réponses, puis de produire automatiquement des statistiques, des rapports
et des exports.

Le premier besoin métier est la réalisation d'**études de marché**. Le moteur
est toutefois conçu pour être **générique et réutilisable**, afin de couvrir
plus tard : enquêtes de satisfaction, qualification de prospects, prise de
rendez-vous, support client, recrutement et standard téléphonique.

---

## Ce que c'est (et ce que ce n'est pas)

- ✅ Une **application métier interne**, utilisée par une seule entreprise.
- ❌ Ce n'est pas une plateforme SaaS.
- ❌ Pas de facturation, pas d'abonnement, pas d'architecture multi-tenant.

L'architecture est volontairement **modulaire** pour que le produit puisse
évoluer pendant des années sans accumuler de dette technique.

---

## Structure du dépôt

| Dossier           | Rôle                                                              |
| ----------------- | ---------------------------------------------------------------- |
| `docs/`           | Toute la documentation du projet (la source de vérité).          |
| `backend/`        | Application FastAPI (Python) — API, logique métier, services.    |
| `frontend/`       | Application web Next.js (React + TypeScript).                    |
| `infrastructure/` | Configuration Nginx, environnements et déploiement.             |
| `docker/`         | Dockerfiles et fichiers Docker Compose.                          |
| `scripts/`        | Scripts d'automatisation pour le développement et l'exploitation.|
| `assets/`         | Ressources statiques et éléments de marque.                      |
| `templates/`      | Modèles de contenu réutilisables (questionnaires, rapports…).    |
| `prompts/`        | Bibliothèque de prompts IA du moteur conversationnel.            |
| `.github/`        | Automatisation GitHub : templates, workflows, CODEOWNERS.        |

Chaque dossier de premier niveau contient un `README.md` détaillant son rôle.

---

## Développement piloté par la documentation

Ce dépôt est **piloté par la documentation Markdown**. Chaque décision
importante est documentée *avant* d'être implémentée. Commencez par
[`docs/00_INDEX.md`](docs/00_INDEX.md).

> 📌 **Règle permanente :** aucune fonctionnalité n'est développée tant que sa
> documentation n'a pas été rédigée, relue et validée.

---

## Stack technique

**Frontend :** Next.js · React · TypeScript · Tailwind CSS · Shadcn UI
**Backend :** Python · FastAPI
**Base de données :** PostgreSQL · **Cache :** Redis
**Infrastructure :** Docker · Docker Compose · Nginx

### Principes d'architecture

Clean Architecture · SOLID · DRY · KISS · Separation of Concerns ·
Repository Pattern · Dependency Injection (lorsque pertinent).

---

## Langue

- Toute la **documentation** et les explications sont rédigées en **français**.
- Le **code** (noms de classes, fonctions, variables, méthodes, fichiers et
  dossiers techniques) reste en **anglais**.

---

## État du projet

🟡 **Phase d'amorçage (bootstrap).** La structure du dépôt et le squelette de
documentation sont en cours d'établissement. Aucune ligne de code applicatif
n'a encore été écrite — c'est volontaire.

Voir [`CHANGELOG.md`](CHANGELOG.md) pour l'historique et
[`CONTRIBUTING.md`](CONTRIBUTING.md) pour démarrer.

---

## Licence

Logiciel propriétaire et confidentiel. Voir [`LICENSE.md`](LICENSE.md).
