# titanic-survival-rate
## Quels types de personnes avaient le plus de chances de survivre ?


Juillet 2024

## Table des matières de la Veille

- [Contexte du projet](#Contexte)
- [Download requirements](#download-requirements)
- [Veille](#veille)
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

A partir d'un [dataset sur les passagers du titanic](https://drive.google.com/file/d/11n_iJwyFsL4iFZBKVfnwLIBsvrmGrGzT/view) en .csv et d'une [description du dataset](https://drive.google.com/file/d/1ZmUYA_v-x0YG927_XiQI0lm4_504hkgc/view) en .txt, il est demandé de réaliser une analyse exploratoire complète dans le but de répondre aux questions suivantes :  
a) Qui étaient les survivants du naufrage du Titanic ?  
b) Qui étaient les victimes du naufrage du Titanic ?  

Il faut ensuite :
- Entraîner et comparer des modèles de classification.
- Faire un tableau de performances des modèles entraînés et interprétez ce tableau.
- Afficher le meilleur modèle entraîné et identifié par Pycaret.
## Download requirements
Installer les bibliothèques nécessaire pour le bon fonctionnemeent du projet :
```sh
pip install -r requirements.txt
```  

## Veille
## Apprentissage automatique supervisé
### Qu’est ce que l’apprentissage automatique supervisé ?

L’apprentissage automatique supervisé est une méthode de machine learning où un modèle est entraîné sur des données étiquetées. Cela signifie que chaque exemple d’entraînement est associé à une sortie correcte. Le modèle apprend à partir de ces exemples pour prédire les résultats sur de nouvelles données.

## Données étiquetées
### Qu’est ce que les données étiquetées ?

Les données étiquetées sont des données d’entraînement qui incluent des entrées et des sorties correctes. Chaque exemple de données est associé à une étiquette ou un label qui indique la réponse correcte que le modèle doit apprendre à prédire.

## Classification supervisée
### En particulier, qu’est ce que la classification supervisée ?

La classification supervisée est une tâche d’apprentissage supervisé où le modèle apprend à attribuer des catégories ou des labels à de nouvelles données en se basant sur des exemples d’entraînement étiquetés. Par exemple, classer des emails comme spam ou non-spam.

## Modèle
### Qu’est ce qu’on appelle un modèle d’apprentissage automatique ?

Un modèle d’apprentissage automatique est une fonction ou un algorithme qui a été entraîné sur des données pour effectuer des prédictions ou des classifications. Il utilise les informations apprises pendant l’entraînement pour faire des prédictions sur de nouvelles données.

## Données d’entraînement
### Qu’est ce que les données d’entraînement ? Qu’est ce que l’entraînement d’un modèle de classification supervisée ?

Les données d’entraînement sont des exemples étiquetés utilisés pour apprendre au modèle. L’entraînement d’un modèle de classification supervisée consiste à ajuster les paramètres du modèle pour minimiser l’erreur entre les prédictions du modèle et les étiquettes correctes des données d’entraînement.

## Cible
### Qu’est ce que la donnée cible ?

La donnée cible, ou target, est la sortie correcte associée à chaque exemple d’entraînement. C’est ce que le modèle essaie de prédire.

## Phase d’entraînement
### A quoi sert la phase d’entraînement d’un modèle d’apprentissage automatique ?

La phase d’entraînement permet au modèle d’apprendre les relations entre les entrées et les sorties dans les données d’entraînement. Le modèle ajuste ses paramètres pour minimiser l’erreur de prédiction.

## Phase de prédiction
### A quoi sert la phase de prédiction d’un modèle d’apprentissage automatique ?

La phase de prédiction utilise le modèle entraîné pour faire des prédictions sur de nouvelles données non étiquetées. Le modèle applique ce qu’il a appris pendant l’entraînement pour prédire les sorties.

## Prétraitement des données
### Qu’est ce que le prétraitement des données et pourquoi est-il important à réaliser avant l’entraînement d’un modèle d’apprentissage automatique ?

Le prétraitement des données consiste à nettoyer et transformer les données brutes en un format approprié pour l’entraînement du modèle. Cela peut inclure la normalisation, la gestion des valeurs manquantes et la transformation des variables catégorielles. Le prétraitement est crucial car des données de mauvaise qualité peuvent entraîner des modèles inefficaces.

## Evaluation d’un modèle d’apprentissage automatique
### Comment l’évaluation d’un modèle d’apprentissage automatique pour une tâche de classification peut-elle se faire ? Etudiez en particulier et seulement, la métrique d’accuracy. En quoi est-elle un indicateur de performance d’un modèle ?

L’évaluation d’un modèle de classification peut se faire en utilisant diverses métriques, dont l’accuracy (précision). L’accuracy est le pourcentage de prédictions correctes faites par le modèle sur un ensemble de test. C’est un indicateur de performance car il montre la proportion de prédictions correctes par rapport au total des prédictions.

## AutoML
### Qu’est ce que l’AutoML et pourquoi est-il pertinent pour vous en tant que débutant dans le domaine de l’intelligence artificielle ?

L’AutoML (Automated Machine Learning) est un ensemble de techniques qui automatisent les étapes du processus de machine learning, comme la sélection des modèles, le prétraitement des données et l’optimisation des hyperparamètres. Pour un débutant, AutoML est pertinent car il simplifie le processus de création de modèles performants sans nécessiter une expertise approfondie en machine learning.

## Arbre de décision
### Qu’est ce qu’un arbre de décision pour la classification supervisée ? Comment fonctionne–t-il ?

Un arbre de décision est un modèle de classification qui divise les données en sous-ensembles basés sur des tests de valeurs de caractéristiques. Chaque nœud de l’arbre représente une caractéristique, chaque branche représente un résultat de test, et chaque feuille représente une classe ou une étiquette. L’arbre de décision fonctionne en parcourant les nœuds de l’arbre pour prendre des décisions basées sur les caractéristiques des données d’entrée.

## Analyse

L'analyse des données du Titanic vise à identifier les caractéristiques des passagers qui ont influencé leurs chances de survie. Pour cela, plusieurs variables clés ont été examinées :

- Sexe : L'analyse montre que le sexe a joué un rôle crucial dans les chances de survie. Environ 74% des femmes ont survécu, contre seulement 18% des hommes. Cette disparité s'explique par la priorité donnée aux femmes et aux enfants lors de l'évacuation.

- Âge : L'âge des passagers a également été déterminant. Les enfants, en particulier ceux de moins de 15 ans, avaient un taux de survie plus élevé. En revanche, les personnes âgées avaient des chances de survie réduites. Une analyse des âges médian et moyen des survivants par rapport aux non-survivants a révélé que les jeunes avaient plus de chances de survivre.

- Classe (Pclass) : La classe du billet, qui représente le statut socio-économique des passagers, était un autre facteur déterminant. Les passagers de première classe avaient un taux de survie d'environ 63%, tandis que ceux de troisième classe avaient un taux de survie de seulement 24%. Cela reflète probablement l'accès plus rapide aux canots de sauvetage pour les passagers des classes supérieures.

Ces analyses mettent en évidence les inégalités en matière de survie selon le sexe, l'âge, et la classe des passagers.

## Algorithmes

Dans cette étude, plusieurs algorithmes de classification supervisée ont été utilisés pour prédire les chances de survie des passagers :

Arbre de décision : Un arbre de décision a été utilisé pour comprendre les règles de survie basées sur les variables clés (âge, sexe, classe). Cet algorithme est interprétable et montre clairement comment chaque caractéristique contribue aux décisions de survie.

Forêt aléatoire (Random Forest) : Cet ensemble d'arbres de décision a permis de renforcer la robustesse des prédictions en réduisant les biais et la variance. La forêt aléatoire est particulièrement utile pour capturer les interactions complexes entre les variables.

Logistic Regression (Régression logistique) : Ce modèle linéaire a été utilisé pour estimer les probabilités de survie en fonction des caractéristiques des passagers. La régression logistique est efficace pour les problèmes de classification binaire, comme celui-ci.

Support Vector Machine (SVM) : Cet algorithme a été employé pour séparer les classes de survivants et de non-survivants en maximisant la marge entre les deux. Le SVM est adapté pour des données où les classes ne sont pas parfaitement séparables.

Chaque algorithme a été évalué en utilisant la précision (accuracy) pour déterminer lequel fournissait les prédictions les plus fiables. La comparaison des performances a permis de sélectionner le meilleur modèle pour prédire la survie des passagers.

## Conclusion

L'analyse des données du Titanic a révélé des insights importants sur les facteurs influençant les chances de survie des passagers. Les femmes, les enfants, et les passagers de première classe avaient significativement plus de chances de survivre.

En utilisant divers algorithmes de classification, nous avons pu prédire avec une précision notable les probabilités de survie en fonction des caractéristiques des passagers. Parmi les modèles testés, la forêt aléatoire s'est révélée être le meilleur en termes de précision et de robustesse. Ce projet démontre comment l'analyse des données et l'apprentissage automatique peuvent être utilisés pour explorer des événements historiques et extraire des connaissances significatives.