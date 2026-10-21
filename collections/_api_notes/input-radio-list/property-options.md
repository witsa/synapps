---
api_type: input/radio-list
kind: property
name: options
---
La propriété *Options* est une chaîne `JSON` qui contient un tableau d'options.

Une option est un object `JSON` qui possède les propriétés suivantes :

| CHAMPS | DESCRIPTION | PAR DÉFAUT |
|--------|-------------|------------|
| `value` | La valeur de l'option. C'est son identifiant unique dans la liste. De préférence, la valeur est une chaîne de caractères. | - |
| `text` | Le texte qui s'affiche à côté du bouton radio. | - |
| `disabled` | Indique si l'option doit apparaître désactivée. | `false` |

Exemple :

<div class="code-example" markdown="1">

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_radio_list/sample01.gif)

</div>

```json
[
  {
    "value": "value1",
    "text": "Option 1"
  },
  {
    "value": "value2",
    "text": "Option 2"
  },
  {
    "value": "value3",
    "text": "Option 3"
  }
]
```
