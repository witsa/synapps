---
title: "Affichage | Ecran"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

Acteur qui permet d'afficher une autre scène.

[&#x1F4BB; Actor.Display.Screen]({{ site.baseurl }}/script-api/Actor.Display.Screen.html){:target="_blank"}

# Propriétés spécifiques

{% assign sorted = site.display_screen_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

## Dépassement de contenu

Les propriétés *Dépassement vertical* et *Dépassement horizontal* permettent de gérer le comportement de l'acteur écran vis à vis d'un dépassement éventuel de la scène montrée.

Si l'acteur écran dispose d'une taille figée *OU* est contrainte par un autre élément (acteur parent par exemple), alors, les propriétés *Dépassement horizontal* et *Dépassement vertical* s'appliquent.

Il existe quatre options pour chacune de ces propriétés :
- **Caché**

Le contenu de l'acteur écran qui ne dispose pas de suffisamment de place pour s'afficher ne sera pas visible et ses éléments ne seront pas accessibles.

- **Visible**

Le contenu de l'acteur écran qui ne dispose pas de suffisamment de place est affiché en dehors de l'emplacement prévu pour l'acteur.

Attention, si un autre acteur chevauche ce dépassement, la partie qui dépasse sera cachée par cet acteur.

> Il faut noter que les deux propriétés doivent être `Visible` afin d'obtenir le comportement souhaité.

- **Défilement** *(défaut)*

Permet d'ajouter une *scrollbar* à la scène afin de pourvoir acceder à ses éléments qui dépassent.

- **Automatique**

Affiche une *scrollbar* uniquement s'il existe un dépassement.

> **ATTENTION**<br>
> Les options `Visible` et `Caché` ne sont pas compatibles entres elles.
>
> Cet exemple ne fonctionne pas :
>
> ![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_screen/showHide.PNG)

# Champ d'information

## Scène affichée
La scène affichée par l'acteur écran est stockée dans la propriété `displayedScene` disponible par liaison et par script.

# évènements spécifiques

> en cours de rédaction...
