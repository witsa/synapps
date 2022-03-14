---
title: Echelle
section: effects
propName: scaling
propPath: properties.scaling
scriptApiClass: Actor.BaseActorProperties
order: 3
---
Cette propriété permet de définir de modifier la taille de l'acteur.

La valeur attendue est un nombre positif OU négatif.
Lorsque le nom est compris dans l'intervalle [-1,1], l'élément est réduit.
Lorsque la valeur est négative, l'élément est inversé par symétrie centrale.

Dans l'inspecteur, le champ de saisie agit également comme un slider, permettant de changer la valeur en faisant glisser la souris vers la droite pour augmenter la valeur et vers la gauche pour diminuer la valeur.

**Pour vous aider :**
La propriété définie la valeur de la fonction 'scale()' en CSS dont la documentation est disponible [à cette adresse](https://developer.mozilla.org/fr/docs/Web/CSS/transform-function/scale()).

***ATTENTION***
Il n'est pas possible de renseigner deux valeurs comme montré dans la documentation CSS.
