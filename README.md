# titanic-survival-rate
## Quels types de personnes avaient le plus de chances de survivre ?


Juillet 2024

Pour que les script ai accès aux variables d'environnement (identifiants de connexion), il faut :  
- Le fichier .env
- Installer Le package dotenv
- Appeler .env dans db.py

## Table des matières de la Veille

- [Explorez différents types de fractales](#explorez-différents-types-de-fractales)
  - [Apprentissage automatique supervisé](#table-des-matières)
  - [Données étiquetées](#léquipe)
  - [Classification supervisée](#fractales)
  - [Modèle](#contexte)
  - [Données d’entraînement](#formes-autosimilaire)
  - [Cible](#triangle-de-sierpiński)
  - [Phase d’entraînement](#mandelbrot)
  - [Phase de prédiction](#julia)
  - [Prétraitement des données](#flocon-de-neige-de-koch) 
  - [Evaluation d’un modèle d’apprentissage automatique](#burning-ship) 
  - [AutoML](#triangle-de-sierpiński)
  - [Arbre de décision](#mandelbrot)



### Qu’est ce que l’apprentissage automatique supervisé ?

L’apprentissage automatique supervisé est une méthode de machine learning où un modèle est entraîné sur des données étiquetées. Cela signifie que chaque exemple d’entraînement est associé à une sortie correcte. Le modèle apprend à partir de ces exemples pour prédire les résultats sur de nouvelles données.

### Qu’est ce que les données étiquetées ?

Les données étiquetées sont des données d’entraînement qui incluent des entrées et des sorties correctes. Chaque exemple de données est associé à une étiquette ou un label qui indique la réponse correcte que le modèle doit apprendre à prédire.

### En particulier, qu’est ce que la classification supervisée ?

La classification supervisée est une tâche d’apprentissage supervisé où le modèle apprend à attribuer des catégories ou des labels à de nouvelles données en se basant sur des exemples d’entraînement étiquetés. Par exemple, classer des emails comme spam ou non-spam.

### Qu’est ce qu’on appelle un modèle d’apprentissage automatique ?

Un modèle d’apprentissage automatique est une fonction ou un algorithme qui a été entraîné sur des données pour effectuer des prédictions ou des classifications. Il utilise les informations apprises pendant l’entraînement pour faire des prédictions sur de nouvelles données.

### Qu’est ce que les données d’entraînement ? Qu’est ce que l’entraînement d’un modèle de classification supervisée ?

Les données d’entraînement sont des exemples étiquetés utilisés pour apprendre au modèle. L’entraînement d’un modèle de classification supervisée consiste à ajuster les paramètres du modèle pour minimiser l’erreur entre les prédictions du modèle et les étiquettes correctes des données d’entraînement.

### Qu’est ce que la donnée cible ?

La donnée cible, ou target, est la sortie correcte associée à chaque exemple d’entraînement. C’est ce que le modèle essaie de prédire.

### A quoi sert la phase d’entraînement d’un modèle d’apprentissage automatique ?

La phase d’entraînement permet au modèle d’apprendre les relations entre les entrées et les sorties dans les données d’entraînement. Le modèle ajuste ses paramètres pour minimiser l’erreur de prédiction.

### A quoi sert la phase de prédiction d’un modèle d’apprentissage automatique ?

La phase de prédiction utilise le modèle entraîné pour faire des prédictions sur de nouvelles données non étiquetées. Le modèle applique ce qu’il a appris pendant l’entraînement pour prédire les sorties.

### Qu’est ce que le prétraitement des données et pourquoi est-il important à réaliser avant l’entraînement d’un modèle d’apprentissage automatique ?

Le prétraitement des données consiste à nettoyer et transformer les données brutes en un format approprié pour l’entraînement du modèle. Cela peut inclure la normalisation, la gestion des valeurs manquantes et la transformation des variables catégorielles. Le prétraitement est crucial car des données de mauvaise qualité peuvent entraîner des modèles inefficaces.

### Comment l’évaluation d’un modèle d’apprentissage automatique pour une tâche de classification peut-elle se faire ? Etudiez en particulier et seulement, la métrique d’accuracy. En quoi est-elle un indicateur de performance d’un modèle ?

L’évaluation d’un modèle de classification peut se faire en utilisant diverses métriques, dont l’accuracy (précision). L’accuracy est le pourcentage de prédictions correctes faites par le modèle sur un ensemble de test. C’est un indicateur de performance car il montre la proportion de prédictions correctes par rapport au total des prédictions.

### Qu’est ce que l’AutoML et pourquoi est-il pertinent pour vous en tant que débutant dans le domaine de l’intelligence artificielle ?

L’AutoML (Automated Machine Learning) est un ensemble de techniques qui automatisent les étapes du processus de machine learning, comme la sélection des modèles, le prétraitement des données et l’optimisation des hyperparamètres. Pour un débutant, AutoML est pertinent car il simplifie le processus de création de modèles performants sans nécessiter une expertise approfondie en machine learning.

### Qu’est ce qu’un arbre de décision pour la classification supervisée ? Comment fonctionne–t-il ?

Un arbre de décision est un modèle de classification qui divise les données en sous-ensembles basés sur des tests de valeurs de caractéristiques. Chaque nœud de l’arbre représente une caractéristique, chaque branche représente un résultat de test, et chaque feuille représente une classe ou une étiquette. L’arbre de décision fonctionne en parcourant les nœuds de l’arbre pour prendre des décisions basées sur les caractéristiques des données d’entrée.