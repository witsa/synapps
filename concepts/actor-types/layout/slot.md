---
title: "Emplacement"
parent: "Disposition"
grand_parent: "Types d'acteur"
api_type: layout/slot
nav_order: 5
---


# Emplacement

Acteur de disposition qui définit un emplacement libre dans un composite : il ne peut être placé que dans un composite et n'y reçoit pas d'enfant. Lorsque le composite est utilisé dans une scène, l'emplacement accueille l'acteur qui y est placé (son *occupant*).

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
