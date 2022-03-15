---
title: "Affichage | HTML"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

L'acteur HTML permet d'intégrer du code HTML et CSS dans votre scène.

C'est un acteur très pratique pour mettre en forme du texte, ou ajouter des classe CSS par exemple.

Son contenu est **jokerable**.

# Propriétés spécifiques

{% assign sorted = site.display_html_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}


# Variantes

## Icône

Une variante de l'acteur HTML offrant la possibilité d'intégrer une icône choisi parmi les icônes intégrées à Synapps.
