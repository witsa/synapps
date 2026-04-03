---
title: "Roue"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Roue

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Roue représente un ventilateur ou une roue de CTA. Il réagit à un mode numérique ou analogique et adapte la durée d'animation à la vitesse.

## Propriétés spécifiques

### Mode

- **Type** : `String`
- **Description** : Définit le mode de commande. Les valeurs possibles sont `digital` et `analogique`.

> ⚡Chemin d’accès depuis l’acteur `properties.mode`

### En marche ?

- **Type** : `Boolean`
- **Description** : Utilisé en mode numérique pour déterminer si la roue tourne.

> ⚡Chemin d’accès depuis l’acteur `properties.isRunning`

### Vitesse

- **Type** : `Number`
- **Description** : Utilisée en mode analogique. La valeur influe directement sur l'animation de la roue.

> ⚡Chemin d’accès depuis l’acteur `properties.speed`
