📊 Analyse des ventes et prédiction du chiffre d’affaires
Présentation du projet
Ce projet consiste à analyser les transactions d’une entreprise afin de comprendre ses performances commerciales, d’identifier les principaux contributeurs au chiffre d’affaires et d’explorer l’utilisation du Machine Learning pour estimer le chiffre d’affaires et classer les ventes élevées.
L’étude suit une démarche de Data Analyst : compréhension des données, contrôle qualité, préparation, analyse exploratoire, visualisation, interprétation métier et modélisation.
🎯 Objectifs
Explorer et contrôler la qualité des données commerciales.
Relier les données de transactions, d’articles et d’acheteurs.
Calculer et analyser le chiffre d’affaires et la marge.
Comparer les performances par famille de produits et par zone géographique.
Étudier les facteurs associés au chiffre d’affaires.
Construire et comparer des modèles de régression et de classification.
Interpréter les résultats, leurs limites et les pistes d’amélioration.
🗂️ Contenu du dépôt
```text
Portfolio_Analyse_Ventes_ML/
├── data/
│   ├── transactions.csv
│   ├── articles.csv
│   └── acheteurs.csv
├── Portfolio_Analyse_Ventes_ML.ipynb
└── README.md
```
Sources de données
Fichier	Contenu
`transactions.csv`	Identifiant et date de transaction, identifiants de l’acheteur et de l’article, quantité vendue
`articles.csv`	Identifiant, désignation, famille, coût unitaire et prix public des articles
`acheteurs.csv`	Identifiant, nom, prénom, ville, date de naissance et date d’adhésion
Volume étudié
120 transactions
10 articles
20 acheteurs
🛠️ Outils et technologies
SQL : travail de consultation et d’analyse des données
Python : traitement et analyse
Pandas : manipulation et préparation des données
Matplotlib : visualisation
Scikit-learn : construction et évaluation des modèles
Jupyter Notebook : environnement d’analyse
Git et GitHub : versionnement et présentation du projet
🔄 Démarche suivie
Importation et découverte des trois fichiers.
Vérification des dimensions, des types et de la qualité des données.
Contrôle des valeurs manquantes, des doublons et de l’unicité des identifiants.
Vérification de l’intégrité des relations entre transactions, articles et acheteurs.
Conversion des dates et fusion des sources.
Création des indicateurs de chiffre d’affaires et de marge.
Analyse exploratoire par famille, produit, ville et période.
Visualisation et interprétation des résultats.
Construction et comparaison de modèles de Machine Learning.
Formulation d’insights, de recommandations et de limites.
🧹 Qualité et préparation des données
Les contrôles réalisés dans le notebook indiquent :
aucune valeur manquante détectée dans les trois tables ;
aucun doublon détecté ;
identifiants uniques dans leurs tables respectives ;
aucune transaction orpheline : chaque transaction est reliée à un acheteur et à un article existant ;
dates converties au format datetime.
Après fusion, la table d’analyse contient 120 transactions et 18 variables.
📈 Résultats de l’analyse commerciale
Le chiffre d’affaires d’une transaction est calculé ainsi :
Chiffre d’affaires = Quantité × Prix public
La marge est calculée ainsi :
Marge = Quantité × (Prix public − Coût unitaire)
Indicateurs clés
Indicateur	Résultat
Chiffre d’affaires total	125 470 000
Marge totale	46 225 000
Taux de marge global	36,84 %
Quantités vendues	438
Nombre de transactions	120
Nombre d’acheteurs	20
Nombre d’articles	10
Chiffre d’affaires par famille
Famille	Chiffre d’affaires
Informatique	57 910 000
Électronique	48 860 000
Téléphonie	10 110 000
Audio	8 590 000
Les familles Informatique et Électronique représentent ensemble environ 85 % du chiffre d’affaires. Elles constituent les principales contributions à l’activité observée dans ce jeu de données.
L’analyse géographique met en évidence des volumes d’activité différents selon les villes. Bamako, Abidjan et Conakry concentrent l’essentiel des transactions, tandis que Dakar ne représente que 2 transactions et 4 unités vendues dans le jeu de données. Cette différence doit être interprétée en tenant compte du faible volume d’observations pour cette ville.
🤖 Machine Learning
Deux tâches ont été étudiées : la prédiction du chiffre d’affaires (régression) et l’identification des ventes élevées (classification).
1. Régression : prédire le chiffre d’affaires
La cible est le chiffre d’affaires d’une transaction. Les variables explicatives utilisées sont `quantite`, `cout_unitaire`, `prix_public` et `Age`.
Les données ont été séparées en 96 observations d’entraînement et 24 observations de test.
Modèle	MAE	RMSE	R²
Régression linéaire	385 889	553 446	0,823
Random Forest Regressor	172 571	304 016	0,946
Sur ce découpage, le Random Forest obtient des erreurs plus faibles et un R² plus élevé que la régression linéaire. Il fournit donc les meilleurs résultats parmi les deux modèles testés.
Importance des variables — régression
Variable	Importance
Quantité	38,13 %
Coût unitaire	30,24 %
Prix public	28,75 %
Âge	2,88 %
La quantité et les variables de prix sont les plus importantes dans ce modèle. Cette observation doit être lue à la lumière de la formule de calcul du chiffre d’affaires.
2. Classification : identifier les ventes élevées
La variable cible `vente_elevee` est définie à partir de la médiane du chiffre d’affaires :
Vente élevée (1) : CA supérieur ou égal à 660 000.
Vente non élevée (0) : CA inférieur à 660 000.
La cible comprend 62 ventes élevées et 58 ventes non élevées. Les données sont séparées en 96 observations d’entraînement et 24 observations de test, avec une séparation stratifiée.
Modèle	Accuracy	Precision	Recall	F1-score
Régression logistique	83,33 %	83,33 %	83,33 %	83,33 %
Random Forest Classifier	100 %	100 %	100 %	100 %
Le Random Forest a correctement classé les 24 observations de test dans cette expérience. Ce résultat parfait ne doit toutefois pas être interprété comme une garantie de performance sur de nouvelles données.
Importance des variables — classification
Variable	Importance
Quantité	59,57 %
Coût unitaire	17,54 %
Prix public	15,61 %
Âge	7,28 %
💡 Insights et recommandations métier
Suivre les familles les plus contributrices : surveiller régulièrement les ventes et les marges des familles Informatique et Électronique.
Analyser les écarts géographiques : approfondir les différences de volumes entre les villes, en particulier les faibles volumes observés à Dakar.
Suivre la rentabilité en plus du chiffre d’affaires : utiliser conjointement le CA, la marge et le taux de marge pour évaluer la performance.
Enrichir les données : intégrer, si elles sont disponibles, les promotions, remises, niveaux de stock, campagnes marketing et davantage d’historique.
Renforcer l’évaluation prédictive : tester une validation croisée et évaluer les modèles sur des données plus nombreuses et représentatives.
⚠️ Limites de l’étude
Les résultats doivent être interprétés en tenant compte de plusieurs limites :
Le jeu de données ne contient que 120 transactions, ce qui limite la généralisation des observations.
Le chiffre d’affaires est calculé à partir de la quantité et du prix public. Ces variables sont également utilisées comme prédicteurs dans le modèle de régression : la relation mathématique directe peut rendre l’exercice de prédiction peu représentatif d’un scénario réel.
La cible de classification `vente_elevee` est dérivée du chiffre d’affaires, alors que la quantité et le prix public sont utilisés comme variables explicatives. Cette proximité entre les prédicteurs et la cible peut expliquer une partie des performances élevées et constitue un risque de fuite d’information (data leakage).
Les résultats sont calculés sur un seul découpage entraînement/test de 80 % / 20 %. Une validation croisée et un jeu de données externe seraient nécessaires pour mieux évaluer la capacité de généralisation.
Les scores obtenus sont donc à considérer comme des résultats expérimentaux sur ce jeu de données, et non comme une garantie de performance en production.
🏁 Conclusion
Ce projet m’a permis de mettre en pratique une démarche complète d’analyse de données : contrôle qualité, préparation et fusion de plusieurs sources, calcul d’indicateurs, analyse exploratoire, visualisation, interprétation métier et modélisation avec Scikit-learn.
L’analyse commerciale met en évidence le poids des familles Informatique et Électronique dans le chiffre d’affaires, ainsi que des différences de volume entre les villes. La comparaison des modèles montre que le Random Forest obtient les meilleurs scores sur les échantillons de test utilisés.
J’ai également identifié une limite méthodologique importante : certaines variables explicatives sont directement liées à la construction des variables cibles. La prise en compte de ce risque de fuite d’information est essentielle pour interpréter les performances avec recul et concevoir une évaluation plus réaliste.
Ce travail constitue une preuve de concept et une mise en pratique de compétences en analyse de données et en Machine Learning. Une suite pertinente serait d’enrichir le jeu de données, de revoir la sélection des variables selon le contexte de prédiction et de valider les modèles sur de nouvelles observations.
---
Projet réalisé dans le cadre d’un parcours de formation Data Analyst et Intelligence Artificielle.
