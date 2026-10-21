---
title: "Liste de boutons"
parent: "Boutons"
grand_parent: "Intéraction"
api_type: input/button-list
nav_order: 2
redirect_from:
  - /script-api/Actor.Input.ButtonList.html
  - /script-api/Actor.Input.ButtonListProperties.html
  - /script-api/synapps-ui_addon_components_actors_input_button-list-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_input_button-list.js.html
---

# Liste de boutons
Liste de boutons pour faire un choix simple. La liste est construite dynamiquement à partir d'une liste d'[options](#options).

**NOTE**
Il n'est pas possible de sélectionner plusieurs boutons en même temps.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Informations
{: #informations }

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

{% include script_api/fields.md type=page.api_type %}

# Événements
{: #evenements }

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/scripts/reference/actor.html).

{% include script_api/events.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
