# Projet 6 — Optimisation de la gestion des données d'une boutique

[← Retour au portfolio](./README.md)

---

## Contexte

**Client fictif :** BottleNeck, marchand de vin prestigieux
**Rôle joué :** Data Analyst missionnée par le manager Nicolas
**Durée estimée :** 70 heures
**Statut :** ✅ Validé

BottleNeck gère ses données via des outils artisanaux et des exports multiples non reliés entre eux : un ERP, un site web WooCommerce (YSKU), et une table de liaison. Les références produits ne correspondent pas entre les deux systèmes. La mission : agréger ces fichiers, détecter les erreurs, analyser les données, et recommander une migration vers un ERP unifié.

---

## Problématique

> Comment fiabiliser et exploiter des données dispersées dans plusieurs systèmes hétérogènes pour produire des analyses décisionnelles ?

---

## Livrables produits

- 📓 **Notebook Python** — traitement complet des données (nettoyage, jointures, analyses)
- 📊 **Présentation CODIR** — synthèse des analyses pour l'équipe de direction

---

## Méthodologie

### Phase 1 — Préparation et nettoyage des données

**Sources de données :**
- `erp.xlsx` : référence produit, prix, état du stock
- `web.xlsx` : données WooCommerce (SKU, ventes, descriptions)
- `liaison.xlsx` : table de correspondance des références entre les deux systèmes

**Traitement réalisé :**

1. **Analyse exploratoire de chaque fichier** avant toute jointure
2. **Détection et traitement des incohérences dans l'ERP :**
   - Incohérences entre `stock_status` et `stock_quantity` (produits marqués *instock* avec quantité nulle, et inversement)
   - Création d'une colonne `stock_status_2` recalculée depuis `stock_quantity` pour identifier les 4 lignes problématiques
   - Prix négatifs isolés dans un DataFrame d'incohérences
   - Isolation des données propres dans `df_erp_clean`
3. **Nettoyage du fichier WEB :**
   - Suppression de 23 colonnes non pertinentes (colonnes à zéro, métadonnées WordPress)
   - Vérification des types de données sur la colonne `sku`
4. **Jointure des fichiers** via la table de liaison pour créer un dataset unifié `df_merge`
5. **Conformité RGPD :** vérification et traitement des données personnelles ou sensibles

**Bilan nettoyage : 8+ erreurs identifiées** (erreurs de saisie, de type, de calcul, d'incohérence logique)

---

### Phase 2 — Analyses pour le CODIR

#### 📈 Chiffre d'affaires
- CA calculé par produit et en total général
- Analyse des tops références (règle 20/80)

#### 📦 Analyse des stocks
- Calcul du nombre de mois de stock par produit
- Valorisation du stock par catégorie (visualisation en bullet chart)
- Rotation moyenne des stocks
- Détection de valeurs aberrantes sur les prix (boxplot + Z-score)

#### 💰 Analyse des marges
- Calcul du prix HT (TVA 20%)
- Taux de marge = `(Prix HT - Prix d'achat) / Prix d'achat`
- Taux de marge minimum et maximum identifiés
- Visualisation du taux de marge moyen par type de produit (graphique barres avec palette RdYlGn)
- Identification d'un produit vendu à perte (taux de marge négatif)

#### 🔗 Analyse de corrélation
- Heatmap de corrélation (seaborn) entre : `stock_quantity`, `total_sales`, `price`, `purchase_price`, `taux_marge`
- Identification des relations entre variables quantitatives

---

## Outils utilisés

| Outil | Usage |
|-------|-------|
| Python | Langage principal |
| pandas | Manipulation et nettoyage des données |
| plotly | Visualisations interactives (bullet chart, barres) |
| matplotlib | Visualisations statiques |
| seaborn | Heatmap de corrélation |
| Jupyter Notebook | Environnement de développement |
| openpyxl | Lecture/écriture des fichiers Excel |

---

## Compétences démontrées

- ✅ Pré-traiter des données pour explorer et comprendre leurs caractéristiques
- ✅ Traiter et nettoyer des données en définissant la gestion des incohérences en conformité du RGPD
- ✅ Effectuer des analyses univariées et multivariées des données pré-traitées
- ✅ Identifier les besoins métier et formuler des recommandations

---

## Difficultés rencontrées & apprentissages

- **Jointure multi-sources :** les références ne correspondent pas entre l'ERP et le WEB → nécessité d'une table de liaison et d'une vérification rigoureuse des types de données avant la jointure
- **Décisions de nettoyage :** face aux données incohérentes, choix de les isoler dans un DataFrame séparé plutôt que de les supprimer, pour garder la traçabilité et permettre la correction en amont dans les systèmes source
- **Communication CODIR :** adapter la présentation technique à un public non-data, en restant synthétique et orienté décision

---

## Recommandations formulées

- Mise en place d'un ERP unifié pour éliminer les doublons de référencement
- Automatisation de la mise à jour du `stock_status` en fonction du `stock_quantity`
- Procédure de validation des prix avant saisie (blocage des valeurs négatives)
- Audit régulier des marges par type de produit

---

[← Retour au portfolio](./README.md)
