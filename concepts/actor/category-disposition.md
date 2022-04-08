---
title: "Catégorie Disposition"
parent: Acteur
grand_parent: Concepts
nav_order: 3
---

{% include table_of_content.html %}

# Catégorie Disposition flexible

Cette catégorie regroupe les propriétés relatives à la disposition de l'acteur dans une disposition flexible comme l'[empilement](../actor-types/layout-stack.md), la [boite à vue](../actor-types/layout-view-box.md) ou la [modale](../actor-types/layout-modal.md).

{% assign sorted = site.base_actor_properties | where: 'section', 'disposition_flex' | sort: 'order' %}

{% for property in sorted %}

{% include actor_property.md property=property %}

{% endfor %}

# Catégorie Disposition dans une toile

Cette catégorie regroupe les propriétés relatives à la disposition de l'acteur dans une [toile](../actor-types/layout-canvas.md).


Dans un acteur [toile](../actor-types/layout-canvas.md), les enfants directes sont disposés suivant des coordonnées relativement à ses 4 bords.


## Position haute
La position haute permet de définir le décalage vertical du bord extérieur haut de l'acteur par rapport au bord intérieur haut de la toile parente. Les bords considérés ici sont :
- bord interne pour la toile, c'est-à-dire qu'il comprend la potentielle marge intérieure haute
- bord externe pour l'acteur enfant, c'est-à-dire qu'il comprend la potentielle marge extérieure haute.

## Position gauche
La position gauche permet de définir le décalage horizontal du bord extérieur gauche de l'acteur par rapport au bord intérieur gauche de la toile parente. Les bords considérés ici sont :
- bord interne pour la toile, c'est-à-dire qu'il comprend la potentielle marge intérieure gauche
- bord externe pour l'acteur enfant, c'est-à-dire qu'il comprend la potentielle marge extérieure gauche.

## Position basse
La position basse permet de définir le décalage vertical du bord extérieur haut de l'acteur par rapport au bord intérieur haut de la toile parente. Les bords considérés ici sont :
- bord interne pour la toile, c'est-à-dire qu'il comprend la potentielle marge intérieure basse
- bord externe pour l'acteur enfant, c'est-à-dire qu'il comprend la potentielle marge extérieure basse.

## Position droite
La position droite permet de définir le décalage horizontal du bord extérieur droite de l'acteur par rapport au bord intérieur droite de la toile parente. Les bords considérés ici sont :
- bord interne pour la toile, c'est-à-dire qu'il comprend la potentielle marge intérieure droite
- bord externe pour l'acteur enfant, c'est-à-dire qu'il comprend la potentielle marge extérieure droite.

> 📌 **REMARQUE**<br>
Les positions haute et gauche sont celles qui sont changées lorsqu'on déplace l'acteur dans la toile en glissant la souris.

> 💡 **ASTUCE**<br>
Si vous utilisez deux coordonnées opposées en même temps (haute/basse *ou* droite/gauche) et qu'il n'y a pas d'autres contraintes de taille, l'acteur va s'entendre pour faire respecter à ses bords les règles de position. Par exemple, pour étendre un acteur sur toute la surface d'une toile, vous pouvez définir toutes les positions à `0`. Ainsi, chaque bord sera collé au bord correspondant de la toile.

## Liens
> - Position haute : {% include actor_property_script.md propName="top" propPath="properties.top" scriptApiClass="Actor.BaseActorProperties" %}
> - Position basse : {% include actor_property_script.md propName="bottom" propPath="properties.bottom" scriptApiClass="Actor.BaseActorProperties" %}
> - Position gauche : {% include actor_property_script.md propName="left" propPath="properties.left" scriptApiClass="Actor.BaseActorProperties" %}
> - Position droite : {% include actor_property_script.md propName="right" propPath="properties.right" scriptApiClass="Actor.BaseActorProperties" %}
