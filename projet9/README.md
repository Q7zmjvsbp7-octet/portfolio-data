# 📚 Projet 9 — Analysez les ventes d'une librairie avec R ou Python

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Library-Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Focus](https://img.shields.io/badge/Focus-Analyse%20Statistique-orange?style=flat)
![Projet](https://img.shields.io/badge/Projet-Data%20Analyst-blue?style=flat)

[← Retour au portfolio principal](../README.md)

---

## 📌 Résumé

Mission de Data Analyst pour **Lapage**, librairie physique ayant ouvert un site de vente en ligne il y a deux ans. La direction souhaite disposer d'une analyse globale des performances commerciales et du comportement clients pour orienter ses décisions stratégiques.

> **Problématique :** Comment analyser les ventes et le comportement des clients d'une librairie en ligne pour identifier les leviers de croissance et les risques à anticiper ?

---

## 🎯 Objectifs du projet

- Analyser l'évolution du chiffre d'affaires dans le temps
- Identifier les catégories de produits les plus performantes
- Comprendre les profils et comportements clients (segmentation, démographie)
- Détecter les corrélations significatives entre profils clients et habitudes d'achat
- Formuler des recommandations stratégiques orientées business

---

## 🔍 Données

3 datasets couvrant mars 2021 à février 2023 :

| Dataset | Volume | Contenu |
|---|---|---|
| `customers` | 8 621 lignes | Données démographiques clients |
| `products` | 3 286 lignes | Catalogue livres (prix, catégorie) |
| `transactions` | 687 534 lignes | Historique des ventes |

---

## 🛠 Préparation des données

- Conversion et correction des dates (erreurs d'horodatage > 24h)
- Fusion des 3 fichiers via jointures SQL-like (Outer Joins)
- Identification et exclusion des 4 clients BtoB VIP (traitement séparé)
- Calcul de l'âge réel des clients au moment de l'analyse
- Création d'indicateurs dérivés : panier moyen, fréquence d'achat, segmentation

---

## ✅ Compétences développées

| Compétence | Détail |
|---|---|
| **Analyse de séries temporelles** | CA mensuel + moyenne mobile 3 mois (MM3) |
| **Segmentation clients** | Pyramide de contribution CA (VIP → Dormeur) |
| **Analyse de concentration** | Courbe de Lorenz · Indice de Gini · Pareto |
| **Tests statistiques** | 5 tests : Chi² · ANOVA · Spearman · Kruskal-Wallis |
| **Business Intelligence** | Recommandations stratégiques orientées décision |

---

## 📊 Analyses & Résultats clés

**Analyses descriptives**
- CA total : **12 027 663 €** sur la période · CA annuel 2022 : 6 108 682 €
- Arrêt total du recrutement de nouveaux clients à partir de **février 2022**
- 24 produits invendus sur 3 286 référencés → potentielle suppression catalogue
- Concentration forte : Gini produits = **0,743** · Gini clients = **0,398**
- Tranche d'âge la plus représentée : 36-45 ans (20,6% des clients)

**5 tests statistiques**
- **Chi² — Genre / Catégorie :** lien significatif mais très faible (V de Cramer = 0,01)
- **ANOVA — Âge / Dépenses totales :** différence significative entre tranches d'âge (η² = 0,06)
- **Spearman — Âge / Fréquence d'achat :** corrélation négative forte (ρ = -0,659)
- **Kruskal-Wallis — Âge / Panier moyen :** panier moyen diminue significativement avec l'âge
- **Chi² — Âge / Catégorie achetée :** association modérée (V de Cramer = 0,375)

---

## 📊 Illustration

![Aperçu — Projet 9 Lapage](./apercu.png)

---

## 🗂 Structure du dossier

| Fichier / Dossier | Description |
|---|---|
| `enonce/` | PDFs OpenClassrooms (scénario, mission, livrables) |
| `donnees/` | Fichiers sources : customers · products · transactions |
| `livrables/` | Notebook Python · Présentation PowerPoint |
| `apercu.png` | Diapositive de titre de la présentation |

---

## 🛠 Outils utilisés

- **Langage :** Python 3.8+
- **Manipulation :** `pandas` · `numpy`
- **Visualisation :** `matplotlib` · `seaborn`
- **Tests statistiques :** `scipy`
- **Environnement :** Jupyter Notebook
- **Présentation :** PowerPoint

---

## 📋 Recommandations stratégiques

- Cibler les femmes de 35-55 ans avec les produits de catégorie 1
- Développer une offre pour les 20-30 ans avec les produits premium (catégorie 2)
- Revoir le catalogue : supprimer ou relancer les 24 produits invendus
- Relancer l'acquisition client — arrêt total depuis février 2022

---

*Projet réalisé dans le cadre de la formation Data Analyst — OpenClassrooms (RNCP niveau 6)*
