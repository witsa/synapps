---
title: "Interaction | Bouton de Navigation"
parent: "Types d'acteur"
grand_parent: Concepts
---

> 🚧 en cours de rédaction...

{% include links_actor.md apiClass="Actor.Input.NavButton" %}

# Bouton de Navigation

L'acteur bouton de navigation permet, en plus de toutes les possibilités de l'[acteur bouton](./input-button.md), de naviguer entre les scènes ainsi que de modifier la scène affichée dans un [acteur écran](./display-screen.md).

Ses propriétés sont similaires aux propriétés de l'acteur bouton et la documentation de ces propriétés peut être retrouvée à [cette adresse](./input-button.md).

Ses propriétés supplémentaires sont listées ci-dessous.

{% include table_of_content.html %}

# Propriétés spécifiques

{% assign sorted = site.input_nav_button_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Évènements spécifiques

> 🚧 en cours de rédaction...

# Variantes

## Icône

La variante de l'acteur bouton offrant la possibilité d'intégrer une icône choisie parmi les icônes intégrées à Synapps.

Le contenu du bouton est complété par une additionnelle *icône* et une additionnelle *texte*.
