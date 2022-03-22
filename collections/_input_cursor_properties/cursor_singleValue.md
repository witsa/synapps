---
title: Valeur unique
section: specifics
propName: isSingleValue
propPath: properties.isSingleValue
scriptApiClass: Actor.input.CursorProperties
order: 2
---
La propriété spécifique `Valeur unique?` permet d'activer / désactiver un deuxième curseur sur l'acteur.

Il est possible de désactiver cette propriété afin d'activer un second curseur sur l'acteur.

Cela va avoir pour effet d'ajouter à l'acteur une propriété `Valeur 2` qui fonctionne comme la propriété spécifique `Valeur` et qui va permettre de définir une intervalle.

Si un second curseur est présent, la propriété spécifique `Valeur` devient la borne inférieure et la propriété spécifique `Valeur 2` devient la borne supérieure.

Il est à noter que la borne inférieure ne peut pas dépasser la borne supérieure et inversement.

Lorsque la propriété est activée, il apparaît également deux nouvelles propriétés spécifiques :
<br>
`Différence min.` : Permet de définir un écart minimal entre `Valeur` et `Valeur 2`
<br>
`Différence max.` : Permet de définir un écart maximal entre `Valeur` et `Valeur 2`


>⚠️ **ATTENTION**<br>
Il est possible de définir la `Valeur` au dessus de la borne supérieure et `Valeur 2` en dessous de la borne inférieure cependant, il est conseillé de définir des valeurs comprises dans les bornes définies.

De même, la `Valeur` et la `Valeur 2` peuvent ne pas respecter les `Différence min.` et `Différence max.` lorsqu'elles sont renseignées manuellement, il est tout de même conseillé de mettre des valeur avec un écart respectant les différences définies.
