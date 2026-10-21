---
title: "Bouton"
parent: "Boutons"
grand_parent: "Intéraction"
api_type: input/button
nav_order: 1
redirect_from:
  - /script-api/Actor.Input.Button.html
  - /script-api/Actor.Input.ButtonProperties.html
  - /script-api/synapps-ui_addon_components_actors_input_button-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_input_button.js.html
---

# Bouton

Acteur bouton poussoir.

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

# Presets

## Icône

Le preset de l'acteur bouton offrant la possibilité d'intégrer une icône choisie parmi les icônes intégrées à Synapps.

Le contenu du bouton est complété par une additionnelle *icône* et une additionnelle *texte*.

## Écriture fournisseur

Ce preset "Bouton d'Écriture Fournisseur" permet de déclencher manuellement le processus d'écriture des données vers un acteur fournisseur spécifique.

Le contenu du bouton est complété par une additionnelle "Acteur fournisseur ciblé", qui permet de choisir l'acteur fournisseur vers lequel le bouton d'écriture est dirigé.
