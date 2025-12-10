---
title: "Technical | Chaudière"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Chaudière (Boiler)

L'acteur Chaudière (Boiler) permet de représenter l'état d'une chaudière industrielle et de son brûleur associé. Il représente visuellement les différents modes de fonctionnement comme la marche, l'arrêt ou un état de défaut.

![Synapps](../../synapps-studio-releases/notes/assets/1.6/boiler.gif)

## Propriétés spécifiques

### Orientation ``orientation``

- **Type** : `String`
- **Description** : Définit l'orientation de la chaudière. Les valeurs possibles sont `right` (droite) ou `left` (gauche).

### Statut ``status``

- **Type** : `String` (Lecture seule)
- **Description** : Indique l'état de fonctionnement de la chaudière. Les valeurs possibles sont :
- `running` (en marche)
- `stopped` (à l'arrêt)
- `starting` (en démarrage)
- `stopping` (en arrêt)

### En défaut? ``isFault``

- **Type** : `Boolean` (Lecture seule)
- **Description** : Indique si la chaudière est en état de défaut (`true`) ou non (`false`).

### Statut du brûleur ``burnerStatus``

- **Type** : `String` (Lecture seule)
- **Description** : Indique le statut du brûleur associé à la chaudière, il existe 9 états possibles:
  - `without` : Sans bruleur
  - `stopped` : Bruleur arrêté, led éteinte, flamme absente
  - `running` : Bruleur en marche, led allumée, flamme présente
  - `standby` : Bruleur en veille, led clignotante, flamme absente
  - `starting` : Bruleur en démarrage, led clignotante, flamme absente
  - `stopping` : Bruleur en arrêt, led clignotante, flamme présente
  - `init` : Bruleur en initialisation, led clignotante, flamme absente
  - `fault` : Bruleur en défaut, led rouge clignotante, flamme absente
  - `faultReachSP` : Bruleur en défaut d'atteinte de consigne, led orange clignotante, flamme présente
