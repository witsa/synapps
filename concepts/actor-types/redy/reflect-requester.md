---
title: "Requêteur de reflet"
parent: "Reflets"
grand_parent: "REDY"
api_type: redy/data-source/reflect-requester
nav_order: 4
---

{% include table_of_content.html %}

# Requêteur de reflet

Acteur requêteur de reflet. Permet de paramétrer les requêtes et d'exposer les reflets pour des liaisons ou accessible par script. Il doit être complété par des [fournisseurs de reflet](./reflect-source.md) pour effectuer une requête groupée.

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
