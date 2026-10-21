---
api_type: redy/data-source/wos-relative-variable
kind: property
name: writeOnChange
---
Cette propriété active/désactive l'enregistrement de la valeur d'une variable dans le REDY si la *donnée* est modifiée par liaison ou par script. Il faut bien entendu que ce soit le *champ* ***Valeur*** qui soit inscrit dans la donnée.

Aussi, pour déclencher l'enregistrement de la donnée changée dans le REDY, il faudra appeler la méthode ⚡ `write()` de l'acteur.
