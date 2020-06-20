# Clustering de textes et de paragraphes
## Principe
Tenter d'extraire des infos :
* Thème
* Opinion
* Argument
* ...
d'un texte/paragraphe.

## Utilisation
S'en servir pour faire des graphes s'appuyant sur ces liens.

## 1. Exploration des possibles
### Idées supplémentaires
Clustering avec des graphes d'associations d'idées. Trouver mesure de similarité entre graphes (noyeaux thèse MJL)

### Articles reçus :
1. https://arxiv.org/abs/1907.07672?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+arxiv%2FQSXk+%28ExcitingAds%21+cs+updates+on+arXiv.org%29
2. https://medium.com/ether-labs/bert-for-unsupervised-text-tasks-fa6e9ce5d133
3. https://arxiv.org/abs/1905.11558



### 1. Analysis of Word Embeddings using Fuzzy Clustering
On peut obtenir des clusters de contextes de mots.
Appliquer du fuzzy clustering sur des vecteurs de word embedding

#### Fuzzy clustering
 Les points appartiennent à plusieurs clusters avec des coefficients différents.
* C-means = K-means fuzzy.
* fuzzy Gustafson-Kessel = augmented version pour reconnaitre shapes, en changeant la mesure de distance et le critère à minimiser.
* indicateurs de qualité : FPC, XB


####Word embedding
Mot représenté comme vecteur de nombre réels.
* GloVe [10] populaire algorithme : optimisation bayes avec coocurrences, résultat trainning matrice associe à chaque mot son vecteur. Mesure de similarité possible ensuite entre ces vecteurs.
* Word2vec : entraînement réseau neuronal, matrice sous produite

#### Résultats
 Appliquer FCM m=1.1, avec GloVe dim = 50 et 100 pour ~ centaines de mots. FGK très bof. Trop grande dimension = mauvais. Nombre de clusters fixé à vue de nez sur un graphique. On trouve des clusters de mots (on dit appartient à cluster si valeur d'appartenance >  seuil).

#### Utilisation
* Choisir quels sont les clusters : partis et obtenir les scores des mots sur-représentés, députés thèmes etc = NON car unsepervised.
* UNSUPERVISED :
* Entrainer les clusters au préalable, puis on peut ainsi en déduire les mots adaptés au contexte à sélectionner.

#### À se renseigner
* Trouver le bon nombre de clusters, ici fait arbitrairement.

#### Wikipedia Word embedding
Word2Vec,Mikolov, qui s'appuie sur les réseaux neuronaux. Voir schéma :
* **Contniuous bag-of-words** :
* **Skip-gram** : On a en entrée les *V* mots qu'on veut vectoriser, en sortie le mot prédit. Chaque exemple d'apprentissage est un **contexte**, qui associe à chaque mot présent ou absent.

### 2. BERT for unsupervised text tasks
#### BERT :
Améliore word embedding en étant bidirectionnel et se plaçant dans la signification de la phrase.
* Modèle BERT pour le français : https://camembert-model.fr/ et https://arxiv.org/pdf/1911.03894.pdf

* Explication de BERT https://ai.googleblog.com/2018/11/open-sourcing-bert-state-of-art-pre.html et https://arxiv.org/pdf/1810.04805.pdf

### 3. Leap LSTM
Propose une appllication de leap LSTM, plus efficace pour plusieurs tâches de NLP.
VOIR LES RÉFÉRENCES:
* Skim-RNN Seo et al 2017 : mini RNN pour les mots unimportant

[We present a novel modification to standard LSTM,
which learns to fuse information from various levels and
skip unimportant words if needed when reading texts.]

Les précédents LSTM ne prennent pas en compte tous les mots.
[More specifically, we design efficient feature
encoders to extract messages from preceding texts, following
texts and the current word for the decision at each step]

Le réseau indique à chaque exemple si on doit skip ou entraîner le LSTM. Usage d'un CNN.
Nécessite un GloVe pour fonctionner, mais comme celui -ci est aussi entraîné, les mots inconnus sont initialisés alétoirement.

Alméliorations LEGERE de performance. Mots importants en table 5.

### 4. Summarization with Pointer-Generator Networks
Résumé de textes. Nouveaux mots résume le texte.
