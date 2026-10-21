---
title: "Menu de navigation"
parent: "Navigation"
grand_parent: "Intéraction"
redirect_from:
  - /concepts/actor-types/layout/layout-nav-menu.html
api_type: layout/nav-menu
nav_order: 2
---

{% include links_actor.md apiClass="Actor.Layout.NavMenu" %}

# Menu de navigation

Le **Menu de navigation** est le conteneur principal qui gère l’état de la navigation. Il porte la scène sélectionnée et distribue les styles actif/inactif à ses enfants (groupes et boutons).

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

{: .info }
>
> Les styles actif/inactif sont les styles définis sur l’acteur **Bouton de menu**.

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
