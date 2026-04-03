---
title: "Capteur antigel"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Capteur antigel

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur Capteur antigel représente un capteur de surveillance du risque de gel. Son affichage reste simple et met en avant un état de défaut visuel lorsque l'alarme est active.

## Propriétés spécifiques

### En gel ?

- **Type** : `Boolean`
- **Description** : Si la valeur est `true`, le capteur signale un état de gel.

> ⚡Chemin d’accès depuis l’acteur `properties.isFrozen`
