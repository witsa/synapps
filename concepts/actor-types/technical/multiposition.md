---
title: "Multiposition"
parent: "Technique"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Acteur Multiposition

Studio **1.6.0**
{: .label .label-green }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-green }

L'acteur Multiposition permet d'afficher un état parmi une liste de "positions" configurables. C'est un composant idéal pour représenter un équipement ayant plusieurs modes de fonctionnement (ex: Arrêt, Manuel, Auto, Alarme).

L'acteur peut gérer jusqu'à 8 positions. Par défaut, il est créé avec 4 positions, mais vous pouvez en ajouter ou en supprimer selon vos besoins.

## Propriétés spécifiques

### Position

- **Type** : `String`
- **Description** : Sélectionne la position à afficher. Il faut utiliser la clé unique de la position (`positionKey`).

> ⚡Chemin d’accès depuis l’acteur `properties.position`

### Afficher le texte

- **Type** : `Boolean`
- **Description** : Permet d'activer ou de désactiver l'affichage du texte pour la position actuellement visible.

> ⚡Chemin d’accès depuis l’acteur `properties.displayText`

## Propriétés des Positions

Chaque position dans la liste est un objet configurable avec les propriétés suivantes :

### Position

- **Type** : `String`
- **Description** : Une clé unique (ex: "mode_auto") pour identifier la position. Cette clé peut être utilisée pour activer la position via la propriété Position.

> ⚡Chemin d’accès depuis l’acteur `properties.positions<n>` où `<n>` est l'index de la position (1 à 8).

### Texte

- **Type** : `String`
- **Description** : Le texte à afficher lorsque cette position est active.

> ⚡Chemin d’accès depuis l’acteur `properties.text<n>` où `<n>` est l'index de la position (1 à 8).

### Image personnalisée

- **Type** : `String` (Chemin/URL)
- **Description** : Le chemin d'accès ou l'URL de l'image à afficher pour cette position.

> ⚡Chemin d’accès depuis l’acteur `properties.customImage<n>` où `<n>` est l'index de la position (1 à 8).

### Clignotant?

- **Type** : `Boolean`
- **Description** : Si `true`, l'image de cette position se mettra à clignoter.

> ⚡Chemin d’accès depuis l’acteur `properties.isBlinking<n>` où `<n>` est l'index de la position (1 à 8).
