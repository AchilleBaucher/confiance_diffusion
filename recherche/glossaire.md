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
Mesure de similarité entre deux distributions de probabilité. Dkl(P||Q) mesure en quelque sorte la cohérence de la distribution théorique Q par rapport à la réelle P en considérant la loi fournie par P. Est une divergence de Bregman.

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

## Arbre KD
Permet de faire des recherches par voisinage très rapidement. Version relaxée.

## Octree
Partition spatiale. Détection collision 3D

## Partition binaire de l'espace
