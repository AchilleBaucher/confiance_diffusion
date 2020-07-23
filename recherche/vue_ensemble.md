* quoi : clustering et similarités entre textes, en déduire des liens entre députés
* pourquoi : étudier blabla assemblée nationale
* comment : essayer variété de méthodes de clustering de textes, Python
* résultats : propres à chaque catégorie, pas encore de conclusion globale

# Clustering de textes
## Préparation
### Technique
* Mise à jour des données
* Extraire les députés et leurs noms.  *associer_auteurs.ypnb*

### Étude des données
* voir rapport metriq
* Comment sont structurées les lettres ? *observation_lettres.ipynb*, *excel*. Lettre surlignée. Forme première phrase, dernière diffuse.
* Est-ce que les députés sont spécialisés ? *deputes_specializes.ipynb*. graphiques, indicateurs quadratique et gini. Conclure un peu mais pas extrêmement frappant

## Représentation vectorielle
### Word embedding pour trucs courts
* Représenter le sujet et la rubrique d'une lettre avec Word Embedding. *sujet.ipynb* et *rubrique.ipynb*. Explication Word embedding (word to vec, modèle cbow ...), origine de la base, cosine distance, heatmap. Finalement arrêt de cette approche.


Les deux chapitres suivants ont des liens avec bac à sable dans *clustering.ipynb* et organisé dans *organized_clustering.ipynb*

### Méthodes principales
* TF et TFIDF, Explication et application aux données. Dimensions élevée, utilisé après.
* ACP. Explication, machin linéaire, graphiques, explained variance.
* LSA. Explication application.
* NMF. Explication application.
* LDA. Explication application.
* distances. Metrics utilisables et propriétés (cosine ...) sur chaque représentation, graphique à bosse, heatmap, amis d'une lettre.
* ACP + umap + t-sne sur chaque représentation.

## Clustering
* Evaluation. indices de clustering (inertie davies hrabasz ...), meilleurs k
* kmeans. Expliquer et appliquer.
* xmeans. Expliquer et appliquer.
* agglomerative. Expliquer, methods et metrics, et appliquer, dendogramme.
* spectral clustering
* Combinaisons. Comparer, ARI, combiner les partitions, stack, ensemble

### Annexes
* curse of dimensionality. *roue_libre.ipynb*. Explication trucs de la thèse (sparsity et creux et hubness), liens et graphiques avec nos données. Nécessité de réduire la dimension.

# Graphes députés
## Premiers tests
* voir *graphe.ipynb*
