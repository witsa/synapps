---
api_type: input/checkbox-list
kind: property
name: values
---
La propriété *Sélection* est une chaîne `JSON` qui contient la liste des valeurs sélectionnées. Dans le cas de la sélection simple, la liste ne contient qu'une seule valeur à la fois.

Exemples en multi sélection:

<div class="code-example" markdown="1">
les options 1 et 2 sont sélectionnées
</div>

```json
["value1", "value2"]
```

<div class="code-example" markdown="1">
Aucune valeur n'est sélectionnée :
</div>

```json
[]
```

<div class="code-example" markdown="1">
Si la propriété *Tout est la valeur vide?* est activée, toutes les options sont sélectionnées :
</div>

```json
null
```

En mode de sélection simple, le format de la sélection reste le meme.

Par exemple : `["value1"]` ou bien `[]`.
