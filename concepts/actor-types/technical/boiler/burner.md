---
title: "Brûleur"
parent: "Chaufferie & ECS"
grand_parent: "Technique"
api_type: technical/burner
nav_order: 2
since:
  studio: 1.6.0
  runtime: 2.8.0
  redy: 16.4.0
---

# Brûleur

L'acteur Brûleur (Burner) représente l'état d'un brûleur. Il affiche visuellement les différents modes de fonctionnement tels que la marche, l'arrêt ou un état de défaut.

![Synapps](../../../../synapps-studio-releases/notes/assets/1.6/burner.gif)


Voici les différents états du brûleur :

| État                                    | Description                                                                   | État LED    | Couleur LED | Flamme     |
| --------------------------------------- | ----------------------------------------------------------------------------- | ----------- | ----------- | ---------- |
| **Arrêté**                              | Le brûleur est éteint et ne fonctionne pas.                                   | Éteinte     | -           | Éteinte    |
| **En marche**                           | Le brûleur est allumé et fonctionne normalement.                              | Allumée     | Verte       | Allumée    |
| **En attente**                          | Le brûleur est en pause, attendant une condition pour continuer.              | Clignotante | Verte       | Éteinte    |
| **Démarrage en cours**                  | Le brûleur est en train de s'allumer.                                         | Clignotante | Verte       | Allumage   |
| **Arrêt en cours**                      | Le brûleur est en train de s'éteindre.                                        | Clignotante | Verte       | Extinction |
| **Initialisation**                      | Le brûleur est en phase d'initialisation.                                     | Clignotante | Verte       | Éteinte    |
| **En défaut**                           | Le brûleur rencontre un problème.                                             | Allumée     | Rouge       | Éteinte    |
| **En défaut d'atteinte de la consigne** | Le brûleur n'a pas réussi à atteindre la température ou la condition définie. | Clignotante | Orange      | Éteinte    |

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
