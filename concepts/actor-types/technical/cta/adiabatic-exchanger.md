---
title: "Échangeur adiabatique"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Échangeur adiabatique

Studio **1.7.0-beta**
{: .label .label-yellow }
Runtime **2.9.0**
{: .label .label-green }
REDY **16.5.0**
{: .label .label-yellow }

L'acteur Échangeur adiabatique représente un échangeur de type adiabatique. Il est possible de personnaliser le sens de circulation des flux ainsi que les couleurs des quatre flux.

## Propriétés spécifiques

### Sens du flux

- **Type** : `String`
- **Description** : Définit le sens de circulation des flux. Il existe quatre sens possibles :
- `top` : les deux flux circulent du haut vers le bas,
- `bottom` : les deux flux circulent du bas vers le haut,
- `left` : les deux flux circulent de la droite vers la gauche,
- `right` : les deux flux circulent de la gauche vers la droite.

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
