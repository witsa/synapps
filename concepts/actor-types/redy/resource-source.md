---
title: "Fournisseur de ressource"
parent: "REDY"
api_type: redy/data-source/resource
---


{% include links_actor.md apiClass="REDY.Actor.WosVariableSource" %}

# Fournisseur de ressource

Acteur [fournisseur de variable](./wos-variable-source.md) mais bloqué pour cibler uniquement les *ressources* d'un REDY.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés

{% include script_api/properties.md type=page.api_type %}

# Informations

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

{% include script_api/fields.md type=page.api_type %}

# Méthodes

{% include script_api/methods.md type=page.api_type %}

# Événements

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/actor/).

{% include script_api/events.md type=page.api_type %}

# Hérite de

{% include script_api/inherits.md type=page.api_type %}
