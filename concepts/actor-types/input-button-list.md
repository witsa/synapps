---
title: "Interaction | Liste de bouton"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

Liste de boutons pour faire un choix simple. La liste est construite dynamiquement à partir d'une liste d'[options](#options).

[&#x1F4BB; Actor.Input.ButtonList]({{ site.baseurl }}/script-api/Actor.Input.ButtonList.html){:target="_blank"}

**NOTE**
Il n'est pas possible de sélectionner plusieurs boutons en même temps.

# Propriétés spécifiques

{% assign sorted = site.input_button_list_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Informations

## Texte sélectionné
> en cours de rédaction...


# Évènements spécifiques

> en cours de rédaction...
