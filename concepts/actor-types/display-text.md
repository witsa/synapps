---
title: "Affichage | Texte"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="Actor.Display.Text" %}

# Texte

Acteur de base pour afficher du texte.

{% include table_of_content.html %}

Son contenu est **jokerable**.

# Propriétés spécifiques

{% assign sorted = site.display_text_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Champs d'informations

## Contenu complété

{% include field_completed_content.md %}
