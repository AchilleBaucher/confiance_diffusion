
# Analyse multivariée /statistiques multivariées
S'intéresse à des lois de probabilités à plusieurs variables.

# Algèbre linéaire
Vecteurs, anneaux, corps etc.

# Non_negative matrix factorization
* https://en.wikipedia.org/wiki/Non-negative_matrix_factorization
Factorisation d'une matrice en deux autres, tous les termes sont positifs. WH=V.

## Utilisation en text minings
* *V* : Matrices des occurrences des mots (en colonnes) par document (en ligne)
* *k* : Nombre de dimensions choisi arbitrairement
* *W* : Matrice des documents (en ligne) et des *k* dimensions associées (en colonne)
* *H* : Matrice des mots (en colonne) et des *k* dimensions associées (en ligne)
En calculant WH approx V on a mis en correspondance des mots et des documents. En imposant HHt = I, on a les résultats d'un k-means. Si on prend l'erreur, on obtient un PLSA.

## Fonctions d'erreurs possibles
On peut prendre Frobenius ou Kullback-Leibler

# Norme de forbenius
Norme d'une matrice, racine de la somme des termes au carré

# Divergence de Kullback-Leibler
Mesure de similarité entre deux distributions de probabilité. Dkl(P||Q) mesure en quelque sorte la cohérence de la distribution théorique Q par rapport à la réelle P en considérant la loi fournie par P. Autrement dit, le nombre de bits nécessaire à la transmission de symboles venant d'une distribution P codés selon la loi théorique Q. Est une divergence de Bregman.

# Divergence de Bregman
Mesure de la différence entre deux distributions dérivée d'une fonction potentiel U à valeurs réelles strictement convexe et continûment différentiable.

# SVD : Décomposition valeurs singulières
* Wikipedia :
Mise de M m*n sous forme U\SigmaV*, avec U m*m unitaire, \Sigma m*n  diagonnale et V n*n unitaire. La diagonale de \Sigma sont les valeurs singulières. U et V sont des vecteurs d'une base orthonormée. V entrée, U sortie. Valeurs singulières correspond aux valeurs propres si M est Hermitienne semi-définie positive. Aucune restriction sur M, peut ne pas être carrée.

# Matrice adjointe : M*
Transposée de la conjuguée

# Matrice unitaire M
MM* = I

# NMF Non-Negative Matrix Factorization
Factoriser une matrice M m*p en W m*r et H r*p avec comme contrainte la non négativité
* Explication du principe et de l'algo :  https://www.math.univ-toulouse.fr/~besse/Wikistat/pdf/st-m-explo-nmf.pdf

# AIC et BIC
Score de pénalité d'un modèle statistique. Mesure la perte d'information du modèle. Version AICc pour les petits échantillons. BIC dépend de la taille de l'échantillon et pas seulement du nombre de paramètres.

# Arbre KD
Permet de faire des recherches par voisinage très rapidement. Version relaxée.

# Octree
Partition spatiale. Détection collision 3D

# Partition binaire de l'espace

# UMAP
Uniform Manifold
Approximation and Projection for
Dimension Reduction : Technique pour la réduction de dimension. La théorie s'appuie sur la gémoétrie de Riemann.
* Article original : https://arxiv.org/pdf/1802.03426.pdf
* Python : https://umap-learn.readthedocs.io/en/latest/
* Suppose que les données sont uniformément représentées sur une variété géométrique inconnue.
* On peut trouver une métrique de Riemann tel que c'est le cas.
* ...
* Explication supplémentaires : https://towardsdatascience.com/how-exactly-umap-works-13e3040e1668
* Mieux que t-sne car
 * t sne occupe trop de mémoire
 * Ne prend pas en compte la structure globale des données (ne gère bien que des distances intra clusters et non inter clusters, genre 2 clusters proches sont pas forcément proches)
 * Ne réduit qu'en 2 ou 3 dimensions
 * Superior run time performance

## Explication précise
1. Construire une fuzzy représentation topologique :
 * Approximer une variété sur laquelle les données semblent se positionner
  * On suppose que les données sont uniformément représentées sur cette variété
  * Uniforme donc toute boule avec la bonne distance contient le même nombre de points
  * On approxime donc un espace métrique par point, et il va falloir les joindre.
 * Construire une représentation en fuzzy simplexe de cette variété
2. En déduire une représentation à faible dimension

## Explication moins précise
Forme le 1-squelette qui est un graphe pondéré


X. Apprendre la théorie des catégories et la topologie Riemannienne.

# Géométrie Riemannienne
Branche de la géométrie différentielle sur des formes ou existent une notion d'angle et de distance.

# Géométrie différentielle
Application des méthodes de calcul différentiel à la géométrie.

# Manifold géométrique
Espace de dimension inférieure à l'hypersurface, courbe (bof)

# Variété Riemannienne

# Variété différentielle

# Ensembles simpliciaux
Peut fournir une approche combinatoire des espaces topologiques.
# Variété topologique
Espace topologique (définit avec des ensembles et des ouverts), assimilable localement à un espace Euclidien de dimension n (tout point de l'espace possède un voisinage homéomorphe à un ouvert de R^n)

# Homéomorphe en topologie
Existe application bijective continue et réciproquement continue
# Geodesic distance
Généralisation du concept de distance effective sur des hypersurfaces

# Curse of dimensionality (fléau de la dimension)

# Distribution à queue lourde (heavy tailed distribution)
Distribution à queue non exponentiellement bornée, ex : log normal, pareto ...

# Adjusted rand index
Mesure l'accord de deux partitions

# Normalized Mutual Information
Mesure l'accord de deux partitions d'une autre manière. Mesure symétrique de l'information partagée.

# Entropie (de Shanon)
Mesure le nombre moyen minimal de bits nécessaire au codage d'une information.

# Entropie croisée
* Wiki:
H(p,q) = espérance selon p de -log2(q). À une constante près, même formule que la divergence de Kullback-Leibler, mais seulement si no compare une distribution q avec une distribution de référence p.
* https://arxiv.org/pdf/1405.2061.pdf
Whereas, Shannon’s entropy metric quantifies, among other things, the
absolute minimum amount of storage and transmission needed for succinctly
capturing any information.
how much can the raw data of a variable be compressed without losing the
information in the variable ?

# Méthode de l'entropie croisée
Méthode d'optimisation
* Générer des données
* Mettre à jour les paramètres de génération à partir des données

# Auto-encoder
2 réseaux de neurones :
* Encoder : map l'entrée vers une représentation cachée (souvent de dimension inférieure)
* Decodeur : map la représentation cachée vers l'espace d'entrée
* Entraîné à reproduire l'entrée à partir de celle-ci (généralement avec erreur quadratique et descente de gradient)
* Permet d'obtenir un mapping non linéaire réduisant la dimension (dans l'espace caché)
* Initialiser un autoencoder: https://www.cs.toronto.edu/~hinton/science.pdf

# Loi Beta
Loi de probabilité pour une seule variable comprise entre 0 et 1. Paramétrée par \alpha et \beta. Cas spécial d'une loi de Dirichlet.

# Perplrexité
* https://towardsdatascience.com/perplexity-in-language-models-87a196019a94
Mesure d'évaluation intrinsèque (sans faire appel à une tâche et comparaison extérieure) de modèles de langages.  Différents modes de calculs :
1. Probabilité inverse normalisée du jeu de donnée test
Donne un score de non réalisme du jeu d'entrée, normalisé par le nombre de mots à chaque fois. Pour cela, une petite astuce en passant en log pour avoir une somme pondérable par le nombre de mots puis en exp pour revenir en obtenant une racine.
2. Exponentielle de l'entropie croisée
Peut mesurer la différence de probabilité estimée et réelle.
