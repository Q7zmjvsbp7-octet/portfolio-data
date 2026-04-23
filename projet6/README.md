# 🚀 Projet 6 — Optimisez la gestion des données d'une boutique avec Python

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Library-Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Focus](https://img.shields.io/badge/Focus-Data%20Cleaning-green?style=flat)
![Projet](https://img.shields.io/badge/Projet-Data%20Analyst-blue?style=flat)

[← Retour au portfolio principal](../README.md)

---

## 📌 Résumé

Mission de Data Analyst pour **BottleNeck**, marchand de vins prestigieux.
L'objectif : réconcilier des données issues de trois sources hétérogènes
(ERP, site web WordPress, table de liaison) afin de constituer une base fiable,
puis produire des analyses décisionnelles à destination du CODIR.

> **Problématique :** Comment fiabiliser et exploiter des données de vente,
> de produits et de stocks afin de produire des analyses cohérentes et utiles
> pour le pilotage d'une activité commerciale ?

---

## 🎯 Objectifs du projet

- Rapprocher les données ERP et site web via la table de liaison
- Identifier et traiter les incohérences (doublons, valeurs manquantes,
  colonnes mal renseignées, valeurs négatives)
- Produire des analyses univariées et multivariées orientées décision
- Justifier les choix de traitement au regard du RGPD

---

## ✅ Compétences développées

| Compétence | Détail |
|---|---|
| **Data Wrangling** | Fusion multi-sources via jointures (Inner / Left Join) |
| **Data Cleaning** | Détection de 8+ anomalies, traitement Z-score et IQR |
| **Analyse exploratoire (EDA)** | Analyses univariées et multivariées |
| **Business Intelligence** | Synthèse en indicateurs clairs pour un public exécutif |
| **Rigueur RGPD** | Justification documentée des choix de traitement |

---

## 🔍 Analyses & Étapes clés

**Phase 1 — Préparation et consolidation**
- Import et audit des trois sources de données
- Harmonisation des formats et gestion des erreurs de saisie
- Fusion des tables via clés de liaison
- Identification de 8 anomalies minimum (doublons, colonnes vides,
  valeurs négatives incohérentes)

**Phase 2 — Analyses statistiques**
- Calcul du chiffre d'affaires par produit et global
- Analyse Pareto 20/80 des meilleures références
- Détection des outliers : **36 produits au-delà de 83,35 €**
  (grands crus millésimés — valeurs cohérentes mais isolées)
- Analyse des marges : taux entre **60 % et 120 %**
  (cognac = marge la plus élevée, huile d'olive = la plus faible)
- Analyse des stocks : le produit n°1 en CA affiche **275 jours de stockage**
- Corrélations : plus un produit est vendu, plus son stock diminue ;
  le prix et le volume vendu ne sont pas corrélés
- Courbe de Lorenz et indice de Gini pour mesurer la concentration des ventes

---

## 📊 Illustration

![Aperçu — Projet 6 BottleNeck](./apercu.png)

---

## 🗂 Structure du dossier

| Fichier / Dossier | Description |
|---|---|
| `enonce/` | PDFs OpenClassrooms (scénario, mission, livrables) |
| `donnees/` | Fichiers sources : erp.xlsx · web.xlsx · liaison.xlsx |
| `livrables/` | Notebook Python · Présentation PowerPoint |
| `apercu.png` | Visualisation principale |

---

## 🛠 Outils utilisés

- **Langage :** Python 3.8+
- **Manipulation :** `pandas` · `numpy`
- **Visualisation :** `matplotlib` · `seaborn`
- **Environnement :** Jupyter Notebook
- **Présentation :** PowerPoint

---

## 📋 Recommandations formulées au CODIR

- Mettre en place des **processus décisionnels de gestion des données**
  pour traiter les incohérences à la source
- Revoir la **rotation et la valorisation des stocks** :
  un produit immobilisé 275 jours ne génère pas de CA et engendre des coûts

---

*Projet réalisé dans le cadre de la formation Data Analyst — OpenClassrooms (RNCP niveau 6)*
