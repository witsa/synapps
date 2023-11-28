---
title: Bords de la bordure
section: border
propName: borderRound
propPath: properties.borderRound
scriptApiClass: Actor.BaseActorProperties
order: 4
---
Cette propriété permet de donner une courbure à la bordure décorative de l'acteur.

La valeur attendue est un nombre entier positif suivit de l'unité désirée (en général le suffixe `px`)
Cette propriété régit la valeur de l'attribut CSS `border-radius`.

> Il est possible de définir une courbure sur tous les coins de l'acteur.
> Ex : `10px`. Ou bien des courbures différentes pour chaque coin : `10px 5px 20px 0px`.
>
> Règle :  `<Haut gauche> <Haut droit> <Bas droit> <Bas gauche>`

**Pour vous aider :**
Nous avons ajouté une aide à la saisie, vous y trouverez les caractéristiques nécessaire pour gérer l'arondi des coins de la bordures<br>
Pour y acceder, il suffit de cliquer ici : ↓ en rouge<br>

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/base_properties/borderRadius/is_borderRadius.png)

Puis vous verrez apparaitre le pop-up suivant ↓<br>

<image src="/assets/concepts/actor/base_properties/borderRadius/Helper_BorderRadius.gif" alt="gif de l'aide à la saisi de l'épaisseur de la bordure" style="max-height: 50%; max-width: 50%;"/>

Il est possible de retrouver la documentation de l'attribut border-radius CSS [à cette adresse](https://developer.mozilla.org/fr/docs/Web/CSS/border-radius).
