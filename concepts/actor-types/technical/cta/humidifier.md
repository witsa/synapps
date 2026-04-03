---
title: "Humidificateur"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Humidificateur

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Humidificateur représente un humidificateur de CTA. Son affichage change selon l'activation et l'état de défaut.

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation de l'humidificateur. Les valeurs possibles suivent `DirectionEnum`.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### Actif ?

- **Type** : `Boolean`
- **Description** : Si la valeur est `true`, l'humidificateur est considéré comme actif.

> ⚡Chemin d’accès depuis l’acteur `properties.isActive`

### En défaut ?

- **Type** : `Boolean`
- **Description** : Si la valeur est `true`, l'indicateur LED passe en état de défaut.

> ⚡Chemin d’accès depuis l’acteur `properties.isDefault`
