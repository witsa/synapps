---
title: "Affichage | Image"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

Un acteur qui permet d'afficher une image.

[&#x1F4BB; Actor.Display.Image]({{ site.baseurl }}/script-api/Actor.Display.Image.html){:target="_blank"}

# Propriétés spécifiques

{% assign sorted = site.display_picture_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}
