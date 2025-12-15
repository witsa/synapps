---
title: "Technical | Vanne 2 voies"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Vanne 2 voies (2-Way Valve)

L'acteur Vanne 2 voies représente une vanne standard. Son état visuel (ouverte, fermée, en mouvement, en défaut) est déterminé par ses propriétés.

![Synapps](../../synapps-studio-releases/notes/assets/1.6/valve-2-ports.gif)

## Propriétés spécifiques

### Type ``type``
- **Type** : `String`
- **Description** : Définit le style visuel de la vanne. Les options incluent 'digital' pour une vanne binaire (ouverte/fermée) et 'analog' pour une vanne à ouverture variable.

### Orientation ``orientation``
- **Type** : `String`
- **Description** : Définit l'orientation du dessin de la vanne.

### Statut ``status``
- **Type** : `String`
- **Description** : Pour le type `digital`, contrôle l'état de fonctionnement de la vanne.
  - `closed` : La vanne est fermée.
  - `opened` : La vanne est ouverte.
  - `closing` : Affiche une animation de fermeture.
  - `opening` : Affiche une animation d'ouverture.
  - `init` : Affiche un état d'initialisation.

### Valeur ``value``
- **Type** : `Number`
- **Description** : Pour le type `analog`, ce pourcentage (0-100) contrôle le degré d'ouverture affiché.

### En défaut ? ``isFault``
- **Type** : `Boolean`
- **Description** : Si cette propriété est activée (`true`), la vanne est considérée comme en état de défaut. Cet état a la priorité sur les autres.
