# Énoncé du problème

## 1. Contexte
Une **institution financière** souhaite réduire son exposition au risque de **défaut de paiement** en évaluant, avant l’octroi d’un crédit, la **probabilité qu’un client rembourse correctement son prêt**.

Le dataset utilisé (`credit-g`, issu d’[OpenML](https://www.openml.org/d/31)) contient des informations **socio-économiques, professionnelles et financières** sur des demandeurs de crédit en Allemagne.

---

## 2. Objectif Machine Learning
Développer un **modèle de classification binaire** permettant de prédire la variable cible `class` :
- `good` → client solvable
- `bad` → client à risque de défaut

L’objectif principal est d’obtenir un **modèle performant et interprétable**, optimisant le compromis entre :
- **Performance globale** (AUC, F1-score)
- **Coût métier des erreurs** :
  - Faux négatif (client risqué accepté)
  - Faux positif (client fiable refusé)

---

## 3. Portée du projet
### Inclus :
- Données tabulaires issues du dataset `credit-g`
- Variables socio-économiques et financières (ex : durée du crédit, revenu, statut personnel, emploi)
- Expérimentation de plusieurs modèles supervisés (logistique, arbre, boosting)

### Exclus :
- Déploiement en production temps réel
- Aspects réglementaires ou juridiques (conformité, RGPD)
- Études approfondies sur les biais démographiques *(abordées en tant que limites du modèle)*

---

## 4. Contraintes et exigences
- Le modèle doit rester **interprétable** pour un usage métier (explicabilité exigée).
- Les métriques principales d’évaluation seront :
  - **AUC (Area Under the ROC Curve)**
  - **F1-score**
- L’analyse doit mettre en évidence le **coût différencié** des erreurs de classification (FN vs FP).
- L’ensemble des scripts doit être **reproductible** et **versionné** (Git).

---

## 5. Livrables attendus
- Rapport complet suivant la méthodologie **CRISP-DM**
- Notebook(s) d’analyse et de modélisation
- Modèle sauvegardé (`.pkl`)
- Visualisations :
  - Matrice de confusion
  - Courbe ROC / AUC
  - Feature importance
- *(Optionnel)* Mini-application de démonstration (ex. Streamlit ou FastAPI)

---

## 6. Critères de succès
- **AUC ≥ 0.75**
- **F1-score équilibré** entre classes `good` et `bad`
- Documentation claire et traçabilité des décisions à chaque phase du CRISP-DM
