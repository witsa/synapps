---
title: "Disposition | Boite à vue"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="Actor.Layout.ViewBox" %}

# Boite à vue

Acteur qui permet de disposer un acteur enfant en l'adaptant à sa taille.

{% include table_of_content.html %}

# Propriétés

## Type de vue

La boite à vue va disposer son acteur enfant suivant deux possibilités suivant la regle donnée par la propriété *Type de vue* :

- **Visible** : la boite à vue va adapter la taille de son acteur enfant pour qu'il soit entièrement visible dans la boite à vue.
- **Rempli** : la boite à vue va adapter la taille de son acteur enfant pour qu'il la remplisse entièrement.

Dans l'exemple ci-dessous, la boite à vue présente un acteur image bien plus grand qu'elle.

![SynApps](../../assets/concepts/actor/view-box/sample-01.gif)


## Disposition

Voir les règles de disposition avec les [propriétés d'alignement vertical et horizontal](../actor/category-disposition.md#catégorie-disposition-flexible)


## Dépassement de contenu

{% include property_overflow.md %}

La valeur par défaut est **Caché**

> ✔️ **CONSEIL**<br>
> Si votre contenu n'est pas visible, il y a de bonne chance que ce soit à cause de la taille réduite de l'acteur parent.


# Usage

La boite à vue est un acteur très pratique pour afficher un contenu de taille fixe tout en s'assurant qu'il sera visible quelque soit la taille de l'écran.

Par exemple, vous pouvez construire tout une superposition d'un plan avec des éléments positionnés précisément par rapport à lui au pixel prés. Ensuite, vous le placerez dans une boite à vue pour qu'il soit visible quelque soit la taille de l'écran.

> ⚠️ **ATTENTION**<br>
> Ne définissez pas des tailles avec des [unites](../sizes.md) relatives dans les acteurs qui sont à l'intérieure d'une boite à vue. En effet, le résultat sera difficilement prévisible.
>
> **Utiliser toujours des unités fixes : `px`, `cm` et `in`.**
