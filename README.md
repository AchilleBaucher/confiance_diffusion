# poli_diffusion
## Principe
* On modélise les opinions individuelles et institutionelles par un graphe d'associations d'idées (+arguments?) = cadre de référence
* On modélise le comportement d'acceptation d'information par une appplication du modèle de confiance de l'article d'Adrien
* On en déduit une dynamique de diffusion des informations pour mettre en exergue certains mécanismes

## Modélisation
**Objectif** : Former modèle de diffusion d'information en s'inspirant du modèle de confiance d'Adrien. Ce serait une application de ce dernier à la diffusion d'information dans le débat public.

### 1. Fiabilité
À quel point je veux croire ce que me dit ma source ?
**Mesure** :
* La proximité pondérée dans un graphe d'opinions, obtenue par des likes facebook etx
* La cohérence globale des informations de cette source avec mon cadre de référence
**Justification** :
 
### 2. Compétence
On peut y rajouter un facteur

### 3. Plausibilité
À quel point l'information correspond-elle à mon cadre de référence ? 
**Mesure** :
On fait le choix de considérer que le cadre de référence est modélisable par un graphe d'association d'idées, et on tente alors d'en déduire la cohérence d'un argument par rapport à un graphe.
**Justification** : 
En parcourant les sites d'opinions (think-tanks, partis, journaux, lettres des députés ...), on peut remarquer que ce ne sont pas tant les oppositions sémantiques d'arguments qui font la différence, mais surtout :
* Les focalisations sur certains sujets -> graphe termes pondérés
* Les associations d'idées = cadre de référence ( islam-danger, développement-croissance, finance-parasite ...) -> graphe associations de termes
**Défis** :
* Une mesure de la proximité de 2 graphes
* Former combien de graphes, quelles techniques,

### 4. Crédibilité
À quel point cete information a été relayée par des sources que je considère comme fiable ? 
**Mesure** : Quantifier le nombre d'informations similaires ou proches diffusées par des sources dont la fiabilité est définie plus haut.
**Justification** : On est entouré de sources auxquelles on accorde de la fiabilité, via les abonnements sur les réseaux sociaux et la presse, les chaînes de télévision et les radios qu'on choisit, les groupes culturels qu'on fréquente

### Remarques
Faut-il ajouter une section : 
* Ce que je veux croire 
* Ce qui m'arrange de croire 
Ou sont elles inclues dans les autres ?

### Diffusion de l'information et évolution temporelle
* Informations non évidentes (confinement, élection) mais influençant l'opinion (arguments, faits divers ...)
* Modèle *Simple* = Tous le monde a accès à l'information **OU** *Complexe* = celle-ci circule à travers des graphes
* Mettre en exergue des mécanismes (autoconfirmation, radicalisation ...) avec humilité car on n'y connaît rien en politique et que c'est un modèle grossier qui se veut simplement exploratoire
* Modification du cadre de référence d'un individu/groupe, séquences temporelles?, associations à des dates?

## Questions article Adrien
* Le modèle sert à contextualiser et à formaliser un cadre d'analyse ?
* Ordre d'intégation : arbitraire et adaptatable. non ?
* Séquentialité : comment représenter ?
* Posture de crédulité : pourquoi pas.

## Questions
* Diffusion d'information : comment représenter ?
* Apprentissage Kernels
