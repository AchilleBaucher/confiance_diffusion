# Graphes
## Principe
Créer des liens entre les députés, observer la diffusion de mots/idées/arguments = **concept**, au cours du temps.

## Choix
* Granularité au niveau député
* Lien entre députés selon la réutilisation du **concept**

## Première approche
### Choix du concept
**concept** = mot, choisi arbitrairement, puis voir ensuite si il est possible d'extraire les plus intéressants.

### Objectif
Créer un graphe entre les députés selon l'utilisaiton commune de certains mots.

### Questions
Temporalité prise en compte ? Au début non. Problèmes :
* Un graphe vraiment ? diffusion de proche en proche paraît étrange, plus 1 vers tous.

### Détails techniques
- [x] Avoir le nom du député associé à un texte
- [x] Former une matrice d'adjacence à partir d'un mot et des lettres
- [x] Afficher le graphe

### Les liens intéressants à montrer
Il faut trouver une mesure à partir de laquelle on choisit on non d'afficher le lien.
* Prop : Seulement les liens vers ceux qui ont un grand nombre de lettres
