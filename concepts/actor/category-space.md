---
title: "Catégorie Marges"
parent: Acteur
grand_parent: Concepts
nav_order: 5
---

{% include table_of_content.html %}


# Catégorie Espaces

Cette catégorie regroupe les propriétés relatives aux marges de l'acteur.

{% assign sorted = site.base_actor_properties | where: 'section', 'space' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
