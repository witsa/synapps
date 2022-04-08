---
title: "Interaction | Bouton interrupteur"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include links_actor.md apiClass="Actor.Input.SwitchButton" %}

# Bouton interrupteur

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_switch_button/sample01.gif)

Acteur d'interaction qui permet d'afficher un interrupteur à deux états.

{% include table_of_content.html %}

# Propriétés

## Valeur

Cette propriété permet de faire basculer l'interrupteur.

## Texte pour vrai, texte pour faux

Ces deux propriétés permettent de définir les textes qui s'affichent dans l'interrupteur correspondant à la valeur `true` et à la valeur `false`.

## Mode pour vrai, mode pour faux

Ces deux propriétés permettent de définir le mode de couleur de l'interrupteur correspondant à la valeur `true` et à la valeur `false`. Ce sont les mêmes mode que pour l'acteur [*bouton*](./input_button.md). La propriété *Outline* permet aussi de gérer les variantes de couleur.

## Taille

{% include property_size.md %}

# Événements

## `onSwitched`

L'évènement `onSwitched` est déclenché lorsque l'acteur est basculé.

> [⚡ `onSwitched`]({{ site.baseurl }}/script-api/Actor.Input.SwitchButton.html#event:onSwitched){:target="_blank"}
