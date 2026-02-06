---
title: "Groupe de navigation"
parent: "Disposition"
---

{% include links_actor.md apiClass="Actor.Layout.NavGroup" %}

# Groupe de navigation

Le **Groupe de navigation** organise des boutons de menu sous une entête repliable. Il permet de structurer un menu en sections. Il se situe **obligatoirement** à l’intérieur d’un **Menu de navigation**.

{% include table_of_content.html %}

# Propriétés

## Contenu

Texte affiché dans l’entête du groupe.

## Icône / Image

Permet d’afficher une icône ou une image dans l’entête. Si une image est définie, elle est prioritaire sur l’icône.

## Position de l’icône

Choix entre **gauche** et **droite** pour l’icône ou l’image.

## Groupe ouvert ?

Contrôle l’état replié/déplié du groupe. Un clic sur l’entête inverse automatiquement cette valeur.

## Couleur de fond du groupe

Couleur d’arrière‑plan spécifique à l’entête du groupe.

# Fonctionnement

Le groupe calcule la hauteur de ses enfants (boutons de menu) afin d’animer l’ouverture et la fermeture. Lorsque l’entête est cliqué, la propriété **Groupe ouvert ?** est inversée et les enfants sont affichés ou masqués.
