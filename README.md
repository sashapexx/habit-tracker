# SASHA — HABIT TRACKER PROJECT

> **"La discipline est la liberté."**
> Un outil personnel de suivi quotidien des habitudes, conçu pour construire une routine disciplinée, mesurer sa progression semaine après semaine, et devenir une meilleure version de soi — chaque jour.

---

## Table des matières

1. [À propos du projet](#à-propos-du-projet)
2. [Fonctionnalités actuelles](#fonctionnalités-actuelles)
3. [Structure du projet](#structure-du-projet)
4. [Installation & utilisation](#installation--utilisation)
5. [Les habitudes suivies](#les-habitudes-suivies)
6. [Système de scoring](#système-de-scoring)
7. [Roadmap & évolutions futures](#roadmap--évolutions-futures)
8. [Stack technique](#stack-technique)
9. [Philosophie du projet](#philosophie-du-projet)

---

## À propos du projet

**Habit Tracker** est un outil personnel de suivi des habitudes quotidiennes, développé pour monitorer 10 domaines clés de l'amélioration personnelle : sport, alimentation, sommeil, productivité, lecture, discipline mentale, hydratation, et hygiène de vie.

L'objectif n'est pas de créer un outil complexe — c'est de créer **le bon outil** : celui qu'on ouvre chaque jour, qu'on remplit honnêtement, et qui reflète exactement où on en est.

Ce projet est une base solide, conçue pour évoluer vers un produit complet avec historique, statistiques, rappels, et synchronisation multi-appareils.

---

## Fonctionnalités actuelles

### Tableau de bord hebdomadaire
- **Sélecteur de semaine** — navigation entre semaines passées et futures
- **4 KPIs en temps réel** :
  - Score global de la semaine (%)
  - Nombre de jours à ≥ 8/10
  - Meilleure habitude de la semaine
  - Streak actuel (jours consécutifs ≥ 5/10)

### Tracker quotidien
- Vue **7 jours** de lundi à dimanche
- Mise en évidence automatique du **jour actuel**
- Deux types d'entrée selon l'habitude :
  - ✅ **Checkbox OUI/NON** — pour les habitudes binaires (sport, lecture, méditation...)
  - 🔢 **Score /10** — pour les habitudes graduelles (alimentation, sommeil, productivité...)
- **Mini barre de progression** visuelle sous chaque score
- **Colonne notes** — une note libre par habitude pour le jour actuel

### Bilan hebdomadaire
- Trois zones de réflexion structurée :
  - **01 — Objectifs** : ce que je vise cette semaine
  - **02 — Bilan** : honnêteté totale sur ce qui s'est passé
  - **03 — Améliorations** : actions concrètes pour la semaine suivante

### Persistance des données
- Sauvegarde automatique dans le **localStorage** du navigateur
- Aucune perte de données entre sessions
- Historique complet par semaine conservé

### Design
- Interface dark mode, thème bleu nuit professionnel
- Typographies : Bebas Neue, Space Mono, Inter
- Responsive (desktop / tablette / mobile)
- Animations fluides, scrollbar custom, sticky header

---

## Structure du projet

```
habit-tracker/
│
├── README.md                     # Ce fichier
├── CHANGELOG.md                  # Historique des versions
├── .gitignore
│
├── src/                          # Code source principal
│   ├── index.html                # Point d'entrée (version standalone)
│   │
│   ├── css/
│   │   ├── main.css              # Styles globaux, variables CSS
│   │   ├── components.css        # Styles des composants (KPI, table, bilan...)
│   │   └── responsive.css        # Media queries
│   │
│   ├── js/
│   │   ├── app.js                # Initialisation & logique principale
│   │   ├── habits.js             # Données des habitudes (config)
│   │   ├── state.js              # Gestion de l'état & localStorage
│   │   ├── ui.js                 # Rendu DOM (table, KPIs, bilan)
│   │   ├── scoring.js            # Calculs de scores et statistiques
│   │   └── utils.js              # Helpers date, formatage...
│   │
│   └── assets/
│       └── fonts/                # Polices si hébergement local
│
├── dist/                         # Build de production (généré)
│   └── habit-tracker.html        # Version standalone compilée (actuelle)
│
├── docs/                         # Documentation complémentaire
│   ├── HABITS.md                 # Description détaillée des habitudes
│   ├── SCORING.md                # Méthode de scoring expliquée
│   └── screenshots/              # Captures d'écran du projet
│
└── config/
    └── habits.config.json        # Configuration des habitudes (JSON)
```

---

## Installation & utilisation

### Version actuelle (standalone HTML)

Le projet fonctionne actuellement comme un **fichier HTML unique** — aucune installation requise.

```bash
# 1. Télécharger le fichier
habit-tracker-project.html

# 2. Ouvrir dans n'importe quel navigateur moderne
# Chrome, Firefox, Safari, Edge — tout fonctionne

# 3. C'est tout. Les données sont sauvegardées automatiquement.
```

### Pour les futures versions modulaires

```bash
# Cloner le repo
git clone https://github.com/sashapexx/habit-tracker.git
cd habit-tracker

# Ouvrir en développement (serveur local recommandé)
npx serve src/
# ou
python3 -m http.server 3000
```

### Utilisation quotidienne

1. **Chaque matin** — ouvrir l'app, vérifier la semaine en cours
2. **Au fil de la journée** — cocher les habitudes au fur et à mesure
3. **Chaque soir** — compléter les scores, ajouter des notes si besoin
4. **Chaque dimanche** — remplir le bilan hebdomadaire (objectifs → bilan → améliorations)
5. **Navigation** — utiliser le sélecteur de semaine pour revoir les semaines passées

---

## Les habitudes suivies

### 🏋️ CORPS & PHYSIQUE

| Habitude | Type | Description |
|---|---|---|
| 🏋️ Sport / Musculation | Checkbox | Séance de salle effectuée (oui/non) |
| 🏃 Course à pied | Checkbox | Sortie running effectuée (oui/non) |
| 🥗 Alimentation saine | Score /10 | Qualité globale de l'alimentation |
| 💧 Hydratation | Score /10 | Consommation d'eau suffisante |
| 🌙 Sommeil | Score /10 | Qualité + durée du sommeil |

### ⚡ MENTAL & PRODUCTIVITÉ

| Habitude | Type | Description |
|---|---|---|
| ⚡ Productivité / Travail | Score /10 | Niveau de focus et d'efficacité |
| 📖 Lecture / Apprentissage | Checkbox | Session de lecture ou apprentissage |
| 🧠 Méditation / Discipline | Checkbox | Practice de mindfulness ou focus |

### ✨ HYGIÈNE DE VIE

| Habitude | Type | Description |
|---|---|---|
| 📵 Sans écrans / Réseaux | Checkbox | Journée sans scrolling passif |
| ✨ Hygiène & Soins perso | Checkbox | Routine d'hygiène complète |

---

## Système de scoring

### Score journée

Chaque jour reçoit un **score /10** calculé automatiquement :
- Chaque habitude vaut **10 points**
- Les checkboxes : **10 pts** si coché, **0 pts** sinon
- Les scores : la valeur entrée (0–10)
- Le score final = total obtenu / total possible × 10

**Interprétation :**
- ≥ 8.0 → 🔵 Journée excellente (discipline totale)
- ≥ 5.0 → 💙 Journée correcte (maintien du streak)
- < 5.0 → 🩶 Journée difficile (à analyser)

### KPIs hebdomadaires

| KPI | Calcul |
|---|---|
| Score semaine | Moyenne pondérée de tous les scores journée |
| Jours ≥ 8/10 | Nombre de journées "excellentes" sur 7 |
| Meilleure habitude | Habitude avec le meilleur taux de réussite sur la semaine |
| Streak | Nombre de jours consécutifs ≥ 5/10 depuis lundi |

---

## Roadmap & évolutions futures

### v2.1 — Améliorations immédiates
- [ ] Export des données en JSON / CSV
- [ ] Mode impression / PDF du bilan hebdomadaire
- [ ] Possibilité de personnaliser les habitudes (ajout / suppression)
- [ ] Thème clair (light mode toggle)

### v3.0 — Statistiques & visualisation
- [ ] **Vue mensuelle** — calendrier de chaleur (heatmap) par habitude
- [ ] **Graphiques d'évolution** — courbes de progression sur 4, 8, 12 semaines
- [ ] **Vue par habitude** — focus sur une seule habitude, son historique complet
- [ ] **Records personnels** — meilleur streak, meilleure semaine, meilleur mois

### v4.0 — Application Progressive (PWA)
- [ ] Installable sur mobile (icône sur l'écran d'accueil)
- [ ] **Rappels quotidiens** — notifications push configurables
- [ ] Fonctionnement **hors-ligne** complet
- [ ] Synchronisation avec le cloud (optionnelle)

### v5.0 — Backend & multi-appareils
- [ ] **Authentification** — compte utilisateur
- [ ] Données sauvegardées en base (Supabase ou Firebase)
- [ ] Accès depuis n'importe quel appareil
- [ ] **Mode partage** — partager ses stats avec un partenaire de discipline
- [ ] API REST pour intégrations tierces (Notion, Obsidian, etc.)

### Idées supplémentaires
- 🎯 **Objectifs quantifiés** — ex: "3 séances de sport cette semaine"
- 🏆 **Système de badges** — récompenses pour les milestones (streak 7j, 30j, 100j...)
- 📊 **Rapport mensuel automatique** — synthèse IA de la progression
- 📅 **Intégration calendrier** — voir ses habitudes dans Google Calendar
- 🤝 **Mode accountability** — partager son tracker avec un ami

---

## Stack technique

### Version actuelle
- **HTML5** — structure sémantique
- **CSS3** — variables CSS, Grid, Flexbox, animations
- **JavaScript Vanilla (ES6+)** — logique pure, zéro dépendance
- **localStorage** — persistance des données côté client
- **Google Fonts** — Bebas Neue, Space Mono, Inter

### Stack envisagée pour les versions futures

| Couche | Technologie recommandée | Pourquoi |
|---|---|---|
| Frontend | **React + Vite** | Composants réutilisables, state management |
| Styles | **Tailwind CSS** | Cohérence, rapidité, utilitaires |
| Graphiques | **Recharts** ou **Chart.js** | Visualisations de données |
| Backend | **Supabase** | BDD PostgreSQL + Auth + API en un |
| Déploiement | **Vercel** | Déploiement instantané, CI/CD gratuit |
| PWA | **Workbox** | Service workers, cache, notifications |

---

## Philosophie du projet

Ce tracker est construit sur une conviction simple : **ce qui se mesure s'améliore**.

Mais au-delà des chiffres, l'objectif est de construire une **identité disciplinée** — de devenir quelqu'un qui fait ce qu'il dit, chaque jour, même quand c'est difficile, même quand personne ne regarde.

Le bilan hebdomadaire n'est pas optionnel. C'est là que se fait le vrai travail : l'honnêteté avec soi-même, l'analyse froide, et l'engagement concret pour la semaine suivante.

> *Chaque jour compte. Pas parce que chaque jour est parfait — mais parce que chaque jour est une décision.*

---

## Licence

Usage personnel. Projet en développement actif.

---

*SASHA HABIT TRACKER PROJECT · v2.0 · 2025*
