## C'est un projet dans le site du Kaggle et mon premier projet personnel sur la création d'un modèle de l'apprentissage supervisé pour la classification binaire

#### Descriptions du projet :

-   Titre : Analyse de qualité de l'eau et création d'un modèle de l'apprentissage supervisé le plus performant pour classer sa potabilité
-   Lien : cliquez [ici](https://www.kaggle.com/datasets/uom190346a/water-quality-and-potability)
-   Durée de réalisation : 3h par jour pendant 3 jours

#### Objectif principal :

L'objectif principal est **de créer un modèle de l'apprentissage supervisé** à partir d'un ensemble de données **dans le but de prédire la potabilité de l'eau en fonction des attributs de qualité de l'eau** avec une perfomance de **50% pour le recall** et **70% pour le f1**.

#### L'ensemble de données :

Cet ensemble de données contient des mesures et des évaluations de la qualité de l'eau liées à la potabilité, c'est-à-dire à l'aptitude de l'eau à la consommation humaine. L'objectif principal de l'ensemble de données est de fournir des informations sur les paramètres de qualité de l'eau et d'aider à déterminer si l'eau est potable ou non. Chaque ligne de l'ensemble de données représente un échantillon d'eau avec des attributs spécifiques, et la colonne « Potabilité » indique si l'eau est propre à la consommation.

**Les différents colonnes dans cet ensemble de données:**

-   *pH* : Le niveau de pH de l'eau. (entre [0,14])
-   *Dureté* (mg/L): Dureté de l'eau, une mesure de la teneur en minéraux.
-   *Solides* (ppm): Total des solides dissous dans l'eau.
-   *Chloramines* (ppm): Concentration de chloramines dans l'eau.
-   *Sulfate (mg/L)*: Concentration de sulfate dans l'eau.
-   *Conductivité* (μS/cm): Conductivité électrique de l'eau.
-   *Carbone organique* (ppm): Teneur en carbone organique dans l'eau.
-   *Trihalométhanes* (μg/L): Concentration de trihalométhanes dans l'eau.
-   *Turbidité (NTU)*: Niveau de turbidité, une mesure de la clarté de l'eau.
-   *Potabilité* : Variable cible ; indique la potabilité de l'eau avec des valeurs 1 (potable) et 0 (non potable).

#### Plan d'action :

le plan est le suivant :

-   Analyse exploratoire de données (EDA): faire un EDA dans le but de connaître le mieux possible les données, de comprendre l'interaction entre les variables et j'accompagne tous ça avec des tableaux et des graphiques ainsi que leurs interpretations.
-   Apprentissage automatique: faire un pré-traitement de données et choisir les modèles de classification de l'apprentissage supervisé, de les entraîner, de les évaluer et de prendre un modèle qui est le plus performant parmis eux.

#### Outils et langages utilisées pendant la réalisation :

-   OS : Ubuntu, Windows
-   Outils : VSCode, MSWord
-   Langage : python

#### Dossiers et fichiers :

-   dataset : contient l'ensemble de données
-   code.ipynb : le code
-   EDA.pdf : le résultat de l'analyse exploratoire de données.
-   potability_model.pkl : le model créé

#### Resultats finals:

**Analyse exploratoire de données :**

-   Les proportions de deux classes de la potabilité ne sont pas équilibré.
-   On a une très faibles voir aucune corrélation entre tous les variables.
-   On trouve 15% de valeurs manquantes dans l'attribut pH, 24% dans la Sulfate et 49% dans la Trihalométhanes.
-   Il y a des valeurs extrêmes dans tous les attributs.

**Apprentissage automatique :**

-   Je trouve que l'algorithme `RandomForestClassifier` est le plus performant par rapport aux autres algorithmes de classification avec **un score recall de 35.66%** et **un score f1 de 48.24%** puis je le sauvegarde.
-   La perfomance de ce modèle n'est pas vraiment très bonne par rapport à l'objectif parce que peut-être le nombre des variables est insuffisant pour faire entraîner et valider ce modèle ou peut-être à cause de manque de corrélation entre les variables features et la variable target.
