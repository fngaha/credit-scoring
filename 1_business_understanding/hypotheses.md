# Hypothèses de travail

Ce document formalise les principales **hypothèses exploratoires** guidant l’analyse des données et la modélisation du risque de crédit.  
Elles orienteront la phase de **Data Understanding** (exploration) et serviront à **valider ou infirmer** certaines relations entre variables explicatives et la variable cible `class` (`good` / `bad`).

---

## H1 — Statut d’épargne et risque de défaut
> **Hypothèse :** Un statut d’épargne favorable (montant d’épargne élevé) est associé à un **risque de défaut plus faible**.

**Justification :**  
Les clients disposant d’une épargne stable témoignent d’une meilleure capacité à faire face aux imprévus financiers, ce qui réduit leur probabilité de non-remboursement.

**Vérification envisagée :**
- Analyse de la distribution du risque selon les classes de la variable `saving_status`
- Test du chi² (variable catégorielle vs cible)
- Visualisation : barplot ou stacked bar chart

---

## H2 — Durée du crédit
> **Hypothèse :** Des **durées de crédit plus longues** augmentent le risque de défaut.

**Justification :**  
Un allongement de la durée du prêt accroît l’incertitude économique et la probabilité d’événements défavorables survenant pendant le remboursement.

**Vérification envisagée :**
- Corrélation entre `duration` et `class`
- Visualisation : boxplot ou histogramme groupé

---

## H3 — Historique de paiement
> **Hypothèse :** Un **historique de paiement défavorable** accroît la probabilité de défaut.

**Justification :**  
Les antécédents de crédit sont un indicateur fort du comportement de remboursement futur.

**Vérification envisagée :**
- Analyse de la variable `checking_status`
- Comparaison du taux de “bad” selon les différentes classes
- Visualisation : heatmap ou grouped bar chart

---

## H4 — Statut professionnel et personnel
> **Hypothèse :** Certains **types d’emploi** ou **statuts personnels** corrèlent avec le risque de défaut.

**Justification :**  
La stabilité de l’emploi et le contexte familial influencent la solvabilité (revenus réguliers, soutien familial, dépendants).

**Vérification envisagée :**
- Variables : `employment`, `personal_status`
- Analyses croisées avec la variable cible (`class`)
- Tests d’indépendance ou d’association (chi²)

---

## H5 — Non-linéarité du phénomène
> **Hypothèse :** La relation entre les variables explicatives et le risque de défaut **n’est pas strictement linéaire**.

**Justification :**  
Les effets combinés (interactions, seuils) peuvent rendre les modèles linéaires insuffisants.  
Des modèles non linéaires (Random Forest, XGBoost, CatBoost) sont donc susceptibles de mieux capturer les relations complexes.

**Vérification envisagée :**
- Comparaison des performances entre modèles linéaires et non linéaires
- Analyse de la courbe ROC et du gain en AUC

---

## Conclusion
Ces hypothèses serviront de **fil conducteur** à la phase d’analyse exploratoire (EDA).  
Elles seront **validées, ajustées ou rejetées** en fonction des résultats statistiques et visuels obtenus.

---
