# Clustering
Trouver des clusters et des distances entre lettres.
* Résume et référence de nombreuses méthodes : http://edutechwiki.unige.ch/fr/Clustering_et_classification_hi%C3%A9rarchique_en_text_mining
* https://hal.archives-ouvertes.fr/hal-00614071/document
* Autres techniques : https://static.aminer.org/pdf/PDF/000/472/974/fast_and_effective_text_mining_using_linear_time_document_clustering.pdf
## À base de TF-IDF
* TD-IDF puis DTW et classification de séries temporelles : https://www-ljk.imag.fr/membres/Marianne.Clausel/Fichiers/DefenseClustering.pdf
* TF-IDF puis k-means : https://towardsdatascience.com/applying-machine-learning-to-classify-an-unsupervised-text-document-e7bb6265f52

## LSA Latent Semantic Analysis
Pour déduire plus la sémantique latente, le sens du texte, que le champs lexical. Demande de faire un tfidf.
* Explication du calcul : http://blog.onyme.com/stats-semantique-lsa/
Effectuer une SVD sur la matrice document-terme avec score d'occurence ou du tfidf. Ne sélectionner que les valeurs singulières les plus hautes, avec un rang k choisi. Calculer l'approximation de la matrice au rang k. En déduire les distances (cosine) entre les deocuments.
* Article original : http://lsa.colorado.edu/papers/JASIS.lsi.90.pdf
* Avec python : https://www.pluralsight.com/guides/topic-identification-nlp ou https://www.analyticsvidhya.com/blog/2018/10/stepwise-guide-topic-modeling-latent-semantic-analysis/
* Version probabiliste : https://arxiv.org/pdf/1301.6705.pdf

## Hyperspace Analogue to Language (HAL)
Extrait les cooccurrences pour faire des liens entre les mots.
* Explication : http://blog.onyme.com/stats-semantique-hal/

## LDA (Latent Dirichlet Allocation)
Wikipedia : choisir K sujets et les documents ainsi que les mots ont des scores de probabilité (Bayes) dans chaque sujet. On part de la matrice des occurrences.
* Article original : http://papers.nips.cc/paper/2070-latent-dirichlet-allocation.pdf
* Python Gensim :  https://www.pluralsight.com/guides/topic-identification-nlp
* Python Scikit-Learn (utilisé):  https://medium.com/mlreview/topic-modeling-with-scikit-learn-e80d33668730
* Utilisation de LDA + EM Bayes : http://www.jmlr.org/papers/volume3/blei03a/blei03a.pdf
* tagging :  http://papers.nips.cc/paper/2587-integrating-topics-and-syntax.pdf
* clustreing : https://engineering.flipboard.com/2017/02/storyclustering

## NMF Factorization par matrices non négatives
* Effectuer le TF-IDF et décomposer avec NMF en deux matrices qui associent respectivement à chaque document et à chaque terme des valeurs positives dans des dimensions de taille choisie.
* Python scikit learn https://medium.com/mlreview/topic-modeling-with-scikit-learn-e80d33668730
* Article clustering :   https://people.eecs.berkeley.edu/~jfc/hcc/courseSP05/lecs/lec14/NMF03.pdf

## X-Means
Extention du k-means avec une estimation du nombre de clusters.
* Article original : https://www.cs.cmu.edu/~dpelleg/download/xmeans.pdf
**Algorithme** :
* Donner borne inf et sup de K
* Partir de la borne inf
* A chaque itération :
    * Run k-means jusqu'à convergence
    * Pour chaque cluster :
        * Diviser en 2 et faire 2-means
        * Décider de garder 1 ou 2 avec le BIC
        * BIC avec log vraissmeblance de spheric gaussian
**Mesures d'accélération** :
* Éviter doublons de calculs
* Structures en kd-treeb
**Python** :
https://pyclustering.github.io/docs/0.9.3/html/d2/d8b/namespacepyclustering_1_1cluster_1_1xmeans.html

## Critères de sélection
https://statweb.stanford.edu/~gwalther/gap
https://cran.r-project.org/web/packages/clusterCrit/vignettes/clusterCrit.pdf

## Comparer la similarité de la partition de deux clusters
* Adjusted rand index
* Simple matching coefficient
* Jaccard index
* Article énumérant les solutions : https://i11www.iti.kit.edu/extra/publications/ww-cco-06.pdf
* Autre meme chose : https://www.stat.washington.edu/mmp/Papers/compare-colt.pdf

## Clustering on several partitions
* Créer graphe O(n^2) des liens existants et prendre les composants complètement connectés : https://stackoverflow.com/questions/58373121/how-to-find-intersection-between-two-or-more-clusterings-of-the-same-dataset
* Combiner plusieurs partitions : http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.87.9937&rep=rep1&type=pdf
* La meme  : http://strehl.com/download/strehl-jmlr02.pdf
* Pour k means : https://arxiv.org/pdf/1712.08786.pdf
