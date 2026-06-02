# 👥 Projet 8 — Analysez des indicateurs de l'égalité femmes-hommes dans le respect du RGPD

![KNIME](https://img.shields.io/badge/KNIME-Workflow-FDD800?style=flat&logo=knime&logoColor=black)
![RGPD](https://img.shields.io/badge/RGPD-Conformité-blue?style=flat)
![RH](https://img.shields.io/badge/Domaine-Ressources%20Humaines-purple?style=flat)
![Projet](https://img.shields.io/badge/Projet-Data%20Analyst-green?style=flat)

[← Retour au portfolio principal](../README.md)

---

## 📌 Résumé

Mission réalisée pour le service Ressources Humaines d'un cabinet de conseil en forte croissance.

L'objectif était d'automatiser la production d'un diagnostic de l'égalité professionnelle femmes-hommes à partir des données du SIRH, tout en garantissant le respect du RGPD et la reproductibilité des analyses.

> **Problématique :** Comment automatiser la production d'indicateurs d'égalité professionnelle tout en respectant les exigences réglementaires liées à la protection des données personnelles ?

---

## 🎯 Objectifs du projet

- Préparer et anonymiser les données RH
- Respecter les contraintes du RGPD
- Construire un workflow automatisé sous KNIME
- Générer un fichier CSV réutilisable pour de futures analyses
- Calculer les principaux indicateurs de l'index égalité femmes-hommes
- Formuler des recommandations d'amélioration

---

## 🔍 Données

3 fichiers issus du Système d'Information des Ressources Humaines (SIRH) :

| Dataset | Contenu |
|---|---|
| `Salarié` | Informations personnelles et démographiques |
| `Info_Pro` | Contrats, ancienneté, promotions |
| `Rémunération` | Salaires et augmentations |

---

## 🛠 Préparation des données

### Respect du RGPD

- Suppression des données identifiantes :
  - Nom
  - Prénom
  - Téléphone
  - Identifiant salarié

- Généralisation des données sensibles :
  - Date de naissance → tranche d'âge
  - Distance domicile-travail → tranche de distance

- Normalisation :
  - Rémunérations converties en équivalent temps plein (EQTP)

- Imputation :
  - Valeurs manquantes d'augmentation remplacées par 0

---

## ⚙️ Workflow KNIME

Pipeline automatisé comprenant :

1. Importation des données
2. Préparation et nettoyage
3. Jointure des tables RH
4. Contrôles de cohérence
5. Anonymisation finale
6. Construction des indicateurs
7. Génération des graphiques
8. Export CSV pour analyses futures

---

## ✅ Compétences développées

| Compétence | Détail |
|---|---|
| RGPD | Anonymisation et protection des données personnelles |
| ETL | Préparation, transformation et intégration des données |
| KNIME | Construction d'un workflow automatisé |
| Qualité des données | Contrôles de cohérence et nettoyage |
| RH Analytics | Analyse des indicateurs sociaux |
| Reporting | Création d'un support décisionnel |

---

## 📊 Analyses & Résultats clés

### Analyse de la structure des effectifs

- Répartition femmes / hommes
- Répartition CDI / CDD
- Répartition temps plein / temps partiel

### Indicateurs de l'index égalité

| Indicateur | Score |
|---|---|
| Écart de rémunération | 36 / 40 |
| Écart d'augmentations | 10 / 20 |
| Écart de promotions | 15 / 15 |
| Hautes rémunérations | 5 / 10 |

### Constats

- Les promotions sont réparties équitablement.
- Les écarts de rémunération restent le principal axe de progression.
- Les femmes sont encore sous-représentées parmi les plus hautes rémunérations.
- L'entreprise dispose déjà d'une base solide mais peut améliorer son index.

---

## 📊 Illustration

![Aperçu — Projet 8](./apercu.png)

---

## 🗂 Structure du dossier

| Fichier / Dossier | Description |
|---|---|
| `enonce/` | Mission OpenClassrooms |
| `donnees/` | Données RH anonymisées |
| `livrables/` | Workflow KNIME · CSV final · Présentation |
| `apercu.png` | Diapositive de présentation |
| `README.md` | Présentation du projet |

---

## 🛠 Outils utilisés

- KNIME
- CSV
- Excel
- PowerPoint
- RGPD
- Data Preparation

---

## 📋 Recommandations stratégiques

- Réduire progressivement les écarts de rémunération.
- Garantir un accès équitable aux augmentations salariales.
- Favoriser l'accès des femmes aux postes les mieux rémunérés.
- Mettre en place un suivi annuel automatisé de l'index.
- Utiliser le workflow KNIME pour reproduire le diagnostic chaque année.

---

## 🚀 Valeur ajoutée du projet

Ce projet démontre la capacité à :

- traiter des données sensibles ;
- respecter les obligations réglementaires ;
- automatiser un processus métier ;
- produire des indicateurs RH exploitables ;
- transformer des données complexes en aide à la décision.

---

*Projet réalisé dans le cadre de la formation Data Analyst — OpenClassrooms (RNCP niveau 6)*
