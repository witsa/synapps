---
title: "Texte"
parent: "Affichage"
grand_parent: "Types d'acteur"
api_type: display/text
nav_order: 1
---

{% include links_actor.md apiClass="Actor.Display.Text" %}

# Texte

Acteur de base pour afficher du texte.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Informations
{: #informations }

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

{% include script_api/fields.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
