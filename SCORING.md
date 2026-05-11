# Système de Scoring — Documentation

## Principe général

Chaque habitude vaut **10 points maximum** par jour.
Le score d'une journée est calculé sur la base de **toutes les habitudes actives**.

---

## Calcul du score journée

```
Score journée = (Points obtenus / Points possibles) × 10
```

**Exemple avec 10 habitudes :**
- Points possibles : 10 habitudes × 10 pts = **100 pts**
- Si 7 checkboxes cochées (70 pts) + scores alimentation 8, eau 7, sommeil 9 = 24 pts
- Total obtenu : 94 / 100 → **Score journée : 9.4 / 10**

---

## Types d'habitudes

### Checkbox (OUI / NON)
- Cochée ✅ → **10 points**
- Non cochée ☐ → **0 point**

Utilisé pour les habitudes binaires : soit tu l'as fait, soit non.
Ex: sport, course, lecture, méditation, sans écran, hygiène

### Score /10
- Valeur entrée directement entre 0 et 10
- Reflète la qualité ou l'intensité, pas juste la présence/absence
- Ex: alimentation 6/10 = quelques écarts mais globalement correct

---

## Interprétation des scores

| Score journée | Couleur | Signification |
|---|---|---|
| ≥ 8.0 / 10 | 🔵 Bleu vif | Journée excellente — discipline totale |
| 5.0 – 7.9 / 10 | 💙 Bleu doux | Journée correcte — maintien du streak |
| < 5.0 / 10 | 🩶 Gris | Journée difficile — à analyser dans le bilan |

---

## KPIs hebdomadaires

### Score semaine (%)
Complétion globale sur 7 jours :
```
Score semaine = (Total points obtenus sur 7j / Total points possibles sur 7j) × 100
```

### Jours ≥ 8/10
Nombre de journées atteignant le seuil "excellent" (8.0 ou plus sur 10).
Objectif cible : **5/7 jours** minimum.

### Meilleure habitude
L'habitude avec le **taux de réussite le plus élevé** sur la semaine.
Calculé comme : `total obtenu pour cette habitude / total possible`.

### Streak
Nombre de **jours consécutifs** depuis lundi avec un score ≥ 5/10.
Se remet à zéro si un jour tombe en-dessous du seuil.

---

## Recommandations

- **Ne pas viser 10/10 chaque jour.** L'objectif réaliste est 7–8/10 en moyenne.
- **Les jours à 5–6 comptent.** L'important est la constance, pas la perfection.
- **Un jour à 3/10 n'est pas un échec.** C'est une information. Analyser dans le bilan.
- **Le streak est ton meilleur indicateur** de constance réelle sur le temps.
