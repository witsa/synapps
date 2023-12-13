---
title: Epaisseur de la bordure
section: border
propName: borderWidth
propPath: properties.borderWidth
scriptApiClass: Actor.BaseActorProperties
order: 2
---
Cette propriété permet de spécifier l'épaisseur de la bordure décorative de l'acteur.

La valeur attendue est un nombre positif ou une chaine de caractères ( retrouvables dans la documentation ci-dessous ).
L'unité par défaut est le pixel, cependant, cette unité peut être renseignée avec toute autre unité compatible.

Il est possible de renseigner jusqu'à quatre valeurs dans le champ afin de définir différentes tailles en fonction du côté souhaité.

Règle :  `<Haut> <Droit> <Bas> <Gauche>`

Il est à noter que la taille de la bordure occupera de l'espace au sein de l'encadrement de l'acteur.

**Pour vous aider :**
Nous avons ajouté une aide à la saisie, vous y trouverez les caractéristiques nécessaires pour gérer l'épaisseur de la bordure.<br>
Pour y acceder, il suffit de cliquer ici : ↓ en rouge<br>

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/base_properties/borderWidth/is_BorderWidth.png)

Puis vous verrez apparaitre le pop-up suivant ↓<br>

<image src="{{ site.baseurl }}/assets/concepts/actor/base_properties/borderWidth/Helper_BorderWidth.gif" alt="gif de l'aide à la saisi de l'épaisseur de la bordure" style="max-height: 50%; max-width: 50%;"/>

Il est possible de retrouver la documentation de l'épaisseur d'une bordure CSS [à cette adresse](https://developer.mozilla.org/fr/docs/Web/CSS/border-width).
