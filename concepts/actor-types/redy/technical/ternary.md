---
title: "Reflet Ternaire"
parent: "Technique REDY"
grand_parent: "REDY"
---

{% include table_of_content.html %}

# Acteur Reflet Ternaire

Studio **1.6.0**
{: .label .label-green }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-green }

L'acteur Reflet Ternaire permet d'afficher un des trois états distincts en fonction d'un reflet. Tous les reflet sont supportés mais le digital est privilégié.

{: .info }
>
> C'est la version avec reflet de l'acteur [Ternaire](../../technical/ternary.md).

1.  **État Vrai** : Lorsque la valeur est vraie
2.  **État Faux** : Lorsque la valeur est fausse
3.  **État de Défaut** : Lorsque le reflet est en défaut (cet état a la priorité sur les autres).

Nous retrouvons les mêmes possibilités de personnalisation que pour l'acteur Ternaire classique, avec la possibilité de configurer une LED ou une image et un comportement de clignotement spécifique pour chaque état. Seule la propriété texte n'est pas personnalisable car elle est directement issue du reflet.

## Propriétés spécifiques

Ces propriétés contrôlent l'état global de l'acteur.

{% include redy_reflect_technical_common.md %}

### Text à afficher `displayText`

- **Type** : `Boolean`
- **Description** : Permet d'activer (`true`) ou de désactiver (`false`) l'affichage du texte pour l'état actuellement visible.

> ⚡Chemin d’accès depuis l’acteur `properties.displayText`

### Couleur LED vrai

- **Type** : `CssColorString`
- **Description** : La couleur de la LED pour cet état (ex: `#00FF00`, `#FF5733`).

{: .pin }

> Les couleurs CSS par mot-clé telles que `red`, `green`, etc., ne sont pas prises en charge.

> ⚡Chemin d’accès depuis l’acteur `properties.ledColorTrue`

### LED vrai Allumée

- **Type** : `Boolean`
- **Description** : Contrôle si la LED est allumée (`true`) ou éteinte (`false`) pour cet état.

> ⚡Chemin d’accès depuis l’acteur `properties.ledIsOnTrue`

### Image personnalisée vrai

- **Type** : `String` (Chemin/URL)
- **Description** : Permet de remplacer la LED par une image.

> ⚡Chemin d’accès depuis l’acteur `properties.pictureTrue`

### Clignotante vrai ?

- **Type** : `Boolean`
- **Description** : Si `true`, la LED ou l'image de cet état se mettra à clignoter.

> ⚡Chemin d’accès depuis l’acteur `properties.isBlinkingTrue`

### Couleur LED faux

- **Type** : `CssColorString`
- **Description** : La couleur de la LED pour cet état (ex: `#00FF00`, `#FF5733`).

{: .pin }

> Les couleurs CSS par mot-clé telles que `red`, `green`, etc., ne sont pas prises en charge.

> ⚡Chemin d’accès depuis l’acteur `properties.ledColorFalse`

### LED faux Allumée

- **Type** : `Boolean`
- **Description** : Contrôle si la LED est allumée (`true`) ou éteinte (`false`) pour cet état.

> ⚡Chemin d’accès depuis l’acteur `properties.ledIsOnFalse`

### Image personnalisée faux

- **Type** : `String` (Chemin/URL)
- **Description** : Permet de remplacer la LED par une image.

> ⚡Chemin d’accès depuis l’acteur `properties.pictureFalse`

### Clignotante faux ?

- **Type** : `Boolean`
- **Description** : Si `true`, la LED ou l'image de cet état se mettra à clignoter.

> ⚡Chemin d’accès depuis l’acteur `properties.isBlinkingFalse`

### Couleur LED défaut

- **Type** : `CssColorString`
- **Description** : La couleur de la LED pour cet état (ex: `#00FF00`, `#FF5733`).

{: .pin }

> Les couleurs CSS par mot-clé telles que `red`, `green`, etc., ne sont pas prises en charge.

> ⚡Chemin d’accès depuis l’acteur `properties.ledColorFault`

### LED défaut Allumée

- **Type** : `Boolean`
- **Description** : Contrôle si la LED est allumée (`true`) ou éteinte (`false`) pour cet état.

> ⚡Chemin d’accès depuis l’acteur `properties.ledIsOnFault`

### Image personnalisée défaut

- **Type** : `String` (Chemin/URL)
- **Description** : Permet de remplacer la LED par une image.

> ⚡Chemin d’accès depuis l’acteur `properties.pictureFault`

### Clignotante défaut ?

- **Type** : `Boolean`
- **Description** : Si `true`, la LED ou l'image de cet état se mettra à clignoter.

> ⚡Chemin d’accès depuis l’acteur `properties.isBlinkingFault`
