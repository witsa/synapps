---
title: "Interaction | Images interrupteur"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="Actor.Input.SwitchImage" %}

# Images interrupteur

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_switch_image/sample01.gif)

Acteur d'interaction qui permet d'afficher un interrupteur à deux états en affichant alternativement des images.

{% include table_of_content.html %}

# Propriétés

## Valeur

Cette propriété permet de faire basculer l'interrupteur.

## Texte pour vrai, texte pour faux

Ces deux propriétés permettent de définir les textes qui s'affichent dans l'interrupteur correspondant à la valeur `true` et à la valeur `false`.

# Événements

## `onSwitched`

L'évènement `onSwitched` est déclenché lorsque l'acteur est basculé.

> [⚡ `onSwitched`]({{ site.baseurl }}/script-api/Actor.Input.SwitchImage.html#event:onSwitched){:target="_blank"}


# Astuces

Cet acteur peut être très utile pour afficher un indicateur avec une image pour chaque état. Il suffit de bien choisir les deux images à afficher, désactiver l'acteur pour éviter qu'un clic de souris le fasse basculer.
