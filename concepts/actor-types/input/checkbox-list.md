---
title: "Liste de Cases à cocher"
parent: "Formulaire"
grand_parent: "Intéraction"
api_type: input/checkbox-list
nav_order: 4
---

{% include links_actor.md apiClass="Actor.Input.CheckboxList" %}

# Liste de cases à cocher

Acteur d'interaction qui permet d'afficher une liste de cases à cocher. Cette liste peut être une arborescence. L'acteur possède deux modes de sélection : simple et multiple.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Informations
{: #informations }

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

Les champs d'information suivants sont très utiles pour réaliser des liaisons ou dans les scripts dans la mesure ou les propriétés de l'acteur ici sont souvent des chaines JSON.

{% include script_api/fields.md type=page.api_type %}

# Événements
{: #evenements }

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/scripts/reference/actor.html).

{% include script_api/events.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
