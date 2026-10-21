---
title: "Barre de navigation"
parent: "Navigation"
grand_parent: "Intéraction"
api_type: layout/navbar
nav_order: 5
---

{% include table_of_content.html %}

# Barre de navigation

Menu de navigation horizontal. Il regroupe des [boutons de menu](./menu-button.md) et des [groupes de barre de navigation](./navbar-group.md), et porte la scène sélectionnée.

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Informations
{: #informations }

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

{% include script_api/fields.md type=page.api_type %}

# Méthodes
{: #methodes }

{% include script_api/methods.md type=page.api_type %}

# Événements
{: #evenements }

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/scripts/reference/actor.html).

{% include script_api/events.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
