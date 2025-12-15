---
title: "Technical | Pompe double"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Pompe double (Double Pump)

L'acteur Pompe double représente un système de pompage avec deux moteurs. Chaque pompe peut être contrôlée et surveillée indépendamment pour son état de marche et de défaut.

![Synapps](../../synapps-studio-releases/notes/assets/1.6/double-pump.gif)

## Propriétés spécifiques

### orientation
- **Type** : `String`
- **Description** : Définit l'orientation du dessin des pompes.

### status
- **Type** : `String`
- **Description** : Contrôle l'état de fonctionnement des pompes.
  - `stopped` : Les deux pompes sont à l'arrêt.
  - `running1` : La pompe 1 est en marche.
  - `running2` : La pompe 2 est en marche.

### isFault1
- **Type** : `Boolean`
- **Description** : Si cette propriété est activée (`true`), la pompe 1 est en état de défaut. Son indicateur LED devient rouge et se met à clignoter.

### isFault2
- **Type** : `Boolean`
- **Description** : Si cette propriété est activée (`true`), la pompe 2 est en état de défaut. Son indicateur LED devient rouge et se met à clignoter.

> 📌 **REMARQUE**<br>
> L'état de défaut de chaque pompe est indépendant et a la priorité sur son état de marche.
