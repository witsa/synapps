---
title: "Groupe de navigation"
parent: "Disposition"
api_type: layout/nav-group
---

{% include links_actor.md apiClass="Actor.Layout.NavGroup" %}

# Groupe de navigation

Le **Groupe de navigation** organise des boutons de menu sous une entête repliable. Il permet de structurer un menu en sections. Il se situe **obligatoirement** à l’intérieur d’un **Menu de navigation**.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

## Couleur de fond du groupe

Couleur d’arrière‑plan spécifique à l’entête du groupe.

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

# Fonctionnement

Le groupe calcule la hauteur de ses enfants (boutons de menu) afin d’animer l’ouverture et la fermeture. Lorsque l’entête est cliqué, la propriété **Groupe ouvert ?** est inversée et les enfants sont affichés ou masqués.
