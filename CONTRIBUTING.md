# Contribuer à VoiceSurvey AI

Merci de votre contribution. Ce guide explique notre façon de travailler afin de
garder une base de code propre, modulaire et maintenable pendant des années.

> 📌 Il s'agit d'un projet **interne**. Les contributions proviennent uniquement
> des membres de l'équipe et prestataires autorisés.

---

## Principes fondamentaux

Nous appliquons ces principes à chaque changement :

- **Concevoir d'abord.** Ne jamais coder immédiatement — documenter la décision
  avant de l'implémenter.
- **Clean Architecture** — garder la logique métier indépendante des frameworks.
- **SOLID, DRY, KISS** — privilégier un code simple, à responsabilité unique et
  réutilisable.
- **Separation of Concerns** — des frontières claires entre couches et modules.
- **Repository Pattern** et **Dependency Injection** lorsque pertinent.
- **La documentation fait partie du produit** — la mettre à jour à chaque
  changement.

---

## Vue d'ensemble du flux de travail

1. **Ouvrir une issue** décrivant le problème ou la fonctionnalité (templates).
2. **Discuter & documenter** — mettre à jour le document concerné dans `docs/`.
3. **Créer une branche** à partir de la branche par défaut à jour.
4. **Implémenter** le changement en commits courts et ciblés.
5. **Ouvrir une Pull Request** en utilisant le template fourni.
6. **Faire passer la CI** et demander la revue aux `CODEOWNERS` concernés.
7. **Fusionner** une fois la PR approuvée et la CI verte.

Détails complets dans [`docs/22_WORKFLOW_GIT.md`](docs/22_WORKFLOW_GIT.md).

---

## Nommage des branches

Branches courtes, descriptives, en kebab-case, avec un préfixe de type :

```
feat/<description-courte>      # nouvelle fonctionnalité
fix/<description-courte>       # correction de bug
docs/<description-courte>      # documentation uniquement
refactor/<description-courte>  # refactorisation interne
chore/<description-courte>     # outillage, dépendances, maintenance
```

---

## Messages de commit

Nous suivons la convention [Conventional Commits](https://www.conventionalcommits.org/) :

```
<type>(<portée optionnelle>) : <résumé court>

<corps optionnel expliquant quoi et pourquoi>
```

Exemples :

```
feat(campaigns): add outbound campaign scheduler
fix(telephony): handle dropped-call retry logic
docs(architecture): document workflow engine boundaries
```

> Rappel : les **messages de commit et le code restent en anglais** ; la
> documentation et les échanges sont en français.

---

## Conventions de code

- **Backend (Python/FastAPI) :** PEP 8, annotations de types, formateur et
  linter du projet. Voir [`docs/21_CONVENTIONS_DE_CODE.md`](docs/21_CONVENTIONS_DE_CODE.md).
- **Frontend (Next.js/TS) :** TypeScript strict, ESLint + Prettier, conventions
  Tailwind + Shadcn UI.

---

## Pull Requests

- Garder les PR petites et centrées sur un seul sujet.
- Remplir intégralement le template de PR.
- Lier la ou les issues associées.
- S'assurer que la documentation est à jour.
- Toutes les vérifications CI doivent passer avant la revue.

---

## Code de conduite

En participant, vous acceptez de respecter notre
[Code de conduite](CODE_OF_CONDUCT.md).
