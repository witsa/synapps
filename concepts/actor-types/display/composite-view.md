---
title: "Vue de composite"
parent: "Affichage"
grand_parent: "Types d'acteur"
api_type: display/composite-view
nav_order: 6
---

{% include links_actor.md apiClass="Actor.Display.CompositeView" %}

# Vue de composite

Cet acteur permet d'afficher un composite de manière dynamique.

> 💡 **ASTUCE**<br>
> Si vous désirez passer des informations au composite, il faut utiliser le [ruissellement de contexte de donnée](../../context.md).

Il faut considérer cet acteur comme un "outil" pour dynamiquement, en fonction de données d'une liaison, ou bien par script, afficher le bon composite.

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
