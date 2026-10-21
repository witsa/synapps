---
title: "Html"
parent: "Affichage"
grand_parent: "Types d'acteur"
api_type: display/html
nav_order: 2
---

{% include links_actor.md apiClass="Actor.Display.Html" %}

# Html
L'acteur HTML permet d'intégrer du code HTML et CSS dans votre scène.

C'est un acteur très pratique pour mettre en forme du texte, ou ajouter des classe CSS par exemple.

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

# Variantes

## Icône

Une variante de l'acteur HTML offrant la possibilité d'intégrer une icône choisie parmi les icônes intégrées à Synapps.

Le contenu de l'acteur est complété par une additionnelle *icône*.
