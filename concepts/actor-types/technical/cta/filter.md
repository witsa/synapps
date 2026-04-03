---
title: "Filtre"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Filtre

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Filtre représente un filtre de CTA avec un indicateur visuel d'encrassement. La couleur de l'élément central varie selon l'état propre ou sale.

## Propriétés spécifiques

### Encrassé ?

- **Type** : `Boolean`
- **Description** : Si la valeur est `true`, le filtre est affiché comme encrassé.

> ⚡Chemin d’accès depuis l’acteur `properties.isDirty`

### Couleur propre

- **Type** : `CssColorString`
- **Description** : Couleur utilisée lorsque le filtre n'est pas encrassé.

> ⚡Chemin d’accès depuis l’acteur `properties.cleanColor`

### Couleur sale

- **Type** : `CssColorString`
- **Description** : Couleur utilisée lorsque le filtre est encrassé.

> ⚡Chemin d’accès depuis l’acteur `properties.dirtyColor`

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation du filtre. Les valeurs suivent `OrientationEnum`.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`
