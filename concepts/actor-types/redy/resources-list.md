---
title: "Liste d'états"
parent: "Variable WOS"
grand_parent: "REDY"
nav_order: 1
api_type: redy/wos-state-list
---

# Liste d'états

L'acteur *Liste d'états* affiche dans un tableau paginé les ressources du REDY avec leur état. Un clic sur une ligne sélectionne la ressource (`selectedResource`) et déclenche l'évènement `onSelected`.

{% include table_of_content.html %}

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
