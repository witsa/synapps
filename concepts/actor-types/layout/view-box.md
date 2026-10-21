---
title: "Boite à vue"
parent: "Disposition"
grand_parent: "Types d'acteur"
api_type: layout/view-box
nav_order: 3
redirect_from:
  - /script-api/Actor.Layout.ViewBox.html
  - /script-api/Actor.Layout.ViewBoxProperties.html
  - /script-api/synapps-ui_addon_components_actors_layout_view-box-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_layout_view-box.js.html
---

# Boite à vue

Acteur qui permet de disposer un acteur enfant en l'adaptant à sa taille.

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

La boite à vue est un acteur très pratique pour afficher un contenu de taille fixe tout en s'assurant qu'il sera visible quelque soit la taille de l'écran.

Par exemple, vous pouvez construire tout une superposition d'un plan avec des éléments positionnés précisément par rapport à lui au pixel prés. Ensuite, vous le placerez dans une boite à vue pour qu'il soit visible quelque soit la taille de l'écran.

{: .warning }
> Ne définissez pas des tailles avec des [unites](../../sizes.md) relatives dans les acteurs qui sont à l'intérieure d'une boite à vue. En effet, le résultat sera difficilement prévisible.
>
> **Utiliser toujours des unités fixes : `px`, `cm` et `in`.**
