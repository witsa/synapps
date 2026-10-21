---
api_type: technical/boiler
kind: property
name: burnerStatus
---
Indique le statut du brûleur associé à la chaudière.

Il existe 9 états possibles:

| **Nom**                  | **Clé**        | **Description**                          | **État de la LED** | **État de la flamme** |
| ------------------------ | -------------- | ---------------------------------------- | ------------------ | --------------------- |
| Sans                     | `without`      | Sans brûleur                             | -                  | -                     |
| Arrêté                   | `stopped`      | Brûleur arrêté                           | Éteinte            | Absente               |
| En marche                | `running`      | Brûleur en marche                        | Allumée            | Présente              |
| En veille                | `standby`      | Brûleur en veille                        | Clignotante        | Absente               |
| Démarrage en cours       | `starting`     | Brûleur en démarrage                     | Clignotante        | Absente               |
| Arrêt en cours           | `stopping`     | Brûleur en arrêt                         | Clignotante        | Présente              |
| Initialisation           | `init`         | Brûleur en initialisation                | Clignotante        | Absente               |
| Défaut                   | `fault`        | Brûleur en défaut                        | Rouge clignotante  | Absente               |
| Défaut atteinte consigne | `faultReachSP` | Brûleur en défaut d'atteinte de consigne | Orange clignotante | Présente              |
