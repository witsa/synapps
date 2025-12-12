---
title: "REDY | Reflet Brûleur"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Reflet Brûleur

L'acteur **Reflet Brûleur** permet une visualisation détaillée d'une ressource brûleur avec reflet.

## Fonctionnement

Cet acteur se connecte directement à la source de données d'un brûleur (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

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

{% include redy_reflect_technical_common.md %}

### Types de reflets compatibles

1. Reflet Brûleur