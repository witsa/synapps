---
title: "Interaction | Liste de Cases à cocher"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="Actor.Input.CheckboxList" %}

# Liste de cases à cocher

Acteur d'interaction qui permet d'afficher une liste de cases à cocher. Cette liste peut être une arborescence. L'acteur possède deux modes de sélection : simple et multiple.

{% include table_of_content.html %}

# Propriétés

## Sélection

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

## Multi sélection
La propriété *Multi sélection?* permet de définir si l'acteur est en mode sélection multiple ou non.

Dans le cas de la multi sélection, la propriété *Avec l'option Tout* permet de définir si l'option "Tout" est présente dans la liste. La propriété *Texte pour Tout* permet de définir le texte qui s'affiche dans l'option "Tout".

## Les options

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

## État de validation

{% include property_validation.md %}

## Taille

{% include property_size.md %}

# Champs d'information

Les champs d'information suivants sont très utiles pour réaliser des liaisons ou dans les scripts dans la mesure ou les propriétés de l'acteur ici sont souvent des chaines JSON.

## Valeur et Valeurs

En mode sélection simple, le champ d'information *Valeur* contient simplement la valeur sélectionnée. Dans le mode multi sélection, le champ d'information *Valeurs* contient la liste des valeurs sélectionnées sous forme de tableau `Javascript`.

## Texte et Textes

De la même manière que pour les valeurs, le champ d'information *Texte* et  *Textes* contient respectivement le texte sélectionné et le tableau des textes sélectionnés.

## Liste des options

Le tableau des options est accessible dans le champ d'information *Liste des options*.

# Événements

## `onSelected`

L'évènement `onSelected` est déclenché lorsque la sélection change.

> [&#x1F4BB; `onSelected`]({{ site.baseurl }}/script-api/Actor.Input.CheckboxList.html#event:onSelected){:target="_blank"}
