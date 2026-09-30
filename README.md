# 📊 Analyse des ventes et prédiction du chiffre d'affaires

## 📌 Présentation du projet

Ce projet consiste à analyser les données de transactions d'une entreprise afin de comprendre ses performances commerciales et d'utiliser le Machine Learning pour prédire le chiffre d'affaires et identifier les ventes élevées.

Le projet couvre l'ensemble d'une démarche d'analyse de données :

**Préparation des données → Analyse exploratoire → Visualisation → Analyse business → Machine Learning → Interprétation des résultats**

L'objectif est de transformer les données de ventes en informations utiles à la compréhension de la performance commerciale.

---

## 🎯 Objectifs

- Explorer et préparer les données de ventes
- Contrôler la qualité et la cohérence des données
- Analyser le chiffre d'affaires et les performances commerciales
- Identifier les principaux facteurs associés au chiffre d'affaires
- Étudier les performances par produit, famille et zone géographique
- Analyser l'évolution des ventes
- Construire un modèle de régression pour prédire le chiffre d'affaires
- Construire un modèle de classification pour identifier les ventes élevées
- Évaluer les performances des modèles
- Interpréter les résultats avec une approche business

---

## 🗂️ Données

Le projet utilise trois sources de données :

| Fichier | Description |
|---|---|
| `transactions.csv` | Informations sur les transactions et les quantités vendues |
| `articles.csv` | Informations sur les articles, leur famille et leurs prix |
| `acheteurs.csv` | Informations sur les clients et leurs caractéristiques |

### Volume des données

- **120 transactions**
- **10 articles**
- **20 acheteurs**

---

## 🛠️ Technologies utilisées

- **SQL**
- **Python**
- **Pandas**
- **Matplotlib**
- **Scikit-learn**
- **Machine Learning**
- **Jupyter Notebook**
- **Git / GitHub**

---

## 🔄 Méthodologie

Le projet suit les principales étapes d'une démarche Data Analyst :

1. Importation et découverte des données
2. Nettoyage et contrôle de la qualité
3. Vérification des identifiants et des relations entre les tables
4. Transformation des données
5. Fusion des différentes sources
6. Calcul des indicateurs commerciaux
7. Analyse exploratoire
8. Visualisation des résultats
9. Identification des insights business
10. Construction des modèles de Machine Learning
11. Évaluation des modèles
12. Interprétation des résultats et formulation de recommandations

---

# 📈 Analyse business

L'analyse porte notamment sur :

- le chiffre d'affaires total ;
- les quantités vendues ;
- la marge ;
- le taux de marge ;
- la performance par famille de produits ;
- la performance par produit ;
- la performance géographique ;
- l'évolution du chiffre d'affaires.

### 💰 Principaux indicateurs

| Indicateur | Résultat |
|---|---:|
| Chiffre d'affaires total | **125,47 M** |
| Marge totale | **46,225 M** |
| Taux de marge | **36,84 %** |
| Nombre de transactions | **120** |
| Nombre d'acheteurs | **20** |
| Nombre d'articles | **10** |

### 🔎 Principaux insights

Les familles **Informatique** et **Électronique** représentent les principales contributions au chiffre d'affaires.

L'analyse permet également de comparer les performances entre les différentes familles de produits, les articles et les zones géographiques afin d'identifier les écarts de performance.

Le suivi conjoint du chiffre d'affaires et de la marge permet de distinguer les ventes générant du volume de celles contribuant réellement à la rentabilité.

---

# 🤖 Machine Learning

Deux problèmes de Machine Learning ont été étudiés :

1. **Régression** : prédire le chiffre d'affaires d'une transaction.
2. **Classification** : identifier les transactions correspondant à une vente élevée.

---

## 4. Régression

### 🎯 Objectif

Prédire le chiffre d'affaires d'une transaction à partir des variables :

- `quantite`
- `cout_unitaire`
- `prix_public`
- `Age`

Le jeu de données contient **120 observations**.

Les données sont séparées en :

- **96 observations d'entraînement**
- **24 observations de test**

Deux modèles sont comparés :

- Régression linéaire
- Random Forest Regressor

Les performances sont évaluées avec :

- MAE
- RMSE
- R²

### 📊 Résultats

| Modèle | MAE | RMSE | R² |
|---|---:|---:|---:|
| Régression linéaire | 385 889 | 553 446 | **0,823** |
| Random Forest Regressor | **172 571** | **304 016** | **0,946** |

Le Random Forest obtient sur l'échantillon de test une erreur absolue moyenne et une erreur quadratique moyenne plus faibles, ainsi qu'un R² plus élevé que la régression linéaire.

Il explique environ **94,6 % de la variabilité du chiffre d'affaires observée sur les données de test**.

Ces résultats doivent toutefois être interprétés dans le contexte du jeu de données et de la construction des variables.

---

# 🎯 Classification

### Objectif

L'objectif est d'identifier si une transaction correspond à une **vente élevée** ou à une **vente non élevée**.

La variable cible `vente_elevee` est créée à partir de la médiane du chiffre d'affaires.

### Seuil utilisé

**660 000**

Une transaction est considérée comme une vente élevée lorsque :

```text
CA >= 660 000
