---
title: "Liste de choix"
parent: "Intéraction"
api_type: input/radio-list
---

{% include links_actor.md apiClass="Actor.Input.RadioList" %}

# Liste de cases à cocher

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_radio_list/sample01.gif)

Acteur d'interaction qui permet d'afficher une liste de cases à cocher. Cette liste peut être une arborescence. L'acteur possède deux modes de sélection : simple et multiple.

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
