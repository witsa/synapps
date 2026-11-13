---
title: "Groupe de barre de navigation"
parent: "Navigation"
grand_parent: "Intéraction"
api_type: layout/navbar-group
nav_order: 6
---

{% include table_of_content.html %}

# Groupe de barre de navigation

Groupe de navigation horizontal, placé dans une [barre de navigation](./navbar.md).

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

# Fonctionnement

Le menu du groupe s’ouvre au clic sur son titre, ou au survol si la barre a **Ouvrir au survol ?** activé. Il s’ouvre sous la barre ou au-dessus selon la **Position du menu des groupes** de la barre ; si la place manque, il s’ouvre de l’autre côté.

Le titre prend les couleurs de **groupe actif** de la barre quand le groupe contient le bouton de la scène sélectionnée, quand il est survolé et tant que son menu est ouvert, comme un bouton de la barre prend son style actif au survol.

La couleur du texte réglée sur la barre s’applique aux boutons du menu du groupe.
