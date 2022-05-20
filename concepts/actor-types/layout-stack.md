---
title: "Disposition | Empilement"
parent: "Types d'acteur"
grand_parent: Concepts
---


{% include links_actor.md apiClass="Actor.Layout.Stack" %}

# Empilement

Acteur qui permet de disposer ses acteurs enfants en les empilant, soit verticalement, soit horizontalement.

{% include table_of_content.html %}

# Propriétés

## Orientation

L'empilement va disposer ses acteurs enfants suivant la règle donnée par la propriété de même *Orientation* :

- **Verticale** *(par défaut)* : Les acteurs enfants s'empilent les uns en dessous des autres, de haut en bas.
- **Horizontale** : Les acteurs enfants s'empilent les uns à côté des autres, de gauche à droite.

## Disposition

Voir les règles de disposition avec les [propriétés d'alignement vertical et horizontal](../actor/category-disposition.md#catégorie-disposition-flexible)

## Dépassement de contenu

{% include property_overflow.md %}

La valeur par défaut est **Caché**

> ✔️ **CONSEIL**<br>
> Si votre contenu n'est pas visible, il y a de bonne chance que ce soit à cause de la taille réduite de l'acteur parent.


# Usage

L'empilement avec les règles de [disposition flexibles](../actor/category-disposition.md#catégorie-disposition-flexible) sont à la base de la construction d'interface qui peuvent s'adapter à n'importe quelle taille d'écran.
Associées à la disposition par [Toile](./layout-canvas.md) et la [Boite à vue](./layout-view-box.md), ces acteurs permettent de construire n'importe quel type de gabarit.

# Événements

{% include events_layout.md %}
