---
title: "Pompe simple"
parent: "Chaufferie & ECS"
grand_parent: "Technique"
api_type: technical/single-pump
nav_order: 6
since:
  studio: 1.6.0
  runtime: 2.8.0
  redy: 16.4.0
---

# Pompe simple

L'acteur Pompe simple représente une pompe avec un seul moteur. Son état visuel (marche, arrêt, défaut) est déterminé par ses propriétés.

![Synapps](../../../../synapps-studio-releases/notes/assets/1.6/single-pump.gif)

Voici les différents états de la pompe simple :

| État          | Description                                     | État LED | Couleur LED |
| ------------- | ----------------------------------------------- | -------- | ----------- |
| **Arrêtée**   | La pompe est éteinte et ne fonctionne pas.      | Éteinte  | ▫️          |
| **En marche** | La pompe est allumée et fonctionne normalement. | Allumée  | 🟩          |
| **En défaut** | La pompe rencontre un problème.                 | Allumée  | 🟥          |

{: .pin }
> L'état de défaut de chaque pompe est indépendant et a la priorité sur son état de marche.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
