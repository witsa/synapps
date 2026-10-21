---
title: "Vanne 3 voies"
parent: "Chaufferie & ECS"
grand_parent: "Technique"
api_type: technical/valve-3-ports
nav_order: 9
since:
  studio: 1.6.0
  runtime: 2.8.0
  redy: 16.4.0
---

# Vanne 3 voies

L'acteur Vanne 3 voies représente une vanne de mélange ou de dérivation. Sa position est contrôlée par une valeur numérique.

![Synapps](../../../../synapps-studio-releases/notes/assets/1.6/valvle-3-ports.gif)

La vanne 3 voies représente présente une poignée indiquant la position actuelle de la vanne, variant de **0%** à **100%**.
Si la ressource est en défaut, la poignée de la vanne est remplacée par une LED rouge clignotante.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
