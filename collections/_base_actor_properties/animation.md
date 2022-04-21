---
title: Animation
section: effects
propName: animation
propPath: properties.animation
scriptApiClass: Actor.BaseActorProperties
order: 8
---

Cette propriété permet de définir des animations CSS sur l'acteur.

Pour déclarer une animation sur un acteur, il est nécessaire en premier lieu de créer un `Acteur HTML`.

Le contenu de cet `Acteur HTML` doit être comme suit :
>\<style>
>
>\@keyframes myAnimationName {
  >
>   instructions de l'animation
>
>}
>
>\</style>

Cela permet ainsi de définir une animation qui a pour nom `myAnimationName` (à changer).

Cette animation pourra par la suite être utilisée par tout autre acteur grâce à son nom de la manière suivante :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/Animation.PNG)

**Pour vous aider :**
La documentation concernant les animations en CSS peut être trouvée [à cette adresse](https://developer.mozilla.org/fr/docs/Web/CSS/animation).
