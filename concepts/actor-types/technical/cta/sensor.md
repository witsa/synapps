---
title: "Capteur"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Capteur

Studio **1.7.0-beta**
{: .label .label-yellow }
Runtime **2.9.0**
{: .label .label-green }
REDY **16.5.0**
{: .label .label-yellow }

L'acteur Capteur représente un capteur de CTA. Il expose un mode de fonctionnement et une valeur numérique simple.

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation du capteur. Les valeurs possibles suivent `OrientationEnum`.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`

### Mode

- **Type** : `String`
- **Description** : Définit le mode de contrôle. Les valeurs possibles sont `digital` et `analogic`.

> ⚡Chemin d’accès depuis l’acteur `properties.mode`

### Valeur

- **Type** : `Number`
- **Description** : Valeur numérique portée par le capteur.

> ⚡Chemin d’accès depuis l’acteur `properties.value`
