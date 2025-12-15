---
title: "Pompe simple"
parent: "Technique"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Pompe simple

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Pompe simple représente une pompe avec un seul moteur. Son état visuel (marche, arrêt, défaut) est déterminé par ses propriétés.

![Synapps](../../../synapps-studio-releases/notes/assets/1.6/single-pump.gif)

Voici les différents états de la pompe simple :

| État          | Description                                     | État LED | Couleur LED |
| ------------- | ----------------------------------------------- | -------- | ----------- |
| **Arrêtée**   | La pompe est éteinte et ne fonctionne pas.      | Éteinte  | ▫️          |
| **En marche** | La pompe est allumée et fonctionne normalement. | Allumée  | 🟩          |
| **En défaut** | La pompe rencontre un problème.                 | Allumée  | 🟥          |

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation du dessin de la pompe. Les valeurs possibles sont `up`, `down`, `right` (droite), ou `left` (gauche).

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### En marche ?

- **Type** : `Boolean`
- **Description** : Si cette propriété est activée, la pompe est considérée comme en marche. L'indicateur LED devient vert et une animation de rotation est appliquée.

> ⚡Chemin d’accès depuis l’acteur `properties.isRunning`

### En défaut ?

- **Type** : `Boolean`
- **Description** : Si cette propriété est activée, la pompe est en état de défaut. L'indicateur LED devient rouge et se met à clignoter. L'état de défaut a la priorité sur l'état de marche.

> ⚡Chemin d’accès depuis l’acteur `properties.isFault`

{: .pin }

> L'état de défaut de chaque pompe est indépendant et a la priorité sur son état de marche.
