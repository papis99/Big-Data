**Systeme de Recommandation Filtering Collaborative avec Pyspark exemple Movie Lens**  

  
  ----------------------------------------------------------**Prérequis**------------------------------------------------------------------  
  **Installation de Anaconda**    
  **Création et activation d’un nouvel environnement  **  
	  conda create -n nom_env python=3.9.12  
	  conda activate nom_env  
	  conda install jupyter  
	  conda install -n base nb_conda_kernels  

 **Installations des packages ci-dessous dans ce nouvel environnement :**    
	    conda install -y -c conda-forge pyspark  
	    conda install -c conda-forge findspark  
	    conda install -y -c anaconda pandas   
        
  **Ajout du nouvel environnement à jupyter notebook** 
	  pip install --user ipykernel  
	  python -m ipykernel install --user --name=nom_env  
    
  
------------------------------------------------------------**Implémentation**-------------------------------------------------------------    
  Dans ce programme, l'algorithme Alternating Least Squares (ALS) sera utilisé avec les API Spark pour prédire les notes des films dans le petit ensemble de données MovieLens.  
    
**Etapes :**   
J'ai utilisé le systeme de recommandation collaboratif ALS en utilisant Spark MLlib et ces recommandations de films sont basées sur l'utilisateur avec une technique de factorisation matricielle évolutive.    
  
**Étape 1 :**   Tout d'abord, je charge 2 ensembles de données, à savoir le film et le note attribué au film, et effectue un certain nombre d'explorations de données sur ces données pour obtenir des informations de base, telles que le nombre d'utilisateurs, le nombre de films, le nombre de notes par utilisateurs et par films.  
  
**Étape 2 :**   Après avoir effectué des prétraitements de données, je construis un modèle ALS basé sur les données d'évaluation pour prédire les évaluations, qui sont traitées comme un degré de préférence des films parmi différents utilisateurs. Les paramètres (maxIter, rank, regParam) sont réglés par une stratégie de recherche de grille via une validation croisée 5 fois pour obtenir le modèle avec le plus petit RMSE sur l'ensemble de validation. Ceci est considéré comme le meilleur modèle de prédiction.  
  
**Étape 3 :**   Par le meilleur modèle obtenu à l'étape ci-dessus, faire des prédictions des notes sur les films dans l'ensemble de test et calculer le RMSE pour évaluer les performances du modèle préparent l'étape suivante.  
  
**Étape 4 :**   Dans cette étape, j'utilise les résultats de prédiction du meilleur modèle pour recommander 5 films pour tous les ID utilisateur.
 mais aussi recommander des films à l'utilisateur numéro 100.
