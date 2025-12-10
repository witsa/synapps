---
title: "Technical | Brûleur"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Brûleur (Burner)

L'acteur Brûleur (Burner) représente l'état d'un brûleur. Il affiche visuellement les différents modes de fonctionnement tels que la marche, l'arrêt ou un état de défaut.

![Synapps](../../synapps-studio-releases/notes/assets/1.6/burner.gif)

## Propriétés spécifiques

### Orientation ``orientation``

- **Type** : `String`
- **Description** : Définit l'orientation du brûleur. Les valeurs possibles sont `right` (droite) ou `left` (gauche).

### Statut ``status``
- **Type** : `String`
- **Description** : Indique l'état de fonctionnement du brûleur. Les valeurs possibles sont :
- `stopped` : Arrêté, led éteinte, flamme absente
- `running` : En marche, led allumée, flamme présente
- `standby` : En veille, led clignotante, flamme absente
- `starting` : En démarrage, led clignotante, flamme absente
- `stopping` : En arrêt, led clignotante, flamme présente
- `init` : En initialisation, led clignotante, flamme absente

### En défaut ? ``isFault``
- **Type** : `Boolean`
- **Description** : Indique si le brûleur est en état de défaut (`true`) ou non (`false`).

### En défaut atteinte consigne ? ``isFaultReachSP``
- **Type** : `Boolean`
- **Description** : Indique si le brûleur est en défaut d'atteinte de consigne.
