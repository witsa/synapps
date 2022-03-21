---
title: "Interaction | Boite de saisie "
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="Actor.Input.TextBox" %}

# Boite de saisie

L'acteur boite de saisie permet de créer des champs de saisies personnalisables.

{% include table_of_content.html %}

# Propriétés spécifiques

{% assign sorted = site.input_text_box_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}