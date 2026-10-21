---
title: "Catégorie Disposition"
parent: Acteur
grand_parent: Concepts
nav_order: 3
---

{% include table_of_content.html %}

# Catégorie Disposition flexible

Cette catégorie regroupe les propriétés relatives à la disposition de l'acteur dans une disposition flexible comme l'[empilement](../actor-types/layout/stack.md), la [boite à vue](../actor-types/layout/view-box.md) ou la [modale](../actor-types/layout/modal.md).

{% include script_api/legend.md %}

{% include script_api/properties.md type="common" names="horizontalAlignment,verticalAlignment" %}

# Catégorie Disposition dans une toile

Cette catégorie regroupe les propriétés relatives à la disposition de l'acteur dans une [toile](../actor-types/layout/canvas.md).


Dans un acteur [toile](../actor-types/layout/canvas.md), les enfants directes sont disposés suivant des coordonnées relativement à ses 4 bords.


{: .info }
> Les positions haute et gauche sont celles qui sont changées lorsqu'on déplace l'acteur dans la toile en glissant la souris.


{: .tip }
> Si vous utilisez deux coordonnées opposées en même temps (haute/basse *ou* droite/gauche) et qu'il n'y a pas d'autres contraintes de taille, l'acteur va s'entendre pour faire respecter à ses bords les règles de position. Par exemple, pour étendre un acteur sur toute la surface d'une toile, vous pouvez définir toutes les positions à `0`. Ainsi, chaque bord sera collé au bord correspondant de la toile.

{% include script_api/properties.md type="common" names="top,left,bottom,right" %}
