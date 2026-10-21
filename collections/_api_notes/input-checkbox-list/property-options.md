---
api_type: input/checkbox-list
kind: property
name: options
---
La propriété *Options* est une chaîne `JSON` qui contient un tableau d' options.

Une option est un object `JSON` qui possède les propriétés suivantes :

| CHAMPS | DESCRIPTION | PAR DÉFAUT |
|--------|-------------|------------|
| `value` | La valeur de l'option. C'est son identifiant unique dans la liste. De préférence, la valeur est une chaîne de caractères. | - |
| `text` | Le texte qui s'affiche à coté de la case à cocher. | - |
| `disabled` | Indique si l'option doit apparaître désactivée. | `false` |
| `options` | Un tableau d'options qui sera affiché sous la case à cocher pour fabriquer une arborescence. | `null` |
| `collapsed` | Indique si la case à cocher doit enrouler ses options éventuelles. | `false` |

Exemple :

<div class="code-example" markdown="1">

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_checkbox_list/sample01.png)



</div>

```json
[
  {
    "value": "item1",
    "text": "Élément 1"
  },
  {
    "value": "item2",
    "text": "Élément 2",
    "options": [
      {
        "value": "sub2Item1",
        "text": "Sous élément 1"
      },
      {
        "value": "sub2Item2",
        "text": "Sous élément 2"
      }
    ]
  },
  {
    "value": "item3",
    "text": "Élément 3",
    "collapsed": true,
    "options": [
      {
        "value": "sub3Item1",
        "text": "Sous élément 1",
        "disabled": true,
        "options": [
          {
            "value": "sub3sub1Item1",
            "text": "Sous sous élément 1"
          },
          {
            "value": "sub3sub1Item2",
            "text": "Sous sous élément 2"
          }
        ]
      },
      {
        "value": "sub3Item2",
        "text": "Sous élément 2"
      }
    ]
  }
]
```
