---
title: "Registre"
parent: "CTA"
grand_parent: "Technique"
---

{% include table_of_content.html %}

# Registre

Studio **1.7.0-beta**
{: .label .label-yellow }
Runtime **2.9.0**
{: .label .label-green }
REDY **16.5.0**
{: .label .label-yellow }

L'acteur Registre représente un registre de ventilation. Son fonctionnement est très proche du bypass : le mode numérique alterne entre ouvert et fermé, tandis que le mode analogic expose un pourcentage d'ouverture.

![Registre CTA](../../../../synapps-studio-releases/notes/assets/1.7/cta-register.gif)

## Propriétés spécifiques

### Mode

- **Type** : `String`
- **Description** : Définit le mode de contrôle. Les valeurs possibles sont `digital` et `analogic`.

> ⚡Chemin d’accès depuis l’acteur `properties.mode`

### Ouvert ?

- **Type** : `Boolean`
- **Description** : Utilisé lorsque le mode est `digital`. Si la valeur est `true`, le registre est affiché comme ouvert.

> ⚡Chemin d’accès depuis l’acteur `properties.isOpen`

### Ouverture (%)

- **Type** : `Number`
- **Description** : Utilisé lorsque le mode est `analogic`. La valeur représente le pourcentage d'ouverture affiché.

> ⚡Chemin d’accès depuis l’acteur `properties.opening`
