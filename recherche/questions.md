# Avancement et questions pour le 6 Juillet
## Avancement
* k-means dimensions spérieures : pk traits ?
* Changement et jeux avec linkage et affinity, dans tous les graphiques + distances à la fin
* Autres distances possibles ? : **braycurtis**, **canberra**, **chebyshev**, **cityblock**, **correlation**, **cosine**, **dice**, **euclidean**, **hamming**, **jaccard**, **jensenshannon**, **kulsinski**, **mahalanobis**, **matching**, **minkowski**, **rogerstanimoto**, **russellrao**, **seuclidean**, **sokalmichener**, **sokalsneath**, **sqeuclidean**, **yule**
* Affichage des densités,mean std, calcul sur tous le corpus
* Ajout titres et des scores de clustering un peu partout, explication dans *clustering.md*
* NMF calculé pour densité etc
* K-means criterions et évolution pour lsa, arrêt vers 10 15
* HAC : tests multiples linkage et affinity, dendogramme tronqué, voir **B.2**
* X-means : lu dans *clustering.md*, fait dans **B.3** : Reste sur le nombre minimal de clusters, ou sinon non mais très variable

* lu Spectral clustering et t-sne
* lu kernel k-means mais pas imlémenté
* Démo k-means au propre et aussi certains indices etc.
* Umap expliquée
* Curse of dimensionality dans roue-libre

## Questions
* Le critère ARI ne fonctionne que pour 2 partitions
* On ne cherche pas à distinguer plusieurs clusters mais à en repérer certains petits
* Comment intégrer la période ? Distance + date ?   
* Trouver des clusters communs entre les différentes partitions
* Pourquoi k-means seulement linéairement séparable ? formes convexes ?

## Le plus important
* Combiner et comparer pleins de partitions
* Comment repérer la première bosse, celle qui nous importe pour le parler de la même chose
* Nice Nîmes
* Armand

# Avancement et questions pour le 21 Juillet
## Avancement
* Lecture curse of dimensionnality et graphiques associés (*roue_libre.ipynb*)
* Explained variance (*clustering*) pas bcp de cassure nette, assez peu d'explication
* Affichage de tous les dendogrammes systématiquement.
* Matrice de comparaison de beaucoup partitions *organized_clustering.ipynb*
* Lecture début clustering ensemble *clustering.md*
* Essai en cours de OpenEnssemble
* Custering ensemble : CO et mutual
* Résumé global commencé (*vue_ensemble.md*)

## Questions et suite
*
