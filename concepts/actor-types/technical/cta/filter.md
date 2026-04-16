---
title: "Filtre"
parent: "CTA"
grand_parent: "Technique"
---

{% include table_of_content.html %}

# Filtre

Studio **1.7.0-beta**
{: .label .label-yellow }
Runtime **2.9.0**
{: .label .label-green }
REDY **16.5.0**
{: .label .label-yellow }

L'acteur Filtre représente un filtre de CTA avec un capteur. L'état varie selon la propriété `isDirty` (sale/propre).

![Filtre CTA](../../../../synapps-studio-releases/notes/assets/1.7/cta-filter.gif)

## Propriétés spécifiques

### Sale ?

- **Type** : `Boolean`
- **Description** : Si la valeur est `true`, le filtre et le capteur prennent la couleur correspondante à l'état sale.

> ⚡Chemin d’accès depuis l’acteur `properties.isDirty`

### Couleur propre

- **Type** : `CssColorString`
- **Description** : Couleur utilisée lorsque le filtre est propre.

> ⚡Chemin d’accès depuis l’acteur `properties.cleanColor`

### Couleur sale

- **Type** : `CssColorString`
- **Description** : Couleur utilisée lorsque le filtre est sale.

> ⚡Chemin d’accès depuis l’acteur `properties.dirtyColor`

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation du filtre.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`
