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

## Kernel k-means
Défaut de k means : seulement séparer les linéairements séparables, il faut des formes convexes (* voir question). Pour y remédier, transformer les données dans un espace de plus grande dimension (pk ?) avec une fonction non linéaire.
* Explication sommaire de la transformation, 60eme page : https://cse.iitk.ac.in/users/piyush/courses/ml_autumn16/771A_lec10_slides.pdf
* Explication et similarités avec spectral clustering : http://www.cs.utexas.edu/~inderjit/public_papers/kdd_spectral_kernelkmeans.pdf

## Spectral clustering
On forme la affinity matrix et on se sert des vecteurs propres eigen vectors. Explication sommaire : https://towardsdatascience.com/spectral-clustering-aba2640c0d5b
* Tutorial : http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.165.9323

## k-prototypes, k-modes
Extension du k-means à des objets non-quantifiables, remplace la distance par la dissimilarité

## Constrained k-means
Ajout de contraintes de liaisons et de non liaisons de certains points dans l'algorithme.
* Article original : https://web.cse.msu.edu/~cse802/notes/ConstrainedKmeans.pdf
* Façon semi supervisée : https://epubs.siam.org/doi/pdf/10.1137/1.9781611972740.31
* Contraintes grandes et bruitées : http://www.cs.cmu.edu/~dpelleg/download/lcvqe.pdf
* mteur graphique opengl.org

## Clustering ensemble
Combiner plusieurs partitions.
##  Énumération et explication de différentes méthodes : https://link.springer.com/content/pdf/10.1007/s13042-017-0756-7.pdf
1. Création des différents partitionnements
 * Diversité d'approches pur capturer max d'infos
 * Bootstrap et resampling pas trop capté
 * k-means avec différentes valeurs de k ou bien diiférents types de clustering,
2. Fonction de consensus
* Énumération présente orignialement dans https://arxiv.org/pdf/1606.01160.pdf
* The object co-occurrence approach : matrice de co-appartenance à un même cluster
* The median partition approach : Trouver la partition qui minimise la dissimilarité avec toutes les autres.
* -> Dans notre cas, co-occurences plus intéressantes puisqu'on s'intéresse à repérer des sujets précis et non pas à tout forcément clusteriser.
3. Évaluation   
* Précision avec ARI ou Normalized Mutual Information
* Stabilité avec moyenne et std de plusieurs tests en changeant légèrement les paramètres d'initialisation

## Python
* Cluster_Ensembles : Pipy cool
* OpenEnssemble : jmlr cool

# Visual assemsment of (cluster) tendency (VAT)
* Bzedek
* Tente de mettre dans le bon ordre la matrice des dissimilarités afin d'en visualiser les formes.
* article original : https://ieeexplore.ieee.org/document/1007487
* python : https://pyclustertend.readthedocs.io/en/latest/

# Deep clustering
## A Self-Training Approach for Short Text Clustering
https://www.aclweb.org/anthology/W19-4322/
* Smooth Inverse Frequency embedding
* Autoencodeur to map SIF vectors to low dimensionnal vectors (voir Hinton)
* Self trainning :
 * Apply cluter algorithm (k-means) on this
 * Assign a soft distribution probability to belong to each cluster to each point
 * Calculate an auxiliary probability distribution, according more importance to high confidence points
 * Fine-tune autoencoder to match this second distribution, with KL-divergence

## Reduce the dimensionaity of data with neural networks
https://www.cs.toronto.edu/~hinton/science.pdf
* Utilise une version améliorée de l'ACP.
