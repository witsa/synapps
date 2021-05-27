---
title: "Acteurs"
parent: Bonnes et Mauvaises pratiques
grand_parent: Documentation Maker
nav_order: 2
---

# Acteurs

Quelques éléments sur l'utilisation des acteurs en général et sur leur particularités.

## La toile

Il faut utiliser les toiles dans le cas où des acteurs doivent se superposer (une image de fond et des acteurs dessus par exemple).

> N'utilisez jamais d'unité relative dans les toiles.

Les unités relatives (`em`, `vmin`, `vh`, `vmax`, `vw`) sont à proscrire dans les toiles. Utilisez uniquement le `px`. S'il faut adapter la toile à l'écran, placez la toile dans une boite à vue.


*(...)*
