---
title: "Bypass"
parent: "Centrale de traitement d'air"
grand_parent: "Types d'acteur"
---

{% include table_of_content.html %}

# Bypass

Studio **1.7.0-beta**
{: .label .label-yellow }
Runtime **2.9.0**
{: .label .label-green }
REDY **16.5.0**
{: .label .label-yellow }

L'acteur Bypass représente une connection entre deux gaines de la CTA avec un registre entre ces deux gaines. Il propose un mode digital, avec un état ouvert ou fermé, et un mode analogic, avec un pourcentage d'ouverture.

## Propriétés spécifiques

### Mode

- **Type** : `String`
- **Description** : Définit le mode de contrôle. Les valeurs possibles sont `digital` et `analogic`.

> ⚡Chemin d’accès depuis l’acteur `properties.mode`

### Ouvert ? (Uniquement pour le mode digital)

- **Type** : `Boolean`
- **Description** : Affiche le volet comme ouvert ou fermé.

> ⚡Chemin d’accès depuis l’acteur `properties.isOpen`

### Ouverture (%) (Uniquement pour le mode analogic)

- **Type** : `Number`
- **Description** : La valeur représente le pourcentage d'ouverture affiché( 0 : fermé, 100 : ouvert).

> ⚡Chemin d’accès depuis l’acteur `properties.opening`
