---
title: "Catégorie Marges"
parent: Acteur
grand_parent: Concepts
---

{% include table_of_content.html %}


# Catégorie Marges

Cette catégorie regroupe les propriétés relatives aux marges de l'acteur.

{% assign sorted = site.base_actor_properties_space | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

