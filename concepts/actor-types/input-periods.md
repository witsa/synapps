---
title: "Interaction | Périodes"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="Actor.Input.Period" %}

# Périodes

L'acteur *Période* propose une sélection de périodes types et expose les bornes de date correspondantes à la période sélectionnée.

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_period/sample01.gif)

{% include table_of_content.html %}

L'acteur *Période* a beaucoup de similitudes avec l'acteur *Liste de boutons* et propose la plupart de ses propriétés (*En ligne?*, *Taille*, ...).

# Propriétés

## Sélection

La propriété `Selection` reflète la valeur sélectionnée en cours.

La valeur attendue est la `value` de l'une des [options][#options] de l'acteur parmi :

| - | - | - |
| `all` | Tout |
| `today` | Aujourd'hui |
| `last24` | Dernières 24H |
| `week` | Semaine en cours |
| `weekprevious` | Semaine dernière |
| `month` | Mois en cours |
| `monthprevious` | Mois dernier |
| `year` | Année en cours |
| `yearprevious` | Année dernière |

## Taille

{% include property_size.md %}

## Périodes présentes

Cette propriété permet de définir les périodes présentes et leur ordre d'apparition dans l'acteur sous la forme d'un tableau `JSON` des valeurs possible. Par ex:
```json
[ "today", "last24", "week", "weekprevious", "month", "monthprevious", "year", "yearprevious" ]
```

# Champs d'information

## Date de début

Ce champ contient la date de début (format ISO) de la période sélectionnée. S'il n'y a pas de période sélectionnée, ou que par définition, elle n'a pas de début, la valeur est `null`.

## Date de fin

Ce champ contient la date de fin (format ISO) de la période sélectionnée. S'il n'y a pas de période sélectionnée, ou que par définition, elle n'a pas de fin, la valeur est `null`.

## Texte sélectionné

Le champ d'information *Texte sélectionné* contient le texte correspondant à l'option sélectionné.

## Liste des options

Le tableau des options est accessible dans le champ d'information *Liste des options*.

# Événements

## `onSelected`

L'évènement `onSelected` est déclenché lorsque la sélection change.

> [&#x1F4BB; `onSelected`]({{ site.baseurl }}/script-api/Actor.Input.Period.html#event:onSelected){:target="_blank"}
