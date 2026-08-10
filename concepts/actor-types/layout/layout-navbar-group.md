---
title: "Groupe de barre de navigation"
parent: "Disposition"
---

{% include links_actor.md apiClass="Actor.Layout.NavBarGroup" %}

# Groupe de barre de navigation

Le **Groupe de barre de navigation** regroupe plusieurs [Boutons de menu](../input/menu-button.md) dans un sous‑menu déroulant. Il s’affiche sous la forme d’une entête cliquable (texte, icône et chevron) placée dans la barre ; les boutons qu’il contient apparaissent dans un panneau qui se déroule **sous** l’entête.

Il se situe à l’intérieur d’une [Barre de navigation](./layout-navbar.md) et n’accepte que des **Boutons de menu** comme enfants.

{% include table_of_content.html %}

# Propriétés

## Contenu

Texte affiché dans l’entête du groupe. Il accepte du HTML et des jokers.

## Icône / Image

Permet d’afficher une icône ou une image dans l’entête. Si une image est définie, elle est prioritaire sur l’icône.

## Position de l’icône

Choix entre **gauche** et **droite** pour l’icône ou l’image, par rapport au texte.

# Fonctionnement

- L’entête du groupe s’ouvre **au clic**, ou **au survol** si la propriété **Ouvrir au survol ?** de la barre de navigation parente est activée. Dans ce mode, le sous‑menu reste ouvert tant que la souris se trouve sur l’entête ou sur le panneau, et se referme peu après l’avoir quitté.
- Le panneau déroulant est ancré sous l’entête et s’affiche au‑dessus du reste de l’interface ; les boutons y sont empilés verticalement.
- Les couleurs de l’entête ne sont pas définies sur le groupe : elles proviennent des **couleurs de groupe** de la barre de navigation parente.
- Le groupe est considéré comme **actif** dès que l’un de ses boutons pointe vers la scène sélectionnée de la barre. Il prend alors les couleurs « groupe actif ».
