---
title: "Moteur axial"
parent: "CTA"
grand_parent: "Technique"
---

{% include table_of_content.html %}

# Moteur axial

Studio **1.7.0-beta**
{: .label .label-yellow }
Runtime **2.9.0**
{: .label .label-green }
REDY **16.5.0**
{: .label .label-yellow }

L'acteur Moteur axial représente une variante plus compacte du moteur CTA. Ses propriétés sont similaires à celles du moteur standard.

![Moteur axial CTA](../../../../synapps-studio-releases/notes/assets/1.7/cta-motor-axial.gif)

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit le sens d'affichage du moteur (droite ou gauche).

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### Mode

- **Type** : `String`
- **Description** : Définit le mode de commande. Les valeurs possibles sont `digital` et `analogic`.

> ⚡Chemin d’accès depuis l’acteur `properties.mode`

### En marche ? (Uniquement pour le mode digital)

- **Type** : `Boolean`
- **Description** : Indique si le moteur est en marche.

> ⚡Chemin d’accès depuis l’acteur `properties.isRunning`

### Vitesse (Uniquement pour le mode analogic)

- **Type** : `Number`
- **Description** :La valeur représente la vitesse d'affichage du moteur (0: lent, 100: rapide).

> ⚡Chemin d’accès depuis l’acteur `properties.speed`

### En défaut ?

- **Type** : `Boolean`
- **Description** : Si la valeur est `true`, la LED passe en état de défaut.

> ⚡Chemin d’accès depuis l’acteur `properties.isDefault`
