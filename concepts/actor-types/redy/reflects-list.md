---
title: "Liste de reflets"
parent: "Reflets"
grand_parent: "REDY"
api_type: redy/reflect-list
nav_order: 1
---

# Liste de reflets

L'acteur *Liste de reflets* affiche, page par page, les reflets du REDY, filtrés selon ses propriétés. Le reflet sélectionné dans la liste est accessible par script ; sa modification déclenche l'évènement `onSelectChange`.

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
