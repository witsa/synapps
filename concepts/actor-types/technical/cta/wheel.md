---
title: "Roue"
parent: "CTA"
grand_parent: "Technique"
---

{% include table_of_content.html %}

# Roue

Studio **1.7.0-beta**
{: .label .label-yellow }
Runtime **2.9.0**
{: .label .label-green }
REDY **16.5.0**
{: .label .label-yellow }

L'acteur Roue représente un ventilateur ou une roue de CTA. Il réagit à un mode numérique ou analogic et adapte la durée d'animation à la vitesse.

![Roue CTA](../../../../synapps-studio-releases/notes/assets/1.7/cta-wheel.gif)

## Propriétés spécifiques

### Mode

- **Type** : `String`
- **Description** : Définit le mode de commande. Les valeurs possibles sont `digital` et `analogic`.

> ⚡Chemin d’accès depuis l’acteur `properties.mode`

### En marche ?

- **Type** : `Boolean`
- **Description** : Utilisé en mode numérique pour déterminer si la roue tourne.

> ⚡Chemin d’accès depuis l’acteur `properties.isRunning`

### Vitesse

- **Type** : `Number`
- **Description** : Utilisée en mode analogic. La valeur influe directement sur l'animation de la roue.

> ⚡Chemin d’accès depuis l’acteur `properties.speed`
