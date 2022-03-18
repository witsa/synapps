---
title: "Interaction | Liste de choix déroulante"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="Actor.Input.DropdownList" %}

# Liste de choix déroulante

Acteur d'interaction qui permet d'afficher une liste de choix déroulante.

{% include table_of_content.html %}

# Propriétés

## Sélection

La propriété *Sélection* est une chaîne qui la valeur qui correspond au choix dans la liste des options.

Exemples:

<div class="code-example" markdown="1">
l'option 1 est sélectionnée :
</div>

```text
value1
```

Aucune valeur n'est sélectionnée si la valeur est une chaîne vide.

## Valeur vide?

Un option *vide* peut être ajouté automatiquement en plus de la liste des options. Cela correspond à la valeur `` chaîne vide.

Si vous ajouter un texte dans la propriété *Texte pour vide*, il s'affichera dans la listes des options en premier à la place de la chaîne vide.

Le texte défini dans la propriété *Texte si vide* s'affichera dans l'acteur si rien n'est sélectionné.

## Les options

La propriété *Options* est une chaîne `JSON` qui contient un tableau d'options.

Une option est un object `JSON` qui possède les propriétés suivantes :

| CHAMPS | DESCRIPTION | PAR DÉFAUT |
|--------|-------------|------------|
| `value` | La valeur de l'option. C'est son identifiant unique dans la liste. De préférence, la valeur est une chaîne de caractères. | - |
| `text` | Le texte qui s'affiche à coté de la case à cocher. | - |
| `disabled` | Indique si l'option doit apparaître désactivée. | `false` |

Exemple :

<div class="code-example" markdown="1">

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_dropdown_list/sample01.png)


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

## État de validation

{% include property_validation.md %}

## Taille

{% include property_size.md %}

# Champs d'information

## Texte sélectionné

Le champ d'information *Texte sélectionné* contient le texte correspondant à l'option sélectionné.

## Liste des options

Le tableau des options est accessible dans le champ d'information *Liste des options*.

# Événements

## `onSelected`

L'évènement `onSelected` est déclenché lorsque la sélection change.

> [⚡ `onSelected`]({{ site.baseurl }}/script-api/Actor.Input.DropdownList.html#event:onSelected){:target="_blank"}
