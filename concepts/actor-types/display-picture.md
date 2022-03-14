---
title: "Affichage | Image"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Propriétés spécifiques

{% assign sorted = site.display_picture_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}