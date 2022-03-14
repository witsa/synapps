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
Il est possible de retrouver la documentation de l'attribut border-radius CSS [à cette adresse](https://developer.mozilla.org/fr/docs/Web/CSS/border-radius).
