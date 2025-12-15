---
title: "Technical | Vanne 3 voies"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Vanne 3 voies (3-Way Valve)

L'acteur Vanne 3 voies représente une vanne de mélange ou de dérivation. Sa position est contrôlée par une valeur numérique.

![Synapps](../../synapps-studio-releases/notes/assets/1.6/valvle-3-ports.gif)

La vanne 3 voies représente présente une poignée indiquant la position actuelle de la vanne, variant de **0%** à **100%**.
Si la ressource est en défaut, la poignée de la vanne est remplacée par une LED rouge clignotante.

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation du dessin de la vanne.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### Valeur

- **Type** : `Number`
- **Description** : Contrôle la position de la vanne avec un pourcentage (0-100). Une valeur de `0` positionne la vanne complètement dans une direction, et `100` la positionne complètement dans l'autre. Les valeurs intermédiaires représentent un état de mélange.

> ⚡Chemin d’accès depuis l’acteur `properties.value`

### En défaut ?

- **Type** : `Boolean`
- **Description** : Représente l'état de défaut de la vanne, cette propriété a la priorité sur les autres états.

> ⚡Chemin d’accès depuis l’acteur `properties.isFault`
