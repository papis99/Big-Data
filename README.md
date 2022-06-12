_Systeme de Recommandation Filtering Collaborative avec Pyspark exemple Movie Lens_

Clicker Ici pour plus de détail  
Dans ce bloc-notes, l'algorithme Alternating Least Squares (ALS) sera utilisé avec les API Spark pour prédire les notes des films dans le petit ensemble de données MovieLens  
#Etapes 
J'ai utilisé le systeme de recommandation collaboratif ALS en utilisant Spark MLlib et ces recommandations de films sont basées sur l'utilisateur avec une technique de factorisation matricielle évolutive.  
*Étape 1 Tout d'abord, je charge quatre ensembles de données, à savoir le film, le classement, les liens et les balises, et effectue un certain nombre d'explorations de données sur ces données pour obtenir des informations de base, telles que le nombre d'utilisateurs, le nombre de films, le nombre de classements par utilisateurs et par films. respectivement, et la distribution de films sur différents genres
.
