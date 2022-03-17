---
title: "Affichage | Texte"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

Acteur de base pour afficher du texte.

[&#x1F4BB; Actor.Display.Text]({{ site.baseurl }}/script-api/Actor.Display.Text.html){:target="_blank"}

Son contenu est **jokerable**.

# Propriétés spécifiques

{% assign sorted = site.display_text_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Champs d'informations

## Contenu complété

{% include field_completed_content.md %}
