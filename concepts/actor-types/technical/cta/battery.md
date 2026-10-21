---
title: "Batterie"
parent: "CTA"
grand_parent: "Technique"
api_type: technical/battery
nav_order: 2
since:
  studio: 1.7.0
  runtime: 2.9.0
  redy: 16.5.0
---

# Batterie

L'acteur Batterie représente une batterie de traitement d'air ou une batterie électrique. Il permet d'afficher un rendu coloré pour la batterie d'air et un indicateur LED pour la version électrique.
La batterie d'air possède des sortie de tuyaux à sa base afin de connecter celle-ci aux acteurs tuyaux de la chaufferie.

{: .pin }

> Pour le type `electric`, l'acteur affiche une LED d'état. Pour le type `air`, l'apparence dépend de la couleur choisie.

![Batterie CTA](../../../../synapps-studio-releases/notes/assets/1.7/cta-battery.gif)

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
