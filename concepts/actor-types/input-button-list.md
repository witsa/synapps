---
title: "Interaction | Liste de bouton"
parent: "Types d'acteur"
grand_parent: Concepts
---


{% include table_of_content.html %}

# Propriétés spécifiques

{% assign sorted = site.input_button_list_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}