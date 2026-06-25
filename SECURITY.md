# Politique de sécurité

VoiceSurvey AI manipule des données sensibles — listes de contacts,
enregistrements et transcriptions d'appels, réponses aux enquêtes. La sécurité
est une préoccupation de premier ordre.

## Signaler une vulnérabilité

Si vous découvrez une vulnérabilité de sécurité :

1. **N'ouvrez pas** d'issue publique.
2. Signalez-la **en privé** au propriétaire du projet / responsable sécurité.
3. Incluez : une description, les étapes de reproduction, les composants
   affectés et l'impact.
4. Laissez un délai raisonnable pour la correction avant toute divulgation.

Les signalements sont accusés réception et traités en priorité.

## Périmètre

Cette politique couvre le code applicatif, la configuration d'infrastructure et
les pipelines de traitement des données de ce dépôt.

## Principes de protection des données

- **Moindre privilège** pour tous les identifiants et comptes de service.
- **Aucun secret dans le dépôt** — utiliser des variables d'environnement et un
  gestionnaire de secrets.
- **Chiffrement** en transit (TLS) et au repos pour les données sensibles.
- **Traitement des données personnelles** (contacts, appels) conforme à la
  réglementation applicable et à la politique de l'entreprise.
- **Traçabilité** — les actions sensibles doivent être journalisées.

Les contrôles détaillés sont documentés dans
[`docs/17_SÉCURITÉ.md`](docs/17_SÉCURITÉ.md) et
[`docs/16_AUTHENTIFICATION.md`](docs/16_AUTHENTIFICATION.md).

## Versions prises en charge

En tant qu'application interne en développement actif, seule la ligne `main`
courante est prise en charge. Les correctifs de sécurité s'appliquent à la
version la plus récente.
