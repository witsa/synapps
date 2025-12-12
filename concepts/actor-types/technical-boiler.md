---
title: "Technical | Chaudière"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Chaudière (Boiler)

L'acteur Chaudière (Boiler) permet de représenter l'état d'une chaudière industrielle et de son brûleur associé. Il représente visuellement les différents modes de fonctionnement comme la marche, l'arrêt ou un état de défaut.

![Synapps](../../synapps-studio-releases/notes/assets/1.6/boiler.gif)

## Propriétés spécifiques

### Orientation ``orientation``

- **Type** : `String`
- **Description** : Définit l'orientation de la chaudière. Les valeurs possibles sont `right` (droite) ou `left` (gauche).

### Statut ``status``

- **Type** : `String` (Lecture seule)
- **Description** : Indique l'état de fonctionnement de la chaudière. Les valeurs possibles sont :
| **Nom**               | **Clé**          | **Description**                       | **État du brûleur**               |
|-----------------------|------------------|---------------------------------------|-----------------------------------|
| Arrêté                | `stopped`        | La chaudière est arrêtée              | Éteint                            |
| En marche             | `running`        | La chaudière est en fonctionnement    | Synchronisé avec l'état du brûleur|
| Démarrage en cours    | `starting`       | La chaudière est en phase de démarrage| Éteint                            |
| Arrêt en cours        | `stopping`       | La chaudière est en phase d'arrêt     | Éteint                            |

### En défaut? ``isFault``

- **Type** : `Boolean` (Lecture seule)
- **Description** : Indique si la chaudière est en état de défaut (`true`) ou non (`false`).

### Statut du brûleur ``burnerStatus``

- **Type** : `String` (Lecture seule)
- **Description** : Indique le statut du brûleur associé à la chaudière.
Il existe 9 états possibles:

| **Nom**                 | **Clé**          | **Description**                                 | **État de la LED**        | **État de la flamme**      |
|-------------------------|------------------|-------------------------------------------------|---------------------------|----------------------------|
| Sans                    | `without`        | Sans brûleur                                    | -                         | -                          |
| Arrêté                  | `stopped`        | Brûleur arrêté                                  | Éteinte                   | Absente                    |
| En marche               | `running`        | Brûleur en marche                               | Allumée                   | Présente                   |
| En veille               | `standby`        | Brûleur en veille                               | Clignotante               | Absente                    |
| Démarrage en cours      | `starting`       | Brûleur en démarrage                            | Clignotante               | Absente                    |
| Arrêt en cours          | `stopping`       | Brûleur en arrêt                                | Clignotante               | Présente                   |
| Initialisation          | `init`           | Brûleur en initialisation                       | Clignotante               | Absente                    |
| Défaut                  | `fault`          | Brûleur en défaut                               | Rouge clignotante         | Absente                    |
| Défaut atteinte consigne| `faultReachSP`   | Brûleur en défaut d'atteinte de consigne        | Orange clignotante        | Présente                   |
