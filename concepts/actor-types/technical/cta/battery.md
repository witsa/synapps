---
title: "Batterie"
parent: "CTA"
grand_parent: "Technique"
---

{% include table_of_content.html %}

# Batterie

Studio **1.7.0-beta**
{: .label .label-yellow }
Runtime **2.9.0**
{: .label .label-green }
REDY **16.5.0**
{: .label .label-yellow }

L'acteur Batterie représente une batterie de traitement d'air ou une batterie électrique. Il permet d'afficher un rendu coloré pour la batterie d'air et un indicateur LED pour la version électrique.
La batterie d'air possède des sortie de tuyaux à sa base afin de connecter celle-ci aux acteurs tuyaux de la chaufferie.

{: .pin }

> Pour le type `electric`, l'acteur affiche une LED d'état. Pour le type `air`, l'apparence dépend de la couleur choisie.

![Batterie CTA](../../../../synapps-studio-releases/notes/assets/1.7/cta-battery.gif)

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation de la batterie.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### Type

- **Type** : `String`
- **Description** : Définit le type de batterie. Les valeurs possibles sont `air` ou `electric`.

> ⚡Chemin d’accès depuis l’acteur `properties.type`

### Couleur de la batterie d'air (uniquement pour le type d'air)

- **Type** : `String`
- **Description** : Définit la couleur de la batterie d'air. Les valeurs possibles sont `rouge`, `bleu` ou `personnalisé`.

> ⚡Chemin d’accès depuis l’acteur `properties.airBatteryColor`

### Couleur personnalisée (Uniquement pour le type d'air)

- **Type** : `CssColorString`
- **Description** : Couleur utilisée lorsque le type d'air est réglé sur `custom`.

> ⚡Chemin d’accès depuis l’acteur `properties.customColor`

### En marche ? (Uniquement pour le type électrique)

- **Type** : `Boolean`
- **Description** : Indique si la batterie est considérée comme en fonctionnement (LED allumée / éteinte).

> ⚡Chemin d’accès depuis l’acteur `properties.isRunning`

### En défaut ? (Uniquement pour le type électrique)

- **Type** : `Boolean`
- **Description** : Indique si la batterie doit afficher son état de défaut. (LED rouge clignotante).

> ⚡Chemin d’accès depuis l’acteur `properties.isDefault`
