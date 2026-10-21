---
api_type: redy/data-source/cursor-request
kind: event
name: onRequestDone
---
Événement déclenché lorsque la requête est terminée et que les données sont disponibles.

Dans `data`, vous trouverez un objet avec les propriétés suivantes :

| Propriété | Type                | Description                                                                                                |
| --------- | ------------------- | ---------------------------------------------------------------------------------------------------------- |
| columns   | Tableau de Colonnes | Tableau contenant les définitions des colonnes                                                             |
| rows      | Tableau de tableaux | Les lignes de résultats, chaque ligne étant un tableau de valeurs correspondant aux colonnes, dans l'ordre |
| totalRows | Nombre              | Le nombre total de lignes disponibles (avant application de la limite et du décalage)                      |

L'objet de Colonne contient les propriétés suivantes :

| Propriété | Type   | Description                      |
| --------- | ------ | -------------------------------- |
| key       | Chaîne | Le nom unique de la colonne      |
| type      | Chaîne | Le type de données de la colonne |

En cas d'erreur, un champ `error` est présent dans l'objet de contexte avec les informations de l'erreur.

Exemple de données retournées :

```json
{
  "columns": [
    { "key": "id", "type": "Integer" },
    { "key": "name", "type": "String" }
  ],
  "rows": [
    [1, "Alice"],
    [2, "Bob"]
  ],
  "totalRows": 50
}
```
