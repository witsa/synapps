---
title: Dessinez !
parent: Bonnes et Mauvaises pratiques
grand_parent: Documentation Maker
nav_order: 1
search_exclude: true
---

{% include table_of_content.html %}


# Avant d'ouvrir le Maker : Dessinez !

Quelques éléments sur les étapes à réaliser **avant** d'ouvrir le Maker afin de construire la SynApp sereinement.

## La maquette

La première chose à faire avant d'ouvrir le Maker est de réaliser un dessin ou maquette de l'interface désirée.
Cela évitera bien des écueils et donc de perdre du temps.
Cela permettra :
 - de mieux définir les fonctionnalités attendues,
 - de mieux prévoir les temps de réalisation
 - et d'identifier des briques à réutiliser.

> Un simple petit croquis peut faire gagner énormément de temps.

Il ne faut pas non plus hésiter à inclure le client dans cette étape.

## Découpage en Scènes

Toujours sur papier, Préparez votre SynApp en la découpant en plusieurs scènes.

> Une idée/fonctionnalité majeure par scène.

Il sera toujours plus facile de réunir des fonctionnalités sur une même scène que de les diviser plus tard.

Cela va permettre aussi de réutiliser des fonctionnalités similaires sur plusieurs endroits de la SynApp sans avoir à les refaire à chaque fois.

C'est encore plus important avec les interfaces dédiées aux plateformes nomades où la fonction de l'écran doit être facilement identifiable et accessible.

## La Mise en Scène des acteurs.

> Découpez vos scènes zone avec les acteurs de disposition.

Chaque zone de la scène, dédiée à une sous-fonction devrait être réunie dans un acteur de disposition (un empilement en général).
Ce sera utile par la suite pour réaliser des modifications de disposition sans avoir à tout retoucher.

Il faut vraiment profiter des arborescences d'acteurs pour bien organiser les différentes portions d'une scène :
 - celles qui sont fixes
 - celles dont le contenu risque de changer

Cela vous permettra d'identifier des sous-scènes et donc de prévoir d'utiliser de la navigation avec un acteur écran (ou même plusieurs).

## Les images, textes et couleurs

> Prévoyez à l'avance les différentes images et autres ressources graphiques.

> Identifiez les textes qui vont se répéter.

> Identifiez les couleurs et thèmes de l'interface.


Tout ces objets vont devoir être mis en librairies. Plus tôt ils sont définis, plus tôt ils seront utilisés dans votre projet et moins de modifications vous aurez à répéter pour en créer une fois que la SynApp est bien avancée.

## Les données

Préparez vos ressources sur le REDY de manière à créer le moins possible de sources de donnée dans la SynApp.

L'idéal et de les regrouper par les scènes qui les utiliseront ou zones de scène pour pouvoir utiliser la ressource parente comme une source de donnée.
