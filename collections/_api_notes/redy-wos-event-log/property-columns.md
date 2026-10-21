---
api_type: redy/wos-event-log
kind: property
name: columns
---
Dans l'entête du tableau vous trouverez les définitions des colonnes. La liste des colonnes est paramétrable. C'est pour l'instant un tableau de clé en JSON :

```json
["id", "ack", "icon", "date", "nod", "site", "state", "todo"]
```

| clé de colonne | Description |
| ---- | ------|
| `id` | Index de l'évènement |
| `ack` | Acquittement |
| `icon` | Icône de l'évènement |
| `date` | Date de l'évènement |
| `nod` | Variable à l'origine de l'évènement |
| `site` | Site de l'élément à l'origine de l'évènement |
| `state` | État de la ressource |
| `todo` | Consigne |

Laissez vide la propriété *Colonnes* pour les afficher toutes.
