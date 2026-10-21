---
title: "Bouton de navigation"
parent: "Navigation"
grand_parent: "Intéraction"
api_type: input/nav-button
nav_order: 1
---

{% include links_actor.md apiClass="Actor.Input.NavButton" %}

# Bouton de navigation
L'acteur bouton de navigation permet, en plus de toutes les possibilités de l'[acteur bouton](./button.md), de naviguer entre les scènes ainsi que de modifier la scène affichée dans un [acteur écran](../display/screen.md).

Ses propriétés sont similaires aux propriétés de l'acteur bouton et la documentation de ces propriétés peut être retrouvée à [cette adresse](./button.md).

Ses propriétés, dont celles héritées du bouton, sont listées ci-dessous.

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

# Presets

## Icône

Le preset de l'acteur bouton offrant la possibilité d'intégrer une icône choisie parmi les icônes intégrées à Synapps.

Le contenu du bouton est complété par une additionnelle *icône* et une additionnelle *texte*.
