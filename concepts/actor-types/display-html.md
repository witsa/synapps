---
title: "Affichage | HTML"
parent: "Types d'acteur"
grand_parent: Concepts
lang: fr
permalink: /concepts/actor-types/display-html.html
---

{% include links_actor.md apiClass="Actor.Display.Html" %}

# HTML

L'acteur HTML permet d'intégrer du code HTML et CSS dans votre scène.

C'est un acteur très pratique pour mettre en forme du texte, ou ajouter des classe CSS par exemple.

{% include table_of_content.html %}

Son contenu est **jokerable**.

## Propriétés spécifiques

{% assign sorted = site.display_html_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Champs d'informations

## Contenu complété

{% include field_completed_content.md %}

# Variantes

## Icône

Une variante de l'acteur HTML offrant la possibilité d'intégrer une icône choisie parmi les icônes intégrées à Synapps.

Le contenu de l'acteur est complété par une additionnelle *icône*.
