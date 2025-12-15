---
title: "Technical | Multiposition"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Acteur Multiposition

L'acteur Multiposition permet d'afficher un état parmi une liste de "positions" configurables. C'est un composant idéal pour représenter un équipement ayant plusieurs modes de fonctionnement (ex: Arrêt, Manuel, Auto, Alarme).

L'acteur peut gérer jusqu'à 8 positions. Par défaut, il est créé avec 4 positions, mais vous pouvez en ajouter ou en supprimer selon vos besoins.

## Propriétés spécifiques

### Position ``position``
- **Type** : `String`
- **Description** : Sélectionne la position à afficher. Il faut utiliser la clé unique de la position (`positionKey`).

### Afficher le texte ``displayText``
- **Type** : `Boolean`
- **Description** : Permet d'activer ou de désactiver l'affichage du texte pour la position actuellement visible.

---

## Propriétés des Positions

Chaque position dans la liste est un objet configurable avec les propriétés suivantes :

### Position
- **Type** : `String`
- **Description** : Une clé unique (ex: "mode_auto") pour identifier la position. Cette clé peut être utilisée pour activer la position via la propriété `position`.

### Texte
- **Type** : `String`
- **Description** : Le texte à afficher lorsque cette position est active.

### Image personnalisée
- **Type** : `String` (Chemin/URL)
- **Description** : Le chemin d'accès ou l'URL de l'image à afficher pour cette position.

### Clignotant?
- **Type** : `Boolean`
- **Description** : Si `true`, l'image de cette position se mettra à clignoter.