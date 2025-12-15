---
title: "Technical | Chaudière"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Chaudière

L'acteur Chaudière permet de représenter l'état d'une chaudière industrielle et de son brûleur associé. Il représente visuellement les différents modes de fonctionnement comme la marche, l'arrêt ou un état de défaut.

![Synapps](../../synapps-studio-releases/notes/assets/1.6/boiler.gif)

Voici les différents états de la chaudière :

| État                   | Description                                         | État LED    | Couleur LED |
| ---------------------- | --------------------------------------------------- | ----------- | ----------- |
| **Arrêtée**            | La chaudière est éteinte et ne fonctionne pas.      | Éteinte     | ▫️          |
| **En marche**          | La chaudière est allumée et fonctionne normalement. | Allumée     | 🟩          |
| **Démarrage en cours** | La chaudière est en train de s'allumer.             | Clignotante | 🟩          |
| **Arrêt en cours**     | La chaudière est en train de s'éteindre.            | Clignotante | 🟩          |
| **En défaut**          | La chaudière rencontre un problème.                 | Clignotante | 🟥          |

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation de la chaudière. Les valeurs possibles sont `right` (droite) ou `left` (gauche).

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### Statut

- **Type** : `String` (Lecture seule)
- **Description** : Indique l'état de fonctionnement de la chaudière. Les valeurs possibles sont :

| **Nom**            | **Clé**    | **Description**                        | **État du brûleur**                |
| ------------------ | ---------- | -------------------------------------- | ---------------------------------- |
| Arrêté             | `stopped`  | La chaudière est arrêtée               | Éteint                             |
| En marche          | `running`  | La chaudière est en fonctionnement     | Synchronisé avec l'état du brûleur |
| Démarrage en cours | `starting` | La chaudière est en phase de démarrage | Éteint                             |
| Arrêt en cours     | `stopping` | La chaudière est en phase d'arrêt      | Éteint                             |

> ⚡Chemin d’accès depuis l’acteur `properties.status`

### En défaut?

- **Type** : `Boolean` (Lecture seule)
- **Description** : Indique si la chaudière est en état de défaut (`true`) ou non (`false`).

> ⚡Chemin d’accès depuis l’acteur `properties.isFault`

### Statut du brûleur

- **Type** : `String` (Lecture seule)
- **Description** : Indique le statut du brûleur associé à la chaudière.

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

> ⚡Chemin d’accès depuis l’acteur `properties.burnerStatus`
