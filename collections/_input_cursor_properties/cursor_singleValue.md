---
title: Valeur unique
section: input
propName: ActorButtonCursorSingleValue
propPath: properties.Actor.input.Cursor
scriptApiClass: Actor.input.Cursor
order: 2
---
La propriété spécifique `Valeur unique?` permet d'activer un deuxième curseur sur l'acteur.

Cela va avoir pour effet d'ajouter à l'acteur une propriété `Valeur 2` qui fonctionne comme la propriété spécifique `Valeur` et qui va permettre de définir une intervalle.

Si cette propriété est activée, la propriété spécifique `Valeur` devient la borne inférieure et la propriété spécifique `Valeur 2` devient la borne supérieure.

Il est à noter que la borne inférieur ne peut pas dépasser la borne supérieur et inversement.

Lorsque la propriété est activée, il apparait également deux nouvelles propriétés spécifiques :
`Différence min.` : Permet de définir un écart minimal entre `Valeur` et `Valeur 2`
`Différence max.` : Permet de définir un écart maximal entre `Valeur` et `Valeur 2`


**ATTENTION**
Il est possible de définir la `Valeur` au dessus de la borne supérieur et `Valeur 2` en dessous de la borne inférieur cependat, il est conseiller de définir des valeur comprises dans les bornes définies.

De même, la `Valeur` et la `Valeur 2` peuvent ne pas respecter les `Différence min.` et `Différence max.` lorsqu'elles sont renseignées manuellement, il est tout de même conseillé de mettre des valeur avec un écart respectant les différences définies.