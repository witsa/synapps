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

## Couleur de fond du menu

Couleur d’arrière‑plan de la zone contenant les boutons du groupe. Si aucune couleur n’est définie, la zone reste transparente.

Les couleurs de l’entête, elles, ne sont pas définies ici : elles proviennent des **couleurs de groupe** du **Menu de navigation** parent.

# Fonctionnement

Le groupe calcule la hauteur de ses enfants (boutons de menu) afin d’animer l’ouverture et la fermeture. Lorsque l’entête est cliqué, la propriété **Groupe ouvert ?** est inversée et les enfants sont affichés ou masqués.
