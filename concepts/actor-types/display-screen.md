---
title: "Affichage | Ecran"
parent: "Types d'acteur"
grand_parent: Concepts
---

> 🚧 en cours de rédaction...

{% include links_actor.md apiClass="Actor.Display.Screen" %}

# Écran

Acteur qui permet d'afficher une autre scène.

{% include table_of_content.html %}

# Propriétés spécifiques

{% assign sorted = site.display_screen_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

## Dépassement de contenu

{% include property_overflow.md %}

> ![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_screen/showHide.PNG)

La valeur par défaut est **Défilement**

# Champ d'information

## Scène affichée
La scène affichée par l'acteur écran est stockée dans la propriété `displayedScene` disponible par liaison et par script.

# évènements spécifiques

> 🚧 en cours de rédaction...
