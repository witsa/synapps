---
title: "Empilement"
parent: "Disposition"
grand_parent: "Types d'acteur"
api_type: layout/stack
nav_order: 1
redirect_from:
  - /script-api/Actor.Layout.Stack.html
  - /script-api/Actor.Layout.StackProperties.html
  - /script-api/synapps-ui_addon_components_actors_layout_stack-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_layout_stack.js.html
---


# Empilement

Acteur qui permet de disposer ses acteurs enfants en les empilant, soit verticalement, soit horizontalement.

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

# Disposition

Voir les règles de disposition avec les [propriétés d'alignement vertical et horizontal](../../actor/category-disposition.md#catégorie-disposition-flexible)

# Usage

L'empilement avec les règles de [disposition flexibles](../../actor/category-disposition.md#catégorie-disposition-flexible) sont à la base de la construction d'interface qui peuvent s'adapter à n'importe quelle taille d'écran.
Associées à la disposition par [Toile](./canvas.md) et la [Boite à vue](./view-box.md), ces acteurs permettent de construire n'importe quel type de gabarit.
