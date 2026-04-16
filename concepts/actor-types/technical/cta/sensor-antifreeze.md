---
title: "Capteur antigel"
parent: "CTA"
grand_parent: "Technique"
---

{% include table_of_content.html %}

# Capteur antigel

Studio **1.7.0-beta**
{: .label .label-yellow }
Runtime **2.9.0**
{: .label .label-green }
REDY **16.5.0**
{: .label .label-yellow }

L'acteur Capteur antigel représente un capteur de surveillance du risque de gel. Son affichage reste simple et met en avant un état de défaut visuel lorsque l'alarme est active.

![Capteur antigel CTA](../../../../synapps-studio-releases/notes/assets/1.7/cta-sensor-freeze.gif)

## Propriétés spécifiques

### En gel ?

- **Type** : `Boolean`
- **Description** : Si la valeur est `true`, le capteur signale un état de gel.

> ⚡Chemin d’accès depuis l’acteur `properties.isFrozen`
