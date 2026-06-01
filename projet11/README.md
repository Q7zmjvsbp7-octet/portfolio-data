🐔 Projet 11 — Produisez une étude de marché avec R ou Python

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![ACP](https://img.shields.io/badge/ACP-Clustering-orange)
![Machine Learning](https://img.shields.io/badge/Segmentation-Marchés-green)
![Projet](https://img.shields.io/badge/Projet-Data%20Analyst-lightgrey)

← Retour au portfolio principal

---

# 📌 Résumé

Mission de Data Analyst pour **La Poule qui Chante**, entreprise française spécialisée dans la production de poulets biologiques.

La direction souhaite identifier les marchés internationaux les plus pertinents pour développer son activité export.

> **Problématique :**
>
> Comment identifier, parmi plus de 150 pays, les marchés les plus attractifs pour exporter du poulet français en combinant potentiel économique, accessibilité logistique et dépendance aux importations ?

---

# 🎯 Objectifs du projet

- Construire une base de données internationale consolidée
- Identifier les facteurs expliquant l’attractivité des marchés
- Réduire la dimension des données via une ACP
- Segmenter les pays selon leurs caractéristiques communes
- Prioriser les marchés les plus intéressants pour une PME exportatrice
- Produire des recommandations opérationnelles pour le COMEX

---

# 🔎 Données

8 sources open data ont été mobilisées selon une logique PESTEL.

| Dataset | Contenu |
|----------|----------|
| Population_2000_2018.csv | Population mondiale |
| Macro_pib_2017.csv | PIB par habitant |
| DisponibiliteAlimentaire_2017.csv | Consommation alimentaire |
| Production_poulet_2017.csv | Production locale |
| Import_poulet_2017.csv | Importations |
| Prix_poulet_2017.csv | Prix producteur |
| Stabilite_politique_2017.csv | Indice WGI Banque Mondiale |
| distance_pays.xls | Distances géographiques CEPII |

---

# 🛠️ Méthodologie de conception

### 01 — Collecte & Préparation

- Sélection de 8 sources internationales
- Harmonisation des codes pays ISO3
- Fusion des datasets
- Traitement des valeurs manquantes
- Construction d'un dataset final de 153 pays

### 02 — Analyse exploratoire

- Analyse univariée
- Détection des valeurs atypiques
- Matrice de corrélation
- Justification des exclusions de variables

### 03 — ACP

- Standardisation des variables
- Analyse en Composantes Principales
- Cercle des corrélations
- Projection des individus
- Conservation de 78,8 % de l'information en 5 composantes

### 04 — Clustering

- Classification Ascendante Hiérarchique (CAH)
- Algorithme K-Means
- Détermination du nombre optimal de clusters
- Validation croisée des résultats

### 05 — Recommandations Export

- Construction d'un score composite pondéré
- Classement des marchés
- Priorisation des pays cibles
- Recommandations stratégiques

---

# ✅ Compétences développées

| Compétence | Détail |
|------------|---------|
| Data Cleaning | Fusion et harmonisation multi-sources |
| Feature Engineering | Construction de 3 indicateurs métier |
| Analyse exploratoire | Corrélations, distributions, outliers |
| ACP | Réduction de dimension |
| Clustering | CAH et K-Means |
| Data Storytelling | Transformation des résultats en recommandations |
| Business Intelligence | Aide à la décision export |

---

# 📊 Structure de l'analyse

### Vue 1 — Préparation des données

- 8 sources
- 153 pays
- 22 variables
- 0 valeur manquante

### Vue 2 — Analyse ACP

- Ébouli des valeurs propres
- Cercle des corrélations
- Projection des individus
- Analyse des axes factoriels

### Vue 3 — Clustering

- Méthode du coude
- Score silhouette
- Dendrogramme CAH
- Segmentation K-Means

### Vue 4 — Décision Export

- Analyse des profils clusters
- Score composite
- Top 30 marchés recommandés
- Priorisation des actions

---

# 🖼️ Illustration

![Aperçu du projet](apercu.png)

---

# 📁 Structure du dossier

| Fichier / Dossier | Description |
|------------------|-------------|
| enonce/ | Cahier des charges OpenClassrooms |
| donnees/ | Sources utilisées |
| notebooks/ | Préparation, ACP et Clustering |
| livrables/ | Présentation finale |
| apercu.png | Illustration du projet |

---

# 🔧 Outils utilisés

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- SciPy
- PowerPoint

---

# 📂 Livrables

- Notebook préparation et nettoyage
- Notebook ACP et clustering
- Présentation COMEX
- Recommandations export

---

# 🏆 Résultat final

153 pays analysés

10 variables stratégiques retenues

4 segments de marchés identifiés

30 marchés export recommandés

2 vagues de déploiement proposées :

- Vague 1 : marchés premium proches et solvables
- Vague 2 : marchés dépendants aux importations à fort potentiel
