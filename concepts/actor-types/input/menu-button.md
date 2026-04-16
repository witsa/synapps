---
title: "Bouton de menu"
parent: "Intéraction"
---

{% include links_actor.md apiClass="Actor.Input.MenuButton" %}

# Bouton de menu

Le **Bouton de menu** est un bouton conçu pour fonctionner avec un **Menu de navigation**. Il met à jour la scène sélectionnée du menu et adapte son style en fonction de l’état actif/inactif. Le style actif est également le style appliqué au bouton au survol.

{% include table_of_content.html %}

# Propriétés

## Scène

Définit la scène ciblée lorsque l’utilisateur clique sur le bouton. Cette valeur est comparée à la **Scène sélectionnée** du Menu pour appliquer le style actif.

## Dépassement de texte

Contrôle l’affichage du texte si celui‑ci dépasse la largeur disponible :

- **Pas de retour à la ligne**
- **Retour à la ligne**
- **Retour à la ligne (cassure)**
- **Tronqué**

## Icône / Image

Permet d’afficher une icône ou une image dans le bouton. Si une image est définie, elle est prioritaire sur l’icône.

## Position de l’icône

Choix entre **gauche** et **droite** par rapport au texte pour l’icône ou l’image.

## Comportement

- Au clic, le bouton met à jour la propriété **Scène sélectionnée** du **Menu de navigation** parent.
- Le style actif/inactif est appliqué automatiquement en fonction de la scène sélectionnée.
- Au survol, le bouton adopte le style actif.
