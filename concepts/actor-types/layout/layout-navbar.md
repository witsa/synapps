---
title: "Barre de navigation"
parent: "Disposition"
---

{% include links_actor.md apiClass="Actor.Layout.NavBar" %}

# Barre de navigation

La **Barre de navigation** est un menu **horizontal** : ses enfants sont disposés les uns à côté des autres, de gauche à droite. Comme le [Menu de navigation](./layout-nav-menu.md), c’est elle qui porte l’état de la navigation : elle mémorise la scène sélectionnée et distribue les styles actif/inactif à ses enfants.

Elle peut contenir directement des [Boutons de menu](../input/menu-button.md), et des [Groupes de barre de navigation](./layout-navbar-group.md) lorsqu’on souhaite regrouper plusieurs boutons dans un sous‑menu déroulant.

{% include table_of_content.html %}

# Propriétés

## Scène sélectionnée

Définit la clé de la scène actuellement sélectionnée. Cette propriété est mise à jour automatiquement lorsqu’un **Bouton de menu** de la barre est cliqué.

## Ouvrir au survol ?

Détermine comment s’ouvrent les sous‑menus des **Groupes de barre de navigation** :

- **False** _(par défaut)_ : le sous‑menu s’ouvre au clic sur l’entête du groupe.
- **True** : le sous‑menu s’ouvre dès que la souris survole l’entête du groupe, et se referme peu après que la souris l’ait quitté.

## Couleurs de groupe

Ces couleurs s’appliquent aux entêtes des **Groupes de barre de navigation** contenus dans la barre :

- **Couleur de fond du groupe** / **Couleur du texte du groupe** : apparence d’un groupe au repos.
- **Couleur de fond du groupe actif** / **Couleur du texte du groupe actif** : apparence d’un groupe considéré comme actif, c’est‑à‑dire dont l’un des boutons pointe vers la scène sélectionnée.

> ✔️ **CONSEIL**<br>
> Les couleurs de fond acceptent aussi un dégradé CSS (`linear-gradient(...)`, `radial-gradient(...)`).

## Styles des boutons

- **Style du bouton actif** : style appliqué au bouton correspondant à la scène sélectionnée (également appliqué au survol).
- **Style du bouton inactif** : style appliqué aux autres boutons.

> 📌 **REMARQUE**<br>
>
> Les styles actif/inactif proposés sont les styles définis sur l’acteur **Bouton de menu**. Les styles fournis par défaut pour une barre de navigation sont _menu-button-navbar-actif_ et _menu-button-navbar-inactif_.

# Événements

## onMenuSceneSelected

Déclenché lorsque la propriété **Scène sélectionnée** change. L’événement expose la clé de scène sélectionnée.

# Usage

La barre de navigation se place typiquement en haut d’une [Boite à vue](./view-box.md) ou d’un gabarit, avec une hauteur fixe. Elle s’affiche toujours au‑dessus du reste de l’interface afin que les sous‑menus déroulants des groupes ne soient pas masqués par le contenu voisin.

Pour une navigation verticale (menu latéral), utiliser plutôt le [Menu de navigation](./layout-nav-menu.md) et ses [Groupes de navigation](./layout-nav-group.md).
