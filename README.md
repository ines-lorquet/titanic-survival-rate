# titanic-survival-rate
## Quels types de personnes avaient le plus de chances de survivre ?


Juillet 2024

## Table des matières

- [Contexte du projet](#Contexte)
- [Veille](#Veille)
  - [Apprentissage automatique supervisé](#apprentissage-automatique-supervisé)
  - [Données étiquetées](#données-étiquetées)
  - [Classification supervisée](#classification-supervisée)
  - [Modèle](#modèle)
  - [Données d’entraînement](#données-dentraînement)
  - [Cible](#cible)
  - [Phase d’entraînement](#phase-dentraînement)
  - [Phase de prédiction](#phase-de-prédiction)
  - [Prétraitement des données](#prétraitement-des-données) 
  - [Evaluation d’un modèle d’apprentissage automatique](#valuation-dun-modèle-dapprentissage-automatique) 
  - [AutoML](#AutoML)
  - [Arbre de décision](#arbre-de-décision)
- [Données](#Données)
- [Analyse](#Analyse)
- [Algorithmes utilisés](#Algorithmes)
- [Conclusion](#Conclusion)

## Contexte
Travail en équipe de 3 étudiants en 1ère année de `Bachelor IT spécialité Intelligence Artificielle` à [La Plateforme_](https://laplateforme.io/) à Marseille

- Said Kheloufi
  <a href="https://www.linkedin.com/in/said-kheloufi/">
    <img src="img/linkedin.png" width=25>
  </a>
  <a href="https://github.com/said-kheloufi">
    <img src="img/github.png" width=25>
  </a>

- Ines Lorquet
  <a href="https://www.linkedin.com/in/ines-lorquet-35b90128b/">
    <img src="img/linkedin.png" width=25>
  </a>
  <a href="https://github.com/ines-lorquet">
    <img src="img/github.png" width=25>
  </a>

- Bruno Coulet
  <a href="https://www.linkedin.com/in/bruno-coulet-35b90128b/">
    <img src="img/linkedin.png" width=25>
  </a>
  <a href="https://github.com/bruno-coulet">
    <img src="img/github.png" width=25>
  </a>

A partir d'un dataset sur les passagers du titanic en .csv, il est demandé de réaliser une analyse exploratoire complète dans le but de répondre aux questions suivantes :  
a) Qui étaient les survivants du naufrage du Titanic ?  
b) Qui étaient les victimes du naufrage du Titanic ?  

Il faut ensuite :
- Entraîner et comparer des modèles de classification.
- Faire un tableau de performances des modèles entraînés et interprétez ce tableau.
- Afficher le meilleur modèle entraîné et identifié par Pycaret.

## Veille
### Apprentissage automatique supervisé
#### Qu’est ce que l’apprentissage automatique supervisé ?

L’apprentissage automatique supervisé est une méthode de machine learning où un modèle est entraîné sur des données étiquetées. Cela signifie que chaque exemple d’entraînement est associé à une sortie correcte. Le modèle apprend à partir de ces exemples pour prédire les résultats sur de nouvelles données.

### Données étiquetées
#### Qu’est ce que les données étiquetées ?

Les données étiquetées sont des données d’entraînement qui incluent des entrées et des sorties correctes. Chaque exemple de données est associé à une étiquette ou un label qui indique la réponse correcte que le modèle doit apprendre à prédire.

### Classification supervisée
#### En particulier, qu’est ce que la classification supervisée ?

La classification supervisée est une tâche d’apprentissage supervisé où le modèle apprend à attribuer des catégories ou des labels à de nouvelles données en se basant sur des exemples d’entraînement étiquetés. Par exemple, classer des emails comme spam ou non-spam.

### Modèle
#### Qu’est ce qu’on appelle un modèle d’apprentissage automatique ?

Un modèle d’apprentissage automatique est une fonction ou un algorithme qui a été entraîné sur des données pour effectuer des prédictions ou des classifications. Il utilise les informations apprises pendant l’entraînement pour faire des prédictions sur de nouvelles données.

### Données d’entraînement
#### Qu’est ce que les données d’entraînement ? Qu’est ce que l’entraînement d’un modèle de classification supervisée ?

Les données d’entraînement sont des exemples étiquetés utilisés pour apprendre au modèle. L’entraînement d’un modèle de classification supervisée consiste à ajuster les paramètres du modèle pour minimiser l’erreur entre les prédictions du modèle et les étiquettes correctes des données d’entraînement.

### Cible
#### Qu’est ce que la donnée cible ?

La donnée cible, ou target, est la sortie correcte associée à chaque exemple d’entraînement. C’est ce que le modèle essaie de prédire.

### Phase d’entraînement
#### A quoi sert la phase d’entraînement d’un modèle d’apprentissage automatique ?

La phase d’entraînement permet au modèle d’apprendre les relations entre les entrées et les sorties dans les données d’entraînement. Le modèle ajuste ses paramètres pour minimiser l’erreur de prédiction.

### Phase de prédiction
#### A quoi sert la phase de prédiction d’un modèle d’apprentissage automatique ?

La phase de prédiction utilise le modèle entraîné pour faire des prédictions sur de nouvelles données non étiquetées. Le modèle applique ce qu’il a appris pendant l’entraînement pour prédire les sorties.

### Prétraitement des données
#### Qu’est ce que le prétraitement des données et pourquoi est-il important à réaliser avant l’entraînement d’un modèle d’apprentissage automatique ?

Le prétraitement des données consiste à nettoyer et transformer les données brutes en un format approprié pour l’entraînement du modèle. Cela peut inclure la normalisation, la gestion des valeurs manquantes et la transformation des variables catégorielles. Le prétraitement est crucial car des données de mauvaise qualité peuvent entraîner des modèles inefficaces.

### Evaluation d’un modèle d’apprentissage automatique
#### Comment l’évaluation d’un modèle d’apprentissage automatique pour une tâche de classification peut-elle se faire ? Etudiez en particulier et seulement, la métrique d’accuracy. En quoi est-elle un indicateur de performance d’un modèle ?

L’évaluation d’un modèle de classification peut se faire en utilisant diverses métriques, dont l’accuracy (précision). L’accuracy est le pourcentage de prédictions correctes faites par le modèle sur un ensemble de test. C’est un indicateur de performance car il montre la proportion de prédictions correctes par rapport au total des prédictions.

### AutoML
#### Qu’est ce que l’AutoML et pourquoi est-il pertinent pour vous en tant que débutant dans le domaine de l’intelligence artificielle ?

L’AutoML (Automated Machine Learning) est un ensemble de techniques qui automatisent les étapes du processus de machine learning, comme la sélection des modèles, le prétraitement des données et l’optimisation des hyperparamètres. Pour un débutant, AutoML est pertinent car il simplifie le processus de création de modèles performants sans nécessiter une expertise approfondie en machine learning.

### Arbre de décision
#### Qu’est ce qu’un arbre de décision pour la classification supervisée ? Comment fonctionne–t-il ?

Un arbre de décision est un modèle de classification qui divise les données en sous-ensembles basés sur des tests de valeurs de caractéristiques. Chaque nœud de l’arbre représente une caractéristique, chaque branche représente un résultat de test, et chaque feuille représente une classe ou une étiquette. L’arbre de décision fonctionne en parcourant les nœuds de l’arbre pour prendre des décisions basées sur les caractéristiques des données d’entrée.


## Données
Un jeux de donnée au format .csv est fourni [ici](https://drive.google.com/file/d/11n_iJwyFsL4iFZBKVfnwLIBsvrmGrGzT/view)  
Ainsi qu'un descriptif du dataset [ici](https://drive.google.com/file/d/1ZmUYA_v-x0YG927_XiQI0lm4_504hkgc/view)  

Il s'agit d'une liste de 891 passagers contenant les informations suivantes :  

- survivant/décédé
- classe d'embarquement (1,2 ou 3)
- état civil
- sexe
- âge
- présence à bord de frères/soeur ou non
- présence à bord de parent/enfant ou non
- numéro de ticket
- prix du ticket
- numéro de cabine
- port d'embarquement

Le dataset est incomplet, il manque certain âge et de nombreux numéro de cabine.  
En outre, l'énoncé nous informe que le naufrage du titanic à entraîné la mort de 1502 des 2224 passagers et
membres d'équipage.

## Analyse
## Algorithmes
## Conclusion