---
title: "Liste de bouton"
parent: "Boutons"
grand_parent: "Intéraction"
api_type: input/button-list
nav_order: 2
---

{% include links_actor.md apiClass="Actor.Input.ButtonList" %}

# Liste de bouton

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
