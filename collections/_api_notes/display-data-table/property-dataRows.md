---
api_type: display/data-table
kind: property
name: dataRows
---
Cette propriété permet de renseigner un tableau d'objets JSON représentant les lignes de données à afficher dans le tableau de données.

Exemple de données JSON pour cette propriété :
{% raw %}

```json
[
  {
    "name": "Robert",
    "age": 23,
    "hasLicence": false
  },
  {
    "name": "Valerie",
    "age": 26,
    "hasLicence": true
  },
  {
    "name": "Bob",
    "age": 32,
    "hasLicence": true
  }
]
```

{% endraw %}

Le JSON est stucturé sous la forme d'un tableau d'objets, chaque objet représentant une ligne de données. Chaque propriété de l'objet représente une colonne potentielle du tableau de données.
