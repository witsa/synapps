# Bonnes et Mauvaises pratiques *(...en construction...)*

L'ambition de cette partie est de répertorier les pratiques et usages autour de la construction de SynApp qui sont à reproduire et ceux qui sont à proscrire.


## Avant d'ouvrir le Maker : Dessinez !

Quelques éléments sur les étapes à réaliser **avant** d'ouvrir le Maker afin de construire la SynApp sereinement.

### La maquette

La première chose à faire avant d'ouvrir le Maker est de réaliser un dessin ou maquette de l'interface désirée.
Cela évitera bien des écueils et donc de perdre du temps. 
Cela permettra : 
 - de mieux définir les fonctionnalités attendues, 
 - de mieux prévoir les temps de réalisation 
 - et d'identifier des briques à réutiliser.

> Un simple petit croquis peut faire gagner énormément de temps.

Il ne faut pas non plus hésiter à inclure le client dans cette étape.

### Découpage en Scènes

Toujours sur papier, Préparez votre SynApp en la découpant en plusieurs scènes.

> Une idée/fonctionnalité majeure par scène. 

Il sera toujours plus facile de réunir des fonctionnalités sur une même scène que de les diviser plus tard.

Cela va permettre aussi de réutiliser des fonctionnalités similaires sur plusieurs endroits de la SynApp sans avoir à les refaire à chaque fois.

C'est encore plus important avec les interfaces dédiées aux plateformes nomades où la fonction de l'écran doit être facilement identifiable et accessible.

### La Mise en Scène des acteurs.

> Découpez vos scènes zone avec les acteurs de disposition. 

Chaque zone de la scène, dédiée à une sous-fonction devrait être réunie dans un acteur de disposition (un empilement en général).
Ce sera utile par la suite pour réaliser des modifications de disposition sans avoir à tout retoucher.

Il faut vraiment profiter des arborescences d'acteurs pour bien organiser les différentes portions d'une scène :
 - celles qui sont fixes
 - celles dont le contenu risque de changer

Cela vous permettra d'identifier des sous-scènes et donc de prévoir d'utiliser de la navigation avec un acteur écran (ou même plusieurs).

### Les images, textes et couleurs

> Prévoyez à l'avance les différentes images et autres ressources graphiques.

> Identifiez les textes qui vont se répéter.

> Identifiez les couleurs et thèmes de l'interface.


Tout ces objets vont devoir être mis en librairies. Plus tôt ils sont définis, plus tôt ils seront utilisés dans votre projet et moins de modifications vous aurez à répéter pour en créer une fois que la SynApp est bien avancée.

### Les données

Préparez vos ressources sur le REDY de manière à créer le moins possible de sources de donnée dans la SynApp.

L'idéal et de les regrouper par les scènes qui les utiliseront ou zones de scène pour pouvoir utiliser la ressource parente comme une source de donnée.


## Dans le Maker


### acteurs

#### Les toiles

Il faut utiliser les toiles dans le cas où des acteurs doivent se superposer (une image de fond et des acteurs dessus par exemple).

> N'utilisez jamais d'unité relative dans les toiles.

Les unités relatives (em, vmin, vh, vmax, vw) sont à proscrire dans les toiles. Utilisez uniquement le px. S'il faut adapter la toile à l'écran, placez la toile dans une boite à vue.



*(...)*

### scènes & composites

*(...)*

## Utilisation des librairies

*(...)*

### les images

*(...)*

### les textes

*(...)*

## les liaisons

*(...)*

## Les sources de données

*(...)*


## Propriété et valeur par défaut

*(...)*

## Propriétés additionnelles

*(...)*

## Les spécificités des équipements nomades

Voici quelques éléments qui vous seront utiles pour entrer plus facilement dans le monde des applications dédiées aux plateformes nomades : les smartphones et les tablettes.
Ces équipements ont des contraintes et des possibilités qui sont non triviales, surtout pour ceux qui sont habitués à des plateformes plus classiques comme celle du PC.

### Tailles d’écran réduites et divers
*(...)*

### Interactions tactiles 
*(taille des zones à toucher, moins de fonctionnalité que l’interaction souris)*

*(...)*

### Performances variable
*navigateur android variable (mauvaise sur certains appareils)*

*(...)*

### Intimité d'usage 
*Besoin d'affichage plus synthétique (l'essentiel est présenté, on navigue pour entrer dans les détails)*

*(...)*

### Qualité de réseau très variable

*que ce soit en WIFI ou 3G/4G*

*(...)*


### mise en pratique

#### la navigation

#### le nombre d'acteurs

