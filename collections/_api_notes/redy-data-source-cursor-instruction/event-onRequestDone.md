---
api_type: redy/data-source/cursor-instruction
kind: event
name: onRequestDone
---
Événement déclenché lorsque l'instruction est terminée et que les résultats sont disponibles.

Dans `data`, vous trouverez un objet avec les propriétés suivantes :

| Propriété | Type   | Description                         |
| --------- | ------ | ----------------------------------- |
| totalRows | Nombre | Le nombre total de lignes impactées |

En cas d'erreur, un champ `error` est présent dans l'objet de contexte avec les informations de l'erreur.
