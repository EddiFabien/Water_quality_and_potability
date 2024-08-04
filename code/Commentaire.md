## Commentaire sur le modèle de machine learning créé

#### Objectif :

-   Créer **un modèle** de l'apprentissage automatique **pour prédire la potabilité de l'eau à partir de ces principaux caractéristiques**.
-   Performance du modèle créé : obtient au moins **50% de recall** et **70% de f1-score**

#### Etapes de la réalisation :

##### 1er étape : Importation des librairies utiles

J'ai importé tous les librairies necéssaires et les librairies qui peuvent-être utilisé pour atteindre les objectifs ci-dessus.

##### 2e étape : Pré-traitement de données

Dans cette partie, j'ai créé des fonctions: une fonction pour l'élimination des valeurs abberantes, une fonction pour traiter les valeurs manquantes et une fonction qui réunit tous les fonctions de pré-traitement de données.

##### 3e étape : Avant la modélisation du modèle

-   J'ai créé une pipeline qui englobe tous les transformations de la pré-traitement de données principaux comme la méthode de selection des variables et la méthode de features engineering à l'exception de la méthode de standardisation de données (J'ai expliquez cette raison dans le point suivant...).\

-   Ensuite, j'ai créé des autres pipelines qui reunissent chacun un modèle, un pipeline de pré-traitement de donnnées ci-dessus et une méthode de standardisation de données (seulement pour le modèle de classification `KNeighborsClassifier` et `SVM` parce que les autres modèles basées sur l'arbre et l'ensembre n'ont pas besoin de données standardisés lors de ses apprentissages.

-   J'ai créé ensuite un dictionnaire des pipelines que j'ai déjà crée précedement.

-   J'ai créé une fonction d'évaluation dans le but d'afficher la performance de chaque modèle, leur courbe d'apprentissage et leur courbe d'évaluation.

-   Enfin, j'ai tester cette fonction d'évaluation en utilisant l'algorithme `RandomForestClassifier`. Je fais ensuite quelque réglage comme la suppression des valeurs abberrantes, le traitement des variables manquantes (remplacement par une valeur ou suppression), le réglage des hyper-paramètres dans le pipeline de pré-traitement de données principaux. J'ai fais une évaluation à chaque changement,j'ai prends des notés et j'ai comparé qui a la meilleure performance.

-   Au final, j'ai trouvé comme perfomance pour ce modèle dans l'image ci-dessous:

    <p align="center">

    <img src="/Water_quality_and_potability/img/performance_randomForest.png" width="100px"/>

    </p>

-   Et sa courbe d'apprentissage et sa courbe d'évaluation dans l'image ci-dessous

    <p align="center">

    <img src="/Water_quality_and_potability/img/learning_curve_randomForest.png" width="100px"/>

    </p>

##### 4e étape : la modélisation final du modèle

-   Dans ce dernier étape, j'ai entraîné tous les modèles en utilisant la fonction d'évaluation que j'ai créé dans la partie précédente.
-   Ensuite, je compare tous les résultat, je prend la meilleure performance et le modèle qui n'a pas un signe de surapprentissage.
-   Au final, j'ai tombé encore sur `RandomForestClassifier`.
-   Je fais quelque ajustement pour améliorer sa performance en utilisant `GridSearchCV` mais il n'atteint que **48.23% de score au final**.

### Conclusion:

-   D'après la figure ci-dessous, le modèle de `RandomForestClassifier` apprend bien à 100% et la courbe de validation a une tendace d'augmenter mais il n'arrive pas à stagner dans une valeur plus intéressante lors son évolution même en essayant de faire des ajustements. **La score finale est donc 48.23%.**
-   Je pense qu'il faut peut-être ajouter plus de données et reévaluer ce modèle pour que sa courbe d'apprentissage stagne dans une meilleure valeur afin d'obtenir la meilleure score.
-   J'ai une tendance de penser que l'ensemble de données n'est pas vrai dans la vraie vie parce que je fais quelque recherche sur internet concernant les variables liées au potablité de l'eau et je trouve qu'il y a certaine variable dépend peut-être de l'autre variable comme le pH peut-être avoir des effets sur la dureté, [Cliquez ici](https://www.inbw.be/parametres-et-normes#durete-eau) pour aller vers le site. Mais on a vu lors de mon analyse exploratoire de données que ces deux variables ont une très très faible corrélation. On a donc une contradiction. C'est très difficile de prendre de décision avec.
