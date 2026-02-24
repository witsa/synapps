---
title: "Ternaire"
parent: "Technique"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Acteur Ternaire

Studio **1.6.0**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Ternaire permet d'afficher un des trois états distincts en fonction d'une valeur et d'un état de défaut :

1.  **État Vrai** : Lorsque la `value` est vraie.
2.  **État Faux** : Lorsque la `value` est fausse.
3.  **État de Défaut** : Lorsqu'un défaut est signalé via `isFault` (cet état a la priorité sur les autres).

Chaque état est entièrement personnalisable, permettant de configurer un texte, une LED ou une image et un comportement de clignotement spécifique.

La led est affichée si vous ne fournissez pas d'image personnalisée.

{: .pin }

> Par défaut, l'acteur Ternaire affiche une LED verte allumée pour l'état Vrai, une LED verte éteinte pour l'état Faux, et une LED rouge clignotante pour l'état de Défaut.

![Synapps](../../../synapps-studio-releases/notes/assets/1.6/ternary.gif)

## Propriétés spécifiques

Ces propriétés contrôlent l'état global de l'acteur.

### Valeur ? `value`

- **Type** : `Boolean`
- **Description** : La valeur principale qui détermine si l'acteur doit afficher l'état "Vrai" ou "Faux".

> ⚡Chemin d’accès depuis l’acteur `properties.value`

### En défaut? `isFault`

- **Type** : `Boolean`
- **Description** : Si défini sur `true`, force l'affichage de l'état "de Défaut", ignorant la propriété `value`.

> ⚡Chemin d’accès depuis l’acteur `properties.isFault`

### Text à afficher `displayText`

- **Type** : `Boolean`
- **Description** : Permet d'activer (`true`) ou de désactiver (`false`) l'affichage du texte pour l'état actuellement visible.

> ⚡Chemin d’accès depuis l’acteur `properties.displayText`

### Texte vrai

- **Type** : `String`
- **Description** : Le texte à afficher pour cet état.

> ⚡Chemin d’accès depuis l’acteur `properties.textTrue`

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

### Texte faux

- **Type** : `String`
- **Description** : Le texte à afficher pour cet état.

> ⚡Chemin d’accès depuis l’acteur `properties.textFalse`

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

### Texte défaut

- **Type** : `String`
- **Description** : Le texte à afficher pour cet état.

> ⚡Chemin d’accès depuis l’acteur `properties.textFault`

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
