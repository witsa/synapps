---
title: "Brûleur"
parent: "Chaufferie"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Brûleur

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Brûleur (Burner) représente l'état d'un brûleur. Il affiche visuellement les différents modes de fonctionnement tels que la marche, l'arrêt ou un état de défaut.

![Synapps](../../../synapps-studio-releases/notes/assets/1.6/burner.gif)


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

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation du brûleur. Les valeurs possibles sont `right` (droite) ou `left` (gauche).

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### Statut

- **Type** : `String`
- **Description** : Indique l'état de fonctionnement du brûleur. Les valeurs possibles sont :

  - `stopped` : Arrêté, led éteinte, flamme absente
  - `running` : En marche, led allumée, flamme présente
  - `standby` : En veille, led clignotante, flamme absente
  - `starting` : En démarrage, led clignotante, flamme absente
  - `stopping` : En arrêt, led clignotante, flamme présente
  - `init` : En initialisation, led clignotante, flamme absente

> ⚡Chemin d’accès depuis l’acteur `properties.status`

### En défaut ?

- **Type** : `Boolean`
- **Description** : Indique si le brûleur est en état de défaut (`true`) ou non (`false`).

> ⚡Chemin d’accès depuis l’acteur `properties.isFault`

### En défaut atteinte consigne ?

- **Type** : `Boolean`
- **Description** : Indique si le brûleur est en défaut d'atteinte de consigne.

> ⚡Chemin d’accès depuis l’acteur `properties.isFaultReachSP`
