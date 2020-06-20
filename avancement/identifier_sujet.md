# Identifier le sujet d'une lettre
Identifier de quoi parle les lettres pour les regrouper par sujet.

## Caractéristiques d'une lettre
* Sujet principal contenu dans la première phrase
* Titre assez explicite

## Méthode : average vector
Faire la moyenne des vecteurs de la phrase ou du titre :
https://freecontent.manning.com/sentence-classification-in-nlp/

## Méthode : thème avec LDA (Latent Dirichlet Allocation)
Wikipedia : choisir K sujets et chaque document a des scores e probabilité (Bayes) dans chaque sujet.
* Pratique utilisecomparer  : https://www.pluralsight.com/guides/topic-identification-nlp

* Utilisation de LDA + EM Bayes : http://www.jmlr.org/papers/volume3/blei03a/blei03a.pdf
* tagging :  http://papers.nips.cc/paper/2587-integrating-topics-and-syntax.pdf

## Topic Modelling
Latent Semantic Analysis (LSA) pour déduire plus la sémantique latente, le sens du texte, que le champs lexical. Demande de faire un tfidf.
* Explication du calcul : http://blog.onyme.com/stats-semantique-lsa/
* Article original : http://lsa.colorado.edu/papers/JASIS.lsi.90.pdf
https://www.pluralsight.com/guides/topic-identification-nlp
* Version probabiliste : https://arxiv.org/pdf/1301.6705.pdf

## Méthode : deep contextualized word representation
* Représenter conexte bidirectionnal : https://arxiv.org/pdf/1802.05365.pdf

## BERT
Bidirectionnal Encoder Represntation from Transformers
* Code https://github.com/google-research/bert
### BERT.1 Article original
* https://arxiv.org/pdf/1810.04805.pdf
#### BERT.1.1 Fonctionnement de l'algorithme BERT
1. **Pre-training** on unlabelled data. Les *token* sont des *WordPiece*. Entrainer le *transformer ???* avec un *MLM* . Ensuite entraîner le même *transformer ???* en NSP.

2. **Fine-tunning** : Entraîner un *transformer ???* avec la même architecture et initialisé avec les paramètres ( *= poids ?*) obtenus par le pre-training, (donc en fait le même *transformer ???*) sur des tâches plus spécifiques de notre choix.

* **Token** : Unité symbolique. *Ex : mot, bout de mot ...*
* **Sentence** : Ensemble ordonné et limité de *token*
* **Word Piece** : Mots parfois séparés en plusieurs parties, trouvés par un algorithme unsupervised précédent, et sous forme de vecteurs. Ce sont ici les token utilisés.
* **MLM = Masqued Language Model :**, Certains token ou groupes de token (ici ~15%) sont masqués aléatoirement dans une phrase et la tâche est de reconstruite la phrase ou comme ici de deviner les token masqués.
* **NSP = Next Sentence Prediction :** (~ Cloze Task) Le résau doit reconnaître si la deuxième sentence est bien la bonne, ici supervised learning avec 50% faux (random) et 50% vrai.
* **Encoder** : La façon d'encoder (représenter) les token et les sentences a une importance cruciale, elle permet de réduire les dimensions pour ne travailler que sur les informations pertinentes.

#### BERT.1.2 Caractéristiques de l'algorithme BERT
* Le pre-trainning est extrêmement important et radicalement plus rapide
* Les autres approches sont unidirectionnelles, ou un concaténation de deux directions (Ex : ELMO), tandis que BERT est complètement bidirectionnel.
* BERT a plus une approche *fine-tunning* que *feature based*
* BERT plus performant sur le level des token comme celui des sentences
* **Feature based approach** :*???* Trouver des caractéristiques en unlabelled, et s'en servir pour des tâche plus précise
* **Fine-tunning** : *???*

**NLP tasks** :
* **NLI** : Natural Language Inference,
* **QA** : Question Answering

### BERT.1.3 Voir
* **Transfert Learning** : voir AA
* **Self-attention** : détecter les entités importantes par rapport à une requête
* **Transformers** : voir
* LES TASKS QU'ILS UTILISENT

### BERT.2 Plus
#### BERT.2.Transformers
* From https://medium.com/inside-machine-learning/what-is-a-transformer-d07dd1fbec04
* **Seq2Seq** : transforme un sequence de token en une autre séquence, traduction par ex. Uses LSTM qui permet de prendre en compte l'ordre des sentences et de sélectionner ce qui est important. Encoder en vecteur avec bcp de dimensions et décoder en sequence. Le LSTM permet de prendre en compte l'importance des token (attention) en les pondérants dans l'encodage et le décodage.
* **Transfomers** : Pas LSTM ni RNN

## Summarization
* Génération de résumé abstraits avec NN :
https://arxiv.org/pdf/1704.04368.pdf
* Amélioration de phrases : https://www.aclweb.org/anthology/D14-1085.pdf
* Génération de résumé abstraits avec attentive RNN : https://www.aclweb.org/anthology/N16-1012.pdf
