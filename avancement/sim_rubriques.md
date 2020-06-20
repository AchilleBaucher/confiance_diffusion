# Mesure de similarité des rubriques
## Contexte
Afin de réduire la quantité de documents à analyser pour déterminer les lettres parlant d'un sujet identique, une solution consiste à ne rechercher que dans les rubriques (~ 211 en tout) susceptibles d'en contenir.

## 1. Similarités entre rubriques
L'idée est de déterminer une mesure de similarité entre les rubriques.
### 1.1 Les noms des rubriques
Dans un premier temps, une mesure de la similarité de deux rubriques en ne considérant que leur nom peut-être suffisante. **Word embedding** semble être la meilleure solution, car ils portent l'information du **contexte** du mot, ce qui est précisément ce que nous cherchons ici.

#### 1.1.1 Word2Vec
Voir *jupyter/rubrique*

#### 1.1.2 GloVe

### 1.2 Une analyse entière des sujets traités
Via le champs lexical utilisé etc., on en déduit des similarités entre les rubriques.


## 2. Lien potentiel entre un sujet et une rubrique
Cette fois, on sélectionne une lettre, identifie son sujet et on cherche toutes les rubriques dans lesquelles sont sujet pourrait être traité. S'appuyer sur les informations obtenues en partie 1.


### 3. Classifier les lettres (label = rubrique)
On entraîne un NN pour apprendre à reconnaître les rubriques en fonction du texte.
* RNN pour classification : https://arxiv.org/pdf/1703.01898.pdf
* LDA : voir *identifier_sujet/LDA*

## 4. Classification de rubriques
Peut-être que les mesures de distances peuvent permettre une classification de rubriques, mais ce n'est pas forcément nécessaire.
