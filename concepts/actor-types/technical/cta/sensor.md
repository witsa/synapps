---
title: "Capteur"
parent: "CTA"
grand_parent: "Technique"
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

![Capteur CTA](../../../../synapps-studio-releases/notes/assets/1.7/cta-sensor.png)

## Propriétés spécifiques

### Orientation

- **Type** : `String`
- **Description** : Définit l'orientation du capteur. Les valeurs possibles suivent `OrientationEnum`.

> ⚡Chemin d’accès depuis l’acteur `properties.orientation`
