---
api_type: redy/reflect-details
kind: event
name: onRequestDone
---
L'évènement `onRequestDone` est déclenché lorsque l'acteur a terminé une requête vers le REDY pour obtenir ou rafraîchir le reflet.

L'évènement comporte un objet `context` avec les propriétés suivantes :
- `data`  : Le reflet obtenu du REDY, cet objet contient toutes les informations relative au reflet (nom, chemin, etc ...).
- `error` : Un message d'erreur si la requête a échoué, ou `null` si elle a réussi.
