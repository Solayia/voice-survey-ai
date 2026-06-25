# 04. Besoins métier — Premier client

> 🟢 **Document rédigé.** Analyse métier de la **première version** de
> VoiceSurvey AI, centrée exclusivement sur le besoin réel du premier client.
>
> Ce document décrit **le métier**, pas la solution technique. Il ne contient
> aucune proposition d'architecture, de base de données, d'API ni d'interface.
> Il doit permettre à un développeur qui ne connaît pas le métier de comprendre
> précisément ce que le client attend.

---

## Sommaire

1. [Cadre et objectif](#1-cadre-et-objectif)
2. [Contexte client](#2-contexte-client)
3. [Fonctionnement actuel (manuel)](#3-fonctionnement-actuel-manuel)
4. [Difficultés, pertes de temps et risques](#4-difficultés-pertes-de-temps-et-risques)
5. [Fonctionnement souhaité (cible)](#5-fonctionnement-souhaité-cible)
6. [Fonctionnalités indispensables](#6-fonctionnalités-indispensables)
7. [Rôles utilisateurs](#7-rôles-utilisateurs)
8. [Parcours utilisateur complet](#8-parcours-utilisateur-complet)
9. [Contraintes métier](#9-contraintes-métier)
10. [Critères de réussite](#10-critères-de-réussite)
11. [Hors périmètre (V1)](#11-hors-périmètre-v1)
12. [Glossaire](#12-glossaire)

---

## 1. Cadre et objectif

Nous mettons volontairement de côté toutes les fonctionnalités futures du
moteur (satisfaction, qualification de prospects, prise de rendez-vous, support,
recrutement, standard). **L'objectif de cette première version n'est pas de
construire un logiciel complet, mais de répondre parfaitement au besoin réel du
premier client.**

Ce besoin est unique et précis : **automatiser la réalisation d'études de marché
par téléphone**, aujourd'hui effectuées manuellement par des enquêteurs humains,
grâce à une intelligence artificielle capable de mener une conversation
naturelle tout en respectant scrupuleusement un questionnaire et des règles
définies.

L'IA doit **remplacer l'enquêteur humain** sur la conduite de l'appel, sans
trahir le sens des questions ni la rigueur méthodologique attendue d'une étude.

---

## 2. Contexte client

Le client est une structure qui réalise des **études de marché par téléphone**
pour le compte de ses propres clients (les commanditaires des études).

- Son métier est de **collecter des réponses fiables** auprès d'un échantillon
  de personnes (le « panel »), à partir d'un **questionnaire** défini.
- Aujourd'hui, ces appels sont passés **un par un, manuellement**, par des
  enquêteurs qui lisent le questionnaire, posent les questions, notent les
  réponses, puis transmettent les résultats.
- Le volume d'appels est élevé et répétitif, la valeur ajoutée humaine réelle
  est faible pendant l'appel (lecture + saisie), mais le coût et le temps sont
  importants.

Le besoin du client est donc d'**augmenter le volume traité, de réduire le coût
et le délai, et d'homogénéiser la qualité**, sans dégrader la fiabilité des
données collectées.

---

## 3. Fonctionnement actuel (manuel)

Cette section décrit, étape par étape, comment une étude se déroule aujourd'hui.

### 3.1 Préparation d'une étude

1. Le commanditaire exprime un besoin (sujet de l'étude, cible, nombre de
   réponses attendues, délai).
2. Un **questionnaire** est rédigé : liste de questions ordonnées, avec parfois
   des **règles de branchement** (« si la personne répond non à la question 3,
   passer directement à la question 7 »).
3. Les questions sont de différents types : choix unique, choix multiple, échelle
   de notation, oui/non, question ouverte (réponse libre).
4. Le questionnaire est relu et validé avant le lancement.
5. Un **objectif de réponses** est fixé (ex. « 300 questionnaires complétés »).

### 3.2 Obtention des contacts

1. Une **liste de contacts** est constituée (numéros de téléphone, et souvent
   nom, prénom, et quelques attributs : ville, tranche d'âge, segment…).
2. Cette liste provient d'un fichier fourni par le commanditaire, d'un panel
   existant, ou d'une base achetée/louée.
3. La liste est souvent un **fichier tableur (CSV ou Excel)**, plus ou moins
   propre (doublons, numéros invalides, colonnes hétérogènes).

### 3.3 Réalisation des appels

1. Chaque enquêteur reçoit une portion de la liste.
2. Il appelle les contacts **un par un**.
3. À chaque appel, plusieurs issues sont possibles :
   - personne **ne répond pas** ;
   - **numéro invalide** / injoignable ;
   - la personne **refuse** de participer ;
   - la personne **accepte** mais n'a pas le temps (à rappeler) ;
   - la personne **accepte et répond** au questionnaire.
4. Pendant l'appel, l'enquêteur **lit les questions**, **adapte parfois la
   formulation** pour rester naturel, **relance** si la réponse est floue, et
   **respecte les branchements**.

### 3.4 Notation des réponses

1. L'enquêteur **saisit les réponses** au fur et à mesure (sur papier, tableur
   ou outil interne).
2. Les réponses ouvertes sont **résumées ou retranscrites** à la main.
3. Le statut de chaque contact est noté (répondu, refus, sans réponse, à
   rappeler, injoignable).

### 3.5 Exploitation des résultats

1. Les réponses de tous les enquêteurs sont **regroupées**.
2. On calcule des **statistiques** (répartition des réponses, pourcentages).
3. Les réponses ouvertes sont **lues et synthétisées**.
4. Un **rapport** est produit pour le commanditaire, accompagné d'un **export**
   des données brutes.

---

## 4. Difficultés, pertes de temps et risques

### 4.1 Difficultés rencontrées

- **Disponibilité des enquêteurs** : capacité limitée par le nombre de personnes
  et leurs horaires.
- **Hétérogénéité de la qualité** : deux enquêteurs ne mènent pas l'appel de la
  même façon ; le ton, les relances et les reformulations varient.
- **Fatigue et lassitude** : la répétition entraîne erreurs de saisie et baisse
  de qualité en fin de journée.
- **Listes de contacts imparfaites** : doublons, numéros faux, données
  incomplètes à nettoyer manuellement.

### 4.2 Pertes de temps

- **Appels improductifs** : une grande partie des appels n'aboutit pas (sans
  réponse, refus, injoignable), mais consomme du temps.
- **Saisie manuelle** des réponses, en double du temps de l'appel.
- **Synthèse manuelle** des réponses ouvertes.
- **Consolidation manuelle** des résultats de plusieurs enquêteurs.
- **Rappels** non systématisés et difficiles à suivre.

### 4.3 Risques

- **Erreurs de saisie** et fautes de respect des branchements (question posée à
  tort, ou oubliée).
- **Biais d'enquêteur** : la formulation ou le ton influencent la réponse.
- **Incohérence des données** entre enquêteurs.
- **Perte de données** (notes papier, fichiers épars).
- **Confidentialité** : manipulation de données personnelles (numéros, noms,
  réponses) sans cadre homogène.
- **Non-atteinte de l'objectif** de réponses dans le délai imparti.

---

## 5. Fonctionnement souhaité (cible)

Le futur processus reprend les mêmes étapes métier, mais l'appel et la saisie
sont **automatisés par l'IA**. Voici le déroulé cible, étape par étape.

### Étape 1 — Création d'un questionnaire

L'utilisateur crée un questionnaire :

- titre et objectif de l'étude ;
- liste **ordonnée** de questions ;
- pour chaque question : son **type** (choix unique, choix multiple, échelle,
  oui/non, ouverte), son **libellé**, et ses **réponses possibles** le cas
  échéant ;
- indication de si la question est **obligatoire** ou facultative ;
- éventuellement une **consigne** pour l'IA (comment relancer, comment
  reformuler sans changer le sens).

### Étape 2 — Import d'une liste de contacts

L'utilisateur importe un **fichier CSV** de contacts :

- au minimum le **numéro de téléphone** ;
- idéalement des attributs (nom, prénom, ville, segment…) ;
- le système doit accepter des fichiers réels, donc imparfaits.

### Étape 3 — Vérification des données

Avant le lancement, le système aide à **fiabiliser la liste** :

- détection des **doublons** ;
- détection des **numéros manifestement invalides** ;
- signalement des **lignes incomplètes** ;
- aperçu clair du nombre de contacts exploitables.

> Objectif métier : éviter de lancer une campagne sur une liste « sale ».

### Étape 4 — Lancement d'une campagne

L'utilisateur crée une **campagne** qui associe :

- **un questionnaire** ;
- **une liste de contacts** ;
- des **paramètres** : plage horaire d'appel autorisée, nombre de tentatives par
  contact en cas de non-réponse, objectif de réponses, durée maximale d'appel.

Puis il **lance** la campagne.

### Étape 5 — L'IA appelle automatiquement les contacts

Le système **passe les appels automatiquement**, contact après contact, en
respectant les plages horaires et les règles de tentatives. Il gère seul les
issues : sans réponse, refus, injoignable, à rappeler, répondu.

### Étape 6 — L'IA mène la conversation

Pendant l'appel, l'IA :

- se présente et explique l'objet de l'appel ;
- **demande le consentement** à participer ;
- pose les questions **dans l'ordre**, en respectant les **branchements** ;
- s'exprime de façon **naturelle**, peut **reformuler sans changer le sens** et
  **relancer** poliment si la réponse est imprécise ;
- respecte la **durée maximale** et sait **clore proprement** (refus, abandon,
  fin du questionnaire).

### Étape 7 — Les réponses sont enregistrées

Pour chaque appel, le système enregistre :

- la **réponse à chaque question** (structurée selon le type de question) ;
- la **transcription** de l'échange ;
- le **statut final** du contact (répondu / refus / sans réponse / injoignable /
  à rappeler / incomplet).

### Étape 8 — Un résumé est généré

Pour chaque questionnaire complété, l'IA produit un **résumé** lisible de
l'échange, mettant en valeur les points clés et les réponses ouvertes.

### Étape 9 — Les résultats sont consultés dans un tableau de bord

L'utilisateur suit l'étude : avancement de la campagne, nombre de réponses
obtenues, répartition des réponses par question, statuts des contacts,
indicateurs de réussite.

### Étape 10 — Export des données

L'utilisateur exporte les résultats (réponses brutes et/ou agrégées) aux formats
**Excel et CSV**, pour les transmettre au commanditaire ou les analyser ailleurs.

---

## 6. Fonctionnalités indispensables

Liste **restreinte au strict nécessaire** pour le premier client. Toute
fonctionnalité ne répondant pas directement à ce besoin est exclue (voir §11).

| # | Fonctionnalité | Pourquoi elle est indispensable |
|---|----------------|---------------------------------|
| 1 | **Gestion des contacts** | Constituer et consulter la base d'appel d'une étude. |
| 2 | **Import CSV** | Charger les listes réelles fournies au client. |
| 3 | **Vérification / nettoyage des contacts** | Doublons, numéros invalides, lignes incomplètes avant lancement. |
| 4 | **Création de questionnaires** | Définir les questions, leurs types et leurs réponses possibles. |
| 5 | **Logique conditionnelle (branchements)** | Respecter les « si… alors passer à… » indispensables aux études. |
| 6 | **Lancement de campagnes** | Associer questionnaire + liste + paramètres et démarrer les appels. |
| 7 | **Appels automatiques par l'IA** | Le cœur du besoin : remplacer l'appel manuel. |
| 8 | **Conduite naturelle de la conversation** | Mener l'entretien comme un enquêteur, avec relances et reformulations à sens constant. |
| 9 | **Suivi des appels** | Voir en temps réel l'état des appels et des contacts. |
| 10 | **Transcription** | Garder une trace fidèle de chaque échange. |
| 11 | **Enregistrement structuré des réponses** | Exploiter les réponses par question. |
| 12 | **Résumé IA** | Synthétiser automatiquement chaque entretien (surtout les réponses ouvertes). |
| 13 | **Statistiques** | Répartition des réponses et indicateurs d'avancement. |
| 14 | **Export Excel et CSV** | Livrer les données au commanditaire. |
| 15 | **Gestion des statuts & rappels** | Refus, sans réponse, à rappeler, injoignable, complété. |

> Note : l'**authentification** des utilisateurs et la **confidentialité des
> données** sont des exigences transverses (voir §9), pas des fonctionnalités
> métier à proprement parler, mais elles conditionnent la mise en service.

---

## 7. Rôles utilisateurs

La V1 vise une petite équipe interne. Trois rôles suffisent au besoin du premier
client.

### 7.1 Chargé d'études (utilisateur principal)

- **Responsabilités** : concevoir les questionnaires, importer et vérifier les
  contacts, lancer et suivre les campagnes, consulter et exporter les résultats.
- **Besoins** : créer une étude de bout en bout sans compétence technique,
  suivre l'avancement, obtenir des données exploitables.
- **Actions autorisées** : créer/modifier questionnaires, importer contacts,
  créer/lancer/mettre en pause une campagne, consulter le tableau de bord,
  exporter.

### 7.2 Superviseur / Responsable d'études

- **Responsabilités** : garantir la qualité méthodologique, valider les
  questionnaires, contrôler les résultats et les indicateurs.
- **Besoins** : vue d'ensemble de toutes les campagnes, accès aux indicateurs de
  réussite et à la qualité des réponses.
- **Actions autorisées** : tout ce que fait le chargé d'études, plus la
  **validation** des questionnaires/campagnes et la consultation transversale.

### 7.3 Administrateur

- **Responsabilités** : gérer les accès des utilisateurs et les paramètres
  généraux du logiciel.
- **Besoins** : maîtriser qui accède à l'outil et aux données.
- **Actions autorisées** : créer/désactiver les comptes, attribuer les rôles,
  gérer les paramètres globaux.

> Pour le premier client, une même personne peut cumuler plusieurs rôles. La
> distinction sert à clarifier les **responsabilités** et les **droits**.

---

## 8. Parcours utilisateur complet

Déroulé de référence d'une étude de marché, **de la connexion à l'export**.

1. **Connexion** — le chargé d'études se connecte au logiciel.
2. **Création du questionnaire** — il saisit les questions, leurs types, leurs
   réponses possibles et les branchements, puis le fait **valider** par le
   superviseur.
3. **Import des contacts** — il importe le fichier CSV de la liste d'appel.
4. **Vérification des contacts** — il consulte le rapport de qualité (doublons,
   numéros invalides, lignes incomplètes) et corrige/écarte les contacts à
   problème.
5. **Création de la campagne** — il associe le questionnaire et la liste, puis
   règle les paramètres : plage horaire, nombre de tentatives, objectif de
   réponses, durée maximale d'appel.
6. **Lancement** — il démarre la campagne.
7. **Déroulement automatique** — l'IA appelle les contacts, mène les
   conversations, gère refus/sans réponse/rappels, et enregistre les réponses et
   transcriptions.
8. **Suivi en temps réel** — il surveille l'avancement sur le tableau de bord
   (appels passés, réponses obtenues, statuts, indicateurs).
9. **Gestion en cours de route** — il peut **mettre en pause / reprendre** la
   campagne si nécessaire.
10. **Clôture** — la campagne se termine quand l'objectif est atteint ou la liste
    épuisée.
11. **Consultation des résultats** — il analyse statistiques et résumés, y
    compris les réponses ouvertes synthétisées par l'IA.
12. **Export** — il exporte les données en Excel/CSV pour le commanditaire.

---

## 9. Contraintes métier

Ces contraintes définissent le **comportement attendu** du logiciel face aux
réalités du terrain.

### 9.1 Durée des appels

- Un appel doit avoir une **durée maximale paramétrable** (objectif indicatif :
  un entretien court, de l'ordre de quelques minutes).
- Au-delà, l'IA doit **clore poliment** sans dénaturer l'étude.

### 9.2 Gestion des refus

- Si la personne **refuse** de participer, l'IA doit **respecter le refus
  immédiatement**, clore courtoisement, et marquer le contact comme « refus ».
- Un refus ne doit **pas** être rappelé.

### 9.3 Gestion des appels sans réponse

- En cas de **non-réponse** ou d'**injoignable**, le contact est **reprogrammé**
  selon le nombre de tentatives autorisées.
- Au-delà du nombre maximal de tentatives, le contact est marqué
  « injoignable » et n'est plus rappelé.

### 9.4 Reprise des campagnes

- Une campagne doit pouvoir être **mise en pause puis reprise** sans perte de
  progression ni de données déjà collectées.
- En cas d'interruption (incident, fin de plage horaire), elle doit **reprendre
  proprement** là où elle s'était arrêtée.

### 9.5 Qualité des réponses

- L'IA doit **relancer** lorsqu'une réponse est floue, incomplète ou hors sujet.
- Elle doit **respecter strictement les branchements** et ne poser que les
  questions pertinentes.
- Les réponses doivent être **rattachées sans ambiguïté** à la bonne question.
- Un questionnaire **interrompu** doit être identifié comme « incomplet ».

### 9.6 Confidentialité des données

- Les données manipulées (numéros, identités, réponses, transcriptions) sont des
  **données personnelles** et doivent être traitées de façon **confidentielle**.
- L'accès aux données doit être **réservé aux utilisateurs autorisés**.
- Le traitement doit pouvoir respecter la **réglementation applicable** sur la
  protection des données et le démarchage téléphonique.

### 9.7 Reformulation sans changement de sens

- L'IA peut **reformuler** une question pour rester naturelle et fluide, mais
  **sans jamais en altérer le sens** ni introduire de biais.
- La **liste des réponses possibles** d'une question fermée ne doit pas être
  modifiée par la reformulation.

---

## 10. Critères de réussite

Indicateurs permettant de juger qu'une campagne — et donc le logiciel — répond
au besoin.

### 10.1 Indicateurs de campagne

- **Taux de réponse** : part des contacts joints ayant accepté de répondre.
- **Taux de questionnaires terminés** : part des entretiens menés **jusqu'au
  bout** parmi ceux commencés.
- **Durée moyenne d'un entretien** : doit rester dans la cible définie.
- **Coût par enquête complétée** : coût total de la campagne rapporté au nombre
  de questionnaires complets.
- **Atteinte de l'objectif** : nombre de réponses complètes obtenu vs objectif
  fixé, dans le délai imparti.

### 10.2 Indicateurs de qualité

- **Fidélité au questionnaire** : branchements respectés, aucune question posée à
  tort ou omise.
- **Exploitabilité des réponses** : réponses claires, correctement rattachées,
  réponses ouvertes correctement transcrites et résumées.
- **Respect des règles** : refus respectés, durée maximale tenue, plages
  horaires respectées.

### 10.3 Critère global de réussite (V1)

> La première version est considérée comme réussie si une étude de marché peut
> être menée **de bout en bout sans intervention humaine pendant les appels**,
> avec des données **aussi fiables qu'un enquêteur humain**, pour un **coût et un
> délai significativement réduits**, et dans le **respect des règles métier et de
> la confidentialité**.

---

## 11. Hors périmètre (V1)

Explicitement **exclus** de cette première version, pour rester concentrés sur
le besoin du premier client :

- Les autres cas d'usage du moteur (satisfaction, qualification de prospects,
  prise de rendez-vous, support client, recrutement, standard téléphonique).
- La **gestion des appels entrants** (la V1 se concentre sur les appels
  **sortants** d'études de marché).
- Toute fonctionnalité de facturation, d'abonnement ou multi-entreprise.
- Toute fonctionnalité « confort » non nécessaire à la réalisation d'une étude.

> Ces éléments restent à la **roadmap** (voir `24_ROADMAP.md`) mais ne font pas
> partie du besoin à satisfaire maintenant.

---

## 12. Glossaire

- **Étude de marché** : collecte structurée de réponses auprès d'un échantillon
  de personnes pour le compte d'un commanditaire.
- **Commanditaire** : le client final qui commande l'étude.
- **Questionnaire** : ensemble ordonné de questions, avec types et règles.
- **Branchement (logique conditionnelle)** : règle qui modifie l'enchaînement
  des questions selon les réponses.
- **Contact** : une personne à appeler, identifiée au minimum par un numéro.
- **Campagne** : exécution d'un questionnaire sur une liste de contacts, selon
  des paramètres donnés.
- **Statut de contact** : état d'avancement d'un contact (à appeler, répondu,
  refus, sans réponse, injoignable, à rappeler, incomplet).
- **Questionnaire complété** : entretien mené jusqu'au bout, exploitable.
- **Transcription** : retranscription écrite de l'échange téléphonique.
- **Résumé** : synthèse lisible d'un entretien produite par l'IA.

---

## Statut

- [x] Rédigé
- [ ] Relu
- [ ] Validé
