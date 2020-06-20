# Clustering et graphe de députés
## Principe
Grandes lignes du projet et noms des fichiers correspondant aux parites
### **S** : Regrouper les lettres qui parlent d'un même **sujet**
* *sim_rubriques* : Établir des similarités entre rubriques ou trouver une correspondance entre un sujet et celle-ci
* *identifier_sujet* : Identifier le sujet d'une lettres
* Faire de clustering de lettres avec leur sujet

### **C** : **Comparer** les lettres d'un même sujet
* Identifier un argument/intérêt/association d'idées
* *similarite_semantique* : Établir un score de proximité sémantique, +-accord, entre deux lettres

### **G** : En déduire un **graphe** de députés
* Attribuer des liens entre députés en fonction des proximité de
* Effectuer du clustering avec la carte des distances
* Parcourir, visualiser le graphe obtenu

## Code
* *associer_auteur* : Associer l'auteur et son nom à chauqe lettre
* *deputes_specialized* : Déterminer si les députés sont spécialisés dans certains sujets
* *observation_lettres* : observation de la structure des lettres et des rubriques associées etc.
* *rubrique* : Établir des similarités entre rubriques ou trouver une correspondance entre un sujet et celle-ci
* *sujet* : Identifier et comparer le sujet de lettres
* *graphe* : Graphe des députés
