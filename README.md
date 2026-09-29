# 📊 Analyse des ventes et prédiction du chiffre d'affaires

## Présentation du projet

Ce projet consiste à analyser les données de transactions d'une entreprise afin de comprendre ses performances commerciales et d'utiliser le Machine Learning pour prédire le chiffre d'affaires et identifier les ventes élevées.

Le projet couvre l'ensemble de la démarche d'analyse de données : préparation des données, analyse exploratoire, visualisation, analyse business, modélisation et évaluation des modèles.

---

## 🎯 Objectifs

- Explorer et préparer les données de ventes
- Analyser le chiffre d'affaires et les performances commerciales
- Identifier les principaux facteurs associés au chiffre d'affaires
- Construire un modèle de régression pour prédire le CA
- Construire un modèle de classification pour identifier les ventes élevées
- Évaluer et interpréter les performances des modèles

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

- SQL
- Python
- Pandas
- Matplotlib
- Scikit-learn
- Machine Learning

---

## 🔄 Méthodologie

Le projet suit les principales étapes d'une démarche Data Analyst :

1. Importation et découverte des données
2. Nettoyage et contrôle de la qualité
3. Vérification des identifiants et de l'intégrité des relations
4. Transformation et fusion des données
5. Calcul du chiffre d'affaires et des indicateurs commerciaux
6. Analyse exploratoire
7. Visualisation des résultats
8. Identification des insights business
9. Construction des modèles de Machine Learning
10. Évaluation et interprétation des modèles

---

## 📈 Principaux résultats business

L'analyse porte notamment sur :

- le chiffre d'affaires total ;
- les quantités vendues ;
- la marge et le taux de marge ;
- la performance par famille de produits ;
- la performance par produit ;
- la performance géographique ;
- l'évolution du chiffre d'affaires dans le temps.

Le chiffre d'affaires total réalisé sur les 120 transactions est de **125,47 M**.

La marge totale s'élève à **46,225 M**, soit un taux de marge global de **36,84 %**.

Les familles **Informatique** et **Électronique** représentent les principales contributions au chiffre d'affaires.

---

## 🤖 Machine Learning

Deux types de modèles ont été développés.

### Régression

L'objectif est de prédire le chiffre d'affaires d'une transaction.

Deux modèles ont été comparés :

| Modèle | MAE | RMSE | R² |
|---|---:|---:|---:|
| Régression linéaire | 385 889 | 553 446 | 0,823 |
| Random Forest | 172 571 | 304 016 | 0,946 |

### Classification

L'objectif est d'identifier les ventes élevées à partir d'un seuil correspondant à la médiane du CA, soit **660 000**.

Deux modèles ont été évalués :

- Régression logistique : **83,33 % d'accuracy**
- Random Forest : **100 % d'accuracy sur l'échantillon de test**

Les résultats de classification doivent toutefois être interprétés avec prudence, car la variable cible est construite à partir du chiffre d'affaires et certaines variables explicatives sont directement liées à son calcul.

---

## ⚠️ Limites du projet

Plusieurs limites doivent être prises en compte :

- le jeu de données contient seulement 120 transactions ;
- le chiffre d'affaires est directement calculé à partir de la quantité et du prix public ;
- certaines variables utilisées par les modèles sont donc directement liées à la variable cible ;
- les données ne contiennent pas certaines informations pouvant expliquer les ventes, comme les promotions, le stock ou les actions marketing ;
- les modèles ont été évalués sur une seule séparation entraînement/test.

Les performances obtenues constituent donc principalement une **preuve de concept**.

---

## 🚀 Perspectives d'amélioration

Pour aller plus loin :

- utiliser un volume de données plus important ;
- intégrer davantage de variables explicatives ;
- éviter les variables directement liées à la construction de la cible ;
- utiliser la validation croisée ;
- optimiser les hyperparamètres ;
- tester d'autres algorithmes ;
- développer des prédictions sur de futures périodes.

---

## 📓 Notebook

Le détail de l'analyse, du nettoyage des données, des visualisations et des modèles est disponible dans :

`Portfolio_Analyse_Ventes_ML.ipynb`