---
title: Ombre de la bordure
section: border
propName: borderShadow
propPath: properties.borderShadow
scriptApiClass: Actor.BaseActorProperties
order: 5
---
Cette propriété permet de donner une ombre à la bordure décorative de l'acteur.

Cette propriété attend veux valeurs essentielles, et plusieurs valeurs optionnelles.

Exemple : ` box-shadow: A B C D E; `.

Dans cet exemple :
- A (Obligatoire) : est la position X de l'ombre projetée.
- B (Obligatoire) : est la position Y de l'ombre projetée.
- C (Optionnelle) : Permet de contrôler le flou appliqué sur l'ombre ( Plus la valeur est élevée plus l'ombre sera floue).
- D (Optionnelle) : Permet de contrôler la taille que va prendre l'ombre (Les valeurs négative diminuent la taille, tandis que les valeurs positives agrandissent la taille).
- E (Optionnelle) : Permet de donner la couleur à l'ombre projetée (Par défaut noire).

Les valeurs attendues pour les paramètres A,B,D sont des nombres positifs ou négatifs suivit de leur suffixe d'unité (`px,em`,etc ...)
La valeur attendue pour le paramètres C est un nombre positif suivit de son suffixe d'unité (`px,em`,etc ...)
La valeur attendue pour le paramètres E est une couleur ou un code RGB. Un aide pour la liste native des couleurs en CSS peut être trouvée [à cette adresse](https://developer.mozilla.org/fr/docs/Web/CSS/color_value).


**Pour vous aider :**
Nous avons ajouté une aide à la saisie, vous y trouverez les caractéristiques nécessaires pour gérer l'ombre de la bordures<br>
Pour y acceder, il suffit de cliquer ici : ↓ en rouge<br>

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/base_properties/boxShadow/is_BoxShadow.png)

Puis vous verrez apparaitre le pop-up suivant ↓<br>

<image src="{{ site.baseurl }}/assets/concepts/actor/base_properties/boxShadow/Helper_BoxShadow.gif" alt="gif de l'aide à la saisi de l'ombre de la bordure" style="max-height: 50%; max-width: 50%;"/>
Il est possible de retrouver la documentation de l'attribut Bos-Shadow CSS [à cette adresse](https://developer.mozilla.org/fr/docs/Web/CSS/box-shadow).
