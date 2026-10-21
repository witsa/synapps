---
title: "Liste de choix"
parent: "Formulaire"
grand_parent: "Intéraction"
api_type: input/radio-list
nav_order: 6
redirect_from:
  - /script-api/Actor.Input.RadioList.html
  - /script-api/Actor.Input.RadioListProperties.html
  - /script-api/synapps-ui_addon_components_actors_input_radio-list-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_input_radio-list.js.html
---

# Liste de choix

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_radio_list/sample01.gif)

Acteur d'interaction qui permet d'afficher une liste d'options matérialisées par des boutons radio, empilés horizontalement ou verticalement. Une seule option peut être sélectionnée à la fois.

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
