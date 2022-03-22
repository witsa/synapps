---
title: "Interaction | Zone de texte"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="Actor.Input.TextArea" %}

# Zone de texte

L'acteur Zone de texte permet de renseigner du texte, il est généralement utilisé pour écrire du texte brut.

{% include table_of_content.html %}

# Propriétés spécifiques

{% assign sorted = site.input_text_area_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}