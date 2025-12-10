---
title: "Technical | Ternaire"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Acteur Ternaire

L'acteur Ternaire permet d'afficher un des trois états distincts en fonction d'une valeur et d'un état de défaut :

1.  **État Vrai** : Lorsque la `value` est vraie.
2.  **État Faux** : Lorsque la `value` est fausse.
3.  **État de Défaut** : Lorsqu'un défaut est signalé via `isFault` (cet état a la priorité sur les autres).

Chaque état est entièrement personnalisable, permettant de configurer un texte, une LED ou une image et un comportement de clignotement spécifique.

![Synapps](../../synapps-studio-releases/notes/assets/1.6/ternary.gif)

## Propriétés spécifiques

Ces propriétés contrôlent l'état global de l'acteur.

### Valeur ? ``value``

- **Type** : `Boolean`
- **Description** : La valeur principale qui détermine si l'acteur doit afficher l'état "Vrai" ou "Faux".

### En défaut? ``isFault``

- **Type** : `Boolean`
- **Description** : Si défini sur `true`, force l'affichage de l'état "de Défaut", ignorant la propriété `value`.

### Text à afficher ``displayText``

- **Type** : `Boolean`
- **Description** : Permet d'activer (`true`) ou de désactiver (`false`) l'affichage du texte pour l'état actuellement visible.

---

## Options des états

Pour chaque état (Vrai, Faux, Défaut), vous pouvez configurer les options d'affichage suivantes.

### Texte vrai

- **Type** : `String`
- **Description** : Le texte à afficher pour cet état.

### Couleur LED

- **Type** : `CssColorString`
- **Description** : La couleur de la LED pour cet état (ex: `#00FF00`, `#FF5733`).

> ⚠️ **ATTENTION**<br>
> Les couleurs CSS par mot-clé telles que `red`, `green`, etc., ne sont pas prises en charge.

### LED Allumée

- **Type** : `Boolean`
- **Description** : Contrôle si la LED est allumée (`true`) ou éteinte (`false`) pour cet état.

### Image personnalisée

- **Type** : `String` (Chemin/URL)
- **Description** : Permet de remplacer la LED par une image. Fournissez le chemin d'accès ou l'URL de l'image.

### Clignotante?

- **Type** : `Boolean`
- **Description** : Si `true`, la LED ou l'image de cet état se mettra à clignoter.