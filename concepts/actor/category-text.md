---
title: "Catégorie Texte"
parent: Acteur
grand_parent: Concepts
---

{% include table_of_content.html %}


# Catégorie Texte

Cette catégorie regroupe les propriétés relatives au texte de l'acteur.

{% assign sorted = site.base_actor_properties | where: 'section', 'text' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
