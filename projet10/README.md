# 💧 Projet 10 — Faites une étude sur l'eau potable

![Tableau Public](https://img.shields.io/badge/Tableau-Public-blue) ![Focus](https://img.shields.io/badge/Focus-Data%20Storytelling-orange) ![Projet](https://img.shields.io/badge/Projet-Data%20Analyst-grey)

[← Retour au portfolio principal](../../README.md)

---

## 📌 Résumé

Mission de Data Analyst pour **DWFA (Drinking Water For All)**, ONG dont l'ambition est de garantir l'accès à l'eau potable à chaque individu sur Terre. La direction souhaite un tableau de bord interactif pour identifier les pays en difficulté et prioriser les zones d'intervention.

> **Problématique :** Comment exploiter des données internationales sur l'accès à l'eau potable pour identifier des disparités territoriales et prioriser les zones d'intervention à l'aide d'un tableau de bord décisionnel ?

---

## 🎯 Objectifs du projet

- Identifier les pays rencontrant des difficultés d'accès à l'eau potable
- Analyser l'évolution de l'accès à l'eau et les inégalités sur la période 2000–2017
- Comparer les écarts par pays et par région OMS
- Prioriser les zones d'intervention selon 3 critères : déficit d'accès, poids démographique, instabilité politique

---

## 🔍 Données

5 datasets couvrant la période 2000–2017 (sources OMS et Banque Mondiale) :

| Dataset | Volume | Contenu |
|---|---|---|
| `BasicAndSafelyManagedDrinkingWaterServices.csv` | 10 476 lignes | Accès basique & sécurisé Urban/Rural |
| `MortalityRateAttributedToWater.csv` | 549 lignes | Décès liés à l'eau insalubre (2016) |
| `PoliticalStability.csv` | 3 526 lignes | Indice de gouvernance Banque Mondiale |
| `Population.csv` | 20 914 lignes | Population totale par pays et par année |
| `RegionCountry.csv` | 194 lignes | Segmentation régionale OMS |

---

## 🛠️ Méthodologie de conception

**01 — Blueprint**
Définition des KPIs, des vues, des filtres et de la logique de navigation. Validation avec les besoins métier issus du CR de réunion de lancement.

**02 — Notebook Python**
Chargement des 5 fichiers sources, renommage des colonnes, jointure sur Country + Year, pivot Urban/Rural.

**03 — Mise en œuvre**
Développement du dashboard dans Tableau Public avec connexion aux sources de données et création de champs calculés.

---

## ✅ Compétences développées

| Compétence | Détail |
|---|---|
| Business Intelligence | Analyse du besoin métier et définition de KPIs sectoriels |
| Data Prep & Blending | Nettoyage et jointures de sources de données disparates via Python |
| Data Storytelling | Construction d'une histoire en 3 vues : Monde · Continent · Pays |
| Data Viz | Cartes choroplèthes, scatter plots, graphiques temporels, bulles comparatives |
| Accessibilité | Palette bleu/orange daltonien-friendly, tooltips, labels redondants |

---

## 📊 Structure du tableau de bord

3 vues interactives navigables par clic :

- **Vue Mondiale** : carte choroplèthe, KPIs globaux, évolution 2000–2017, répartition accès basique/sécurisé/sans accès
- **Vue Continentale** : filtre Région OMS, comparaison accès basique vs sécurisé, heatmap temporelle, classement mortalité
- **Vue Pays** : indicateurs démographiques, stabilité politique, scatter plots corrélation eau/mortalité, indice de vulnérabilité

---

## 🖼️ Illustration

![apercu](./apercu.png)

---

## 📁 Structure du dossier

| Fichier / Dossier | Description |
|---|---|
| `enonce/` | PDFs OpenClassrooms (scénario, CR réunion, livrables) |
| `donnees/` | 5 fichiers CSV sources |
| `livrables/` | Présentation PowerPoint · Dashboard Tableau (.twbx) · Blueprint · Mockup |
| `apercu.png` | Diapositive de titre de la présentation |

---

## 🔧 Outils utilisés

- **Visualisation :** Tableau Public
- **Préparation :** Python · pandas · numpy
- **Présentation :** PowerPoint

---

*Projet réalisé dans le cadre de la formation Data Analyst — OpenClassrooms (RNCP niveau 6)*
