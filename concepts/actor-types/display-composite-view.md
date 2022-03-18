---
title: "Affichage | Vue de composite"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="Actor.Display.CompositeView" %}

# Vue de composite

Cet acteur permet d'afficher un composite de manière dynamique.

La propriété *Composite* permet de choisir parmi les composites définis dans le projet celui qu'on désire afficher.

Le composite en question est affiché avec ses propriétés par défaut.

> **Astuce**<br>
> Si vous désirez passer des informations au composite, il faut utiliser le [ruissellement de contexte de donnée](../context.md).

Il faut considérer cet acteur comme un "outil" pour dynamiquement, en fonction de données d'une liaison, ou bien par script, afficher le bon composite.
