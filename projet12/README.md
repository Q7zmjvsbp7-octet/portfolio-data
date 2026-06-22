# 💶 Projet 12 — Détectez des faux billets avec R ou Python

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Supervisé%20%26%20Non%20supervisé-green)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Projet](https://img.shields.io/badge/Projet-Data%20Analyst-lightgrey)

[← Retour au portfolio principal](../../README.md)

---

# 📌 Résumé

Mission de Data Analyst pour l'**ONCFM (Organisation nationale de lutte contre le faux-monnayage)**, organisation publique chargée de mettre en place des méthodes d'identification des contrefaçons de billets en euros.

L'organisation souhaite une application de machine learning capable de prédire automatiquement la nature d'un billet (vrai ou faux) à partir de ses seules dimensions géométriques.

> **Problématique :**
>
> Comment construire un algorithme capable de différencier automatiquement un vrai billet d'un faux à partir de ses six caractéristiques géométriques, en privilégiant la détection du maximum de faux billets ?

---

# 🎯 Objectifs du projet

- Réaliser une analyse exploratoire du jeu de 1 500 billets étiquetés
- Traiter les valeurs manquantes par imputation plutôt que par suppression
- Explorer la structure des données via une ACP et un clustering non supervisé
- Mettre en concurrence 4 modèles de prédiction recommandés par le client
- Sélectionner le modèle minimisant les faux négatifs (faux billets non détectés)
- Livrer une application fonctionnelle de prédiction à partir d'un fichier de billets

---

# 🔎 Données

Un jeu de **1 500 billets étiquetés** (1 000 vrais, 500 faux), décrits par **6 variables géométriques** exprimées en millimètres.

| Variable | Description |
|----------|-------------|
| `length` | Longueur du billet |
| `height_left` | Hauteur mesurée sur le côté gauche |
| `height_right` | Hauteur mesurée sur le côté droit |
| `margin_up` | Marge entre le bord supérieur et l'image |
| `margin_low` | Marge entre le bord inférieur et l'image |
| `diagonal` | Diagonale du billet |

La variable cible `is_genuine` indique la nature réelle du billet (vrai / faux).

---

# 🛠️ Méthodologie de conception

### 01 — Exploration des données

- Analyse de la répartition vrais / faux (ratio 2/1, benchmark naïf à 66,7 %)
- Distribution des 6 variables par classe (`length` et `margin_low` les plus discriminantes)
- Matrice de corrélation : pas de redondance parfaite entre variables

### 02 — Imputation des valeurs manquantes

- 37 valeurs manquantes sur `margin_low`
- Comparaison de 3 modèles de régression linéaire (OLS)
- Modèle retenu : `length + is_genuine` (meilleur RMSE, 5 conditions OLS validées)
- Vérification : moyenne et écart-type préservés après imputation

### 03 — Préparation & exploration non supervisée

- Split stratifié 80/20 et standardisation (règle anti-fuite : `fit` sur le train uniquement)
- ACP : 2 composantes retenues (coude après PC2)
- K-Means : 2 groupes naturels confirmés (cohérents avec les classes réelles)

### 04 — Modélisation supervisée

- 4 modèles testés : Régression Logistique, KNN, Random Forest, K-Means (centroïdes)
- Métrique prioritaire : le **Recall** (minimiser les faux billets non détectés)
- Évaluation par matrice de confusion et courbe ROC pour chaque modèle

### 05 — Sélection & validation finale

- Comparaison des 4 modèles sur Recall et AUC
- Modèle retenu : **Régression Logistique**
- Pipeline ré-entraîné sur l'ensemble des 1 500 billets et sauvegardé

---

# ✅ Compétences développées

| Compétence | Détail |
|------------|--------|
| Apprentissage supervisé | Prédiction de la nature d'un billet par classification |
| Apprentissage non supervisé | Catégorisation des billets via K-Means |
| Imputation statistique | Régression linéaire OLS et validation des hypothèses |
| Réduction de dimension | ACP et interprétation des axes factoriels |
| Évaluation de modèles | Matrice de confusion, Recall, AUC, courbe ROC |
| Aide à la décision | Justification du modèle retenu pour la production |

---

# 📊 Résultats des modèles

Comparaison des 4 modèles — métrique prioritaire : Recall (faux négatifs minimisés).

| Modèle | Type | Recall | AUC | Faux négatifs |
|--------|------|--------|-----|---------------|
| **Régression Logistique** | Supervisé | **0,990** | **0,9996** | **1** |
| KNN (k=2) | Supervisé | 0,990 | 0,9898 | 1 |
| Random Forest | Supervisé | 0,980 | 0,9993 | 2 |
| K-Means (centroïdes) | Non supervisé | 0,980 | 0,9992 | 2 |

**Modèle retenu : Régression Logistique** — meilleur compromis Recall / AUC, interprétable, et un seul faux billet non détecté sur 100.

---

# 🖼️ Illustration

![Aperçu du projet](apercu.png)

---

# 📁 Structure du dossier

| Fichier / Dossier | Description |
|-------------------|-------------|
| `enonce/` | Cahier des charges et énoncés OpenClassrooms |
| `donnees/` | Jeu des 1 500 billets étiquetés |
| `livrables/` | Notebook d'analyse · Script de l'application · Présentation |
| `apercu.png` | Illustration du projet |

---

# 🔧 Outils utilisés

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Statsmodels
- PowerPoint

---

# 🏆 Résultat final

1 500 billets analysés

6 variables géométriques exploitées

4 modèles mis en concurrence

1 modèle retenu : Régression Logistique (Recall 0,990 · AUC 0,9996)

1 application fonctionnelle de prédiction livrée, testée sur un jeu de production

---

*Projet réalisé dans le cadre de la formation Data Analyst — OpenClassrooms (RNCP niveau 6)*
