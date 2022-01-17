---
title: "Exécuter un script à l'affichage"
parent: Scripts
grand_parent: Concepts
---

# Exécuter un script à l'affichage

## Comment exécuter un script à l'affichage d'une scène ou d'un composite

Que ce soit pour une scène ou un composite, il est possible d'exécuter un script juste à son affichage.

Pour cela, il suffit de définir ce script dans l'évènement `onPostInit` de l'acteur principale de la scène ou du composite.

En effet, lorsqu'une scène ou un composite doit être affichée, l'arborescence des acteurs est construite. Lors de cette construction, les scripts `onInit` sont d'abord exécutés en parcourant l'arborescence des acteurs vers le bas. Puis l'évènement `onPostInit` est exécuté sur chaque acteur, en remontant l'arborescence. Ainsi, lorsque le tour de l'acteur principal est arrivé, tous les acteurs ont été déclarés, toutes les liaisons réalisées.

## liens connexes

- [Cycle de vie d'un acteur](../actor/actor-life-cycle.md)
