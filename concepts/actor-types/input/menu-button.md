---
title: "Bouton de menu"
parent: "Intéraction"
api_type: input/menu-button
---

{% include links_actor.md apiClass="Actor.Input.MenuButton" %}

# Bouton de menu

Le **Bouton de menu** est un bouton conçu pour fonctionner avec un **Menu de navigation**. Il met à jour la scène sélectionnée du menu et adapte son style en fonction de l’état actif/inactif. Le style actif est également le style appliqué au bouton au survol.

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

# Comportement

- Au clic, le bouton met à jour la propriété **Scène sélectionnée** du **Menu de navigation** parent.
- Le style actif/inactif est appliqué automatiquement en fonction de la scène sélectionnée.
- Au survol, le bouton adopte le style actif.
