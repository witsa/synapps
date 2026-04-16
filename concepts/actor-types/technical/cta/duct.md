---
title: "Conduit"
parent: "CTA"
grand_parent: "Technique"
---

{% include table_of_content.html %}

# Conduit

Studio **1.7.0-beta**
{: .label .label-yellow }
Runtime **2.9.0**
{: .label .label-green }
REDY **16.5.0**
{: .label .label-yellow }

L'acteur Conduit représente une portion de gaine de ventilation. Il peut afficher un tronçon simple ou une extrémité selon sa configuration.

## Propriétés spécifiques

### Bord ?

- **Type** : `Boolean`
- **Description** : Si la valeur est `true`, le conduit affiche une extrémité à la fin de celui-ci.

> ⚡Chemin d’accès depuis l’acteur `properties.isEdge`

### Taille

- **Type** : `Number`
- **Description** : Définit la taille visuelle du conduit. Plus la valeur est élevée, plus le tronçon affiché est long.

> ⚡Chemin d’accès depuis l’acteur `properties.size`

{: .alert .alert-info }
> La taille du conduit doit être ajustée pour contenir tout les éléments de CTA que l'on souhaite représenter dans ce conduit. Par exemple, si on souhaite représenter un moteur et un capteur dans le même conduit, il faudra s'assurer que la taille du conduit est suffisante pour contenir les deux éléments.
