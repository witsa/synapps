---
title: "Chaudière"
parent: "Chaufferie & ECS"
grand_parent: "Technique"
api_type: technical/boiler
nav_order: 1
since:
  studio: 1.6.0
  runtime: 2.8.0
  redy: 16.4.0
---

# Chaudière

L'acteur Chaudière permet de représenter l'état d'une chaudière industrielle et de son brûleur associé. Il représente visuellement les différents modes de fonctionnement comme la marche, l'arrêt ou un état de défaut.

![Synapps](../../../../synapps-studio-releases/notes/assets/1.6/boiler.gif)

Voici les différents états de la chaudière :

| État                   | Description                                         | État LED    | Couleur LED |
| ---------------------- | --------------------------------------------------- | ----------- | ----------- |
| **Arrêtée**            | La chaudière est éteinte et ne fonctionne pas.      | Éteinte     | ▫️          |
| **En marche**          | La chaudière est allumée et fonctionne normalement. | Allumée     | 🟩          |
| **Démarrage en cours** | La chaudière est en train de s'allumer.             | Clignotante | 🟩          |
| **Arrêt en cours**     | La chaudière est en train de s'éteindre.            | Clignotante | 🟩          |
| **En défaut**          | La chaudière rencontre un problème.                 | Clignotante | 🟥          |

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
