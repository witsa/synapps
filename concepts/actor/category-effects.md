---
title: "Catégorie Effets"
parent: Acteur
grand_parent: Concepts
nav_order: 7
---

{% include table_of_content.html %}


# Catégorie Effets

Cette catégorie regroupe les propriétés relatives à la disposition de l'acteur.

{% assign sorted = site.base_actor_properties | where: 'section', 'effects' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
