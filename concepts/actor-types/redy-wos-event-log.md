---
title: "REDY | Journal des variables"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="REDY.Actor.WosEventLog" %}

# Journal des variables

L'acteur *Journal des variables* affiche un tableau contenant  les évènements de journaux du REDY.


# Propriétés

## Rafraîchissement

Le journal est mis à jour suivant un délai qui est paramétrable. Ce rafraîchissement peut être désactivé.

## Entête et pagination

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
| `todo` | ? |

Laissez vide la propriété *Colonnes* pour les afficher toutes.

Une propriété permet de faire disparaître l'entête.


La liste des évènements est paginée, c'est-à-dire que seul un nombre paramétrable est affichée en même temps. Des boutons permettent de naviguer de page en page.

Une propriété permet de faire disparaître les boutons de pagination.

## Les filtres

Vous pouvez choisir de filtrer les évènements dans le temps, ne voir que les encours, par attributs (groupe, ensemble, zone, ...) ou même par variable.

# Événements

## `onRequestDone`

L'évènement `onRequestDone` est déclenché lorsque l'acteur a terminé une requête vers le REDY pour obtenir ou rafraîchir la liste à afficher.

> [⚡ `onRequestDone`]({{ site.baseurl }}/script-api/REDY.Actor.WosEventLog.html#event:onSelected){:target="_blank"}

# Exemples

## Journal avec selection de période de temps :

> TODO
