---
title: "Moteur axial"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Moteur axial

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Moteur axial représente une variante plus compacte du moteur CTA. Son comportement est identique sur le plan fonctionnel, avec un rendu plus adapté aux équipements axiaux.

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit le sens d'affichage du moteur. Les valeurs possibles suivent `DirectionEnum`.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### Mode

- **Type** : `String`
- **Description** : Définit le mode de commande. Les valeurs possibles sont `digital` et `analogique`.

> ⚡Chemin d’accès depuis l’acteur `properties.mode`

### En marche ?

- **Type** : `Boolean`
- **Description** : Utilisé en mode numérique pour indiquer si le moteur tourne.

> ⚡Chemin d’accès depuis l’acteur `properties.isRunning`

### Vitesse

- **Type** : `Number`
- **Description** : Utilisée en mode analogique. La valeur représente la vitesse d'affichage du moteur, généralement entre 0 et 100.

> ⚡Chemin d’accès depuis l’acteur `properties.speed`

### En défaut ?

- **Type** : `Boolean`
- **Description** : Si la valeur est `true`, la LED passe en état de défaut.

> ⚡Chemin d’accès depuis l’acteur `properties.isDefault`
