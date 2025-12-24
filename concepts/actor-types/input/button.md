---
title: "Bouton"
parent: "Intéraction"
---

> 🚧 en cours de rédaction...

{% include links_actor.md apiClass="Actor.Input.Button" %}

# Bouton

Acteur bouton poussoir.

{% include table_of_content.html %}

# Propriétés spécifiques

{% assign sorted = site.input_button_properties | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Champs d'informations

## Est Pressé ?

Le champ d'information *Est pressé?* est un booléen qui est `true` lorsque le bouton est pressé et repasse à `false` lorsque le bouton est relâché, après un petit délai de relaxation.

## Contenu complété

{% include field_completed_content.md %}

# Évènements spécifiques

> 🚧 en cours de rédaction...

# Variantes

## Icône

La variante de l'acteur bouton offrant la possibilité d'intégrer une icône choisie parmi les icônes intégrées à Synapps.

Le contenu du bouton est complété par une additionnelle *icône* et une additionnelle *texte*.

## Écriture fournisseur

Cette variation "Bouton d'Écriture Fournisseur" permet de déclencher manuellement le processus d'écriture des données vers un acteur fournisseur spécifique.

Le contenu du bouton est complété par une additionnelle "Acteur fournisseur ciblé", qui permet de choisir l'acteur fournisseur vers lequel le bouton d'écriture est dirigé.
