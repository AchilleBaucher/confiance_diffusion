# Clustering
Trouver des clusters et des distances entre lettres.
* Résume et référence de nombreuses méthodes : http://edutechwiki.unige.ch/fr/Clustering_et_classification_hi%C3%A9rarchique_en_text_mining

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