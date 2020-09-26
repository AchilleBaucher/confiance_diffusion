* Quoi : Appliquer des méthodes de clustering , de représentation de textes et de comparaisons entre textes courts qui sont ceux de l'assemblée nationale, (en déduire des liens entre députés).
* Pourquoi : Explorer et répertorier des méthodes utilisables sur ce type de données (savoir de quelle manière les députés+8+++++++++5+ partagent des arguments etc.)
* Comment : Suite
* Résultats : Quelles approches ont fonctionné ou non et pourquoi, (Générer des graphes avec les liens des députés)


# Préparation et première approche
## Technique
* Mise à jour des données
* Extraire les députés et leurs noms.  *associer_auteurs.ypnb*

## Étude des données
* voir rapport metriq
* Comment sont structurées les lettres ? *observation_lettres.ipynb*, *excel*. Lettre surlignée. Forme première phrase, dernière diffuse.
* Est-ce que les députés sont spécialisés ? *deputes_specializes.ipynb*. graphiques, indicateurs quadratique et gini. Conclure un peu mais pas extrêmement frappant

# Clustering de textes
* Principe : Mettre le texte sous forme vectorielle puis effectuer des techniques de clustering classiques
## Représentation vectorielle et réduction de dimension
### Pour les mots et expressions
* Représenter le sujet et la rubrique d'une lettre avec Word Embedding. *sujet.ipynb* et *rubrique.ipynb*. Explication Word embedding (word to vec, modèle cbow ...), origine de la base, cosine distance, heatmap. Finalement arrêt de cette approche.


Les deux chapitres suivants ont des liens avec bac à sable dans *clustering.ipynb* et organisé dans *organized_clustering.ipynb*

### Pour les textes entiers
* TF et TFIDF, Explication et application aux données. Dimensions élevée, utilisé après. Curse of dimensionality
* ACP. Explication, machin linéaire, graphiques, explained variance.
* LSA. Explication application.
* NMF. Explication application.
* LDA. Explication application.
* distances. Metrics utilisables et propriétés (cosine ...) sur chaque représentation, graphique à bosse, heatmap, amis d'une lettre.
* ACP + umap + t-sne sur chaque représentation.

## Clustering avec les représentations obtenues
* Évaluation. indices de clustering (inertie davies harabasz ...), meilleurs k
* kmeans. Expliquer et appliquer.
* xmeans. Expliquer et appliquer.
* agglomerative. Expliquer, methods et metrics, et appliquer, dendogramme.
* spectral clustering
* Combinaisons. Comparer, ARI, combiner les partitions, stack, ensemble

## Analyse des clusters
* Prototypes et mots associés

### Annexes
* curse of dimensionality. *roue_libre.ipynb*. Explication trucs de la thèse (sparsity et creux et hubness), liens et graphiques avec nos données. Nécessité de réduire la dimension.

# Graphes députés
## Premiers tests
* voir *graphe.ipynb*
