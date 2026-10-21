---
title: "Pompe double"
parent: "Chaufferie & ECS"
grand_parent: "Technique"
api_type: technical/double-pump
nav_order: 3
since:
  studio: 1.6.0
  runtime: 2.8.0
  redy: 16.4.0
---

# Pompe double

L'acteur Pompe double représente un système de pompage avec deux moteurs. Chaque pompe peut être contrôlée et surveillée indépendamment pour son état de marche et de défaut.

![Synapps](../../../../synapps-studio-releases/notes/assets/1.6/double-pump.gif)


Voici les différents états de la pompe double :

| État                  | Description                                           | État LED | Couleur LED |
| --------------------- | ----------------------------------------------------- | -------- | ----------- |
| **Arrêtée**           | Les deux pompes sont éteintes et ne fonctionnent pas. | Éteinte  | ▫️          |
| **Pompe 1 en marche** | La pompe 1 est allumée et fonctionne normalement.     | Allumée  | 🟩          |
| **Pompe 2 en marche** | La pompe 2 est allumée et fonctionne normalement.     | Allumée  | 🟩          |
| **Pompe 1 en défaut** | La pompe 1 rencontre un problème.                     | Allumée  | 🟥          |
| **Pompe 2 en défaut** | La pompe 2 rencontre un problème.                     | Allumée  | 🟥          |

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
