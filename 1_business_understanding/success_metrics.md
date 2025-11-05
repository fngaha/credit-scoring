# Success Metrics

Ce document définit les **indicateurs de performance** utilisés pour évaluer la qualité du modèle de scoring, en cohérence avec les objectifs métier et les contraintes de la phase **Business Understanding**.

---

## Objectif général
Assurer un **équilibre entre performance prédictive et interprétabilité**, tout en limitant le coût des erreurs de classification :
- Minimiser les **faux négatifs (FN)** → clients risqués acceptés à tort.
- Maîtriser les **faux positifs (FP)** → clients fiables refusés injustement.

---

## Indicateurs principaux

| **Métrique** | **Objectif** | **Justification / Interprétation** |
|---------------|--------------|------------------------------------|
| **AUC ROC ≥ 0.80** | Capacité discriminante minimale attendue | Mesure la qualité globale de séparation entre classes "good" et "bad". |
| **Recall (classe "bad") ≥ 0.70** | Taux minimal de détection des clients risqués | Priorité métier : éviter les défauts de remboursement. |
| **Precision (classe "bad") ≥ 0.50** | Limiter le sur-refus de bons clients | Maintient un équilibre entre sensibilité et pertinence. |
| **Stabilité (écart < 3 points entre k-folds)** | Robustesse du modèle sur différents échantillons | Vérifie la généralisabilité du modèle. |

---

## Indicateurs complémentaires

### Courbe coût-bénéfice  
- Analyse du **compromis entre FP et FN** selon différents seuils.  
- Permet d’identifier un **seuil décisionnel optimal** selon le coût métier (ex. perte financière, risque de défaut).

### Matrice de confusion  
- Permet une lecture directe des cas mal classés.  
- Sert à interpréter le **rappel et la précision** sur chaque classe.

### Rapport de classification  
- Résumé des métriques clés (Accuracy, Precision, Recall, F1) pour chaque classe.

---

## Seuil de décision

Le seuil de probabilité par défaut (0.5) sera **ajusté** afin d’optimiser la détection des “bad” :

> **Objectif d’optimisation :**  
> Maximiser `Recall_bad` sous la contrainte `Precision_bad ≥ 0.50`

Ce seuil sera choisi à partir :
- de la **courbe ROC** et/ou **Precision-Recall**
- du **coût relatif** FP/FN défini par l’entreprise

---

## Métriques de validation

Les performances finales seront estimées via :
- **Validation croisée (k-folds)**  
- **Test set** indépendant (20–30% du jeu de données)
- Suivi de la variance inter-folds pour détecter le sur-apprentissage

---

## Critères de succès globaux

Le modèle est considéré comme **réussi** si :
1. `AUC ROC ≥ 0.80`  
2. `Recall_bad ≥ 0.70`  
3. `Écart moyen AUC_kfold < 0.03`  
4. Le rapport coûts/bénéfices est **documenté et interprété**  
5. Le modèle reste **interprétable** (feature importance, SHAP, etc.)

---
