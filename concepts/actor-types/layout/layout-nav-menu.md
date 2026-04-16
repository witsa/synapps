---
title: "Menu de navigation"
parent: "Disposition"
---

{% include links_actor.md apiClass="Actor.Layout.NavMenu" %}

# Menu de navigation

Le **Menu de navigation** est le conteneur principal qui gère l’état de la navigation. Il porte la scène sélectionnée et distribue les styles actif/inactif à ses enfants (groupes et boutons).

{% include table_of_content.html %}

# Propriétés

## Scène sélectionnée

Définit la clé de la scène actuellement sélectionnée. Cette propriété est mise à jour automatiquement lorsqu’un **Bouton de menu** est cliqué.

## Couleurs de groupe

- **Couleur de fond du groupe** : couleur d’arrière‑plan des entêtes de groupes.
- **Couleur du texte** : couleur du texte des entêtes de groupes.

## Styles des boutons

- **Style du bouton actif** : style appliqué au bouton correspondant à la scène sélectionnée.
- **Style du bouton inactif** : style appliqué aux autres boutons.

> 📌 **REMARQUE**<br>
>
> Les styles actif/inactif sont les styles définis sur l’acteur **Bouton de menu**.

# Événements

## onMenuSceneSelected

Déclenché lorsque la propriété **Scène sélectionnée** change. L’événement expose la clé de scène sélectionnée.
