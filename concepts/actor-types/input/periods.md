---
title: "Périodes"
parent: "Intéraction"
api_type: input/period
---

{% include links_actor.md apiClass="Actor.Input.Period" %}

# Périodes

L'acteur *Période* propose une sélection de périodes types et expose les bornes de date correspondantes à la période sélectionnée.

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_period/sample01.gif)

L'acteur *Période* a beaucoup de similitudes avec l'acteur [*Liste de boutons*](./button-list.md) et propose la plupart de ses propriétés (*En ligne?*, *Taille*, *Mode*, ...).

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
