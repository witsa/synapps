---
title: "Conduit"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Conduit

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Conduit représente une portion de gaine de ventilation. Il peut afficher un tronçon simple ou une extrémité selon sa configuration.

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation du conduit. Les valeurs possibles sont celles de `DirectionEnum`, généralement `left` ou `right`.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### Bord ?

- **Type** : `Boolean`
- **Description** : Si la valeur est `true`, le conduit affiche une extrémité au lieu d'un tronçon standard.

> ⚡Chemin d’accès depuis l’acteur `properties.isEdge`

### Taille

- **Type** : `Number`
- **Description** : Définit la taille visuelle du conduit. Plus la valeur est élevée, plus le tronçon affiché est long.

> ⚡Chemin d’accès depuis l’acteur `properties.size`
