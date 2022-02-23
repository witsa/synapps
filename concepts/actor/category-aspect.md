---
title: "Catégorie Aspect"
parent: Acteur
grand_parent: Concepts
---

{% include table_of_content.html %}


# Catégorie Aspect

Cette catégorie regroupe les propriétés relatives à l'aspect de l'acteur.

{% assign sorted = site.base_actor_properties | where: 'section', 'aspect' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
