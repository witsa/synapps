---
title: "Échangeur adiabatique"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Échangeur adiabatique

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Échangeur adiabatique représente un échangeur de type adiabatique. Il est entièrement graphique et permet de personnaliser le sens de circulation ainsi que les couleurs des quatre quadrants.

## Propriétés spécifiques

### Sens du flux

- **Type** : `String`
- **Description** : Définit le sens de circulation principal. Les valeurs possibles sont `bottom`, `top`, `left` et `right`.

> ⚡Chemin d’accès depuis l’acteur `properties.flowDirection`

### Couleur haut gauche

- **Type** : `CssColorString`
- **Description** : Couleur affichée dans le quadrant haut gauche.

> ⚡Chemin d’accès depuis l’acteur `properties.colorTopLeft`

### Couleur haut droite

- **Type** : `CssColorString`
- **Description** : Couleur affichée dans le quadrant haut droit.

> ⚡Chemin d’accès depuis l’acteur `properties.colorTopRight`

### Couleur bas gauche

- **Type** : `CssColorString`
- **Description** : Couleur affichée dans le quadrant bas gauche.

> ⚡Chemin d’accès depuis l’acteur `properties.colorBottomLeft`

### Couleur bas droite

- **Type** : `CssColorString`
- **Description** : Couleur affichée dans le quadrant bas droit.

> ⚡Chemin d’accès depuis l’acteur `properties.colorBottomRight`
