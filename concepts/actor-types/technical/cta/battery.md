---
title: "Batterie"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Batterie

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Batterie représente une batterie de traitement d'air ou une batterie électrique. Il permet d'afficher un rendu coloré pour la batterie d'air et un indicateur LED pour la version électrique.

{: .pin }

> Pour le type `electric`, l'acteur affiche une LED d'état. Pour le type `air`, l'apparence dépend de la couleur choisie.

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation de la batterie.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### Type

- **Type** : `String`
- **Description** : Définit le type de batterie. Les valeurs possibles sont `air` ou `electric`.

> ⚡Chemin d’accès depuis l’acteur `properties.type`

### Couleur de la batterie d'air

- **Type** : `String`
- **Description** : Définit la couleur de la batterie d'air. Les valeurs possibles sont `rouge`, `bleu` ou `personnalisé`.

> ⚡Chemin d’accès depuis l’acteur `properties.airBatteryColor`

### Couleur personnalisée

- **Type** : `CssColorString`
- **Description** : Couleur utilisée lorsque le type d'air est réglé sur `custom`.

> ⚡Chemin d’accès depuis l’acteur `properties.customColor`

### En marche ?

- **Type** : `Boolean`
- **Description** : Indique si la batterie est considérée comme en fonctionnement.

> ⚡Chemin d’accès depuis l’acteur `properties.isRunning`

### En défaut ?

- **Type** : `Boolean`
- **Description** : Indique si la batterie doit afficher son état de défaut. Pour la version électrique, cela force une LED rouge clignotante.

> ⚡Chemin d’accès depuis l’acteur `properties.isDefault`
