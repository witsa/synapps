---
title: Options
section: iFrame
propName: picture
propPath: properties.Image
scriptApiClass: Actor.Display.Iframe
order: 2
---

***Autoriser les scripts***

Cette propriété permet d'activer ou de désactiver les scripts (principalement JavaScript) au sein du site web chargé par l'iFrame.

***Traiter comme même origine***

Cette propriété permet de définir l'origine du site web affiché dans l'iFrame comme ayant la même origine que le site qui affiche l'iFrame.

Si cette propriété est désactivée, les ressources du site d'origine seront donc inaccessible pour l'iFrame, de plus, le site à l'intérieur de l'iFrame aura une origine 'null' ce qui peut empêcher certaines requêtes et limiter certains accès.

*Pour en apprendre plus sur les origines et leurs fonctionnements :*
La documentation MDN peut être trouvée [à cette adresse](https://developer.mozilla.org/fr/docs/Web/Security/Same-origin_policy).

***Autoriser les modales***

Cette propriété permet d'activer / désactiver toute les alertes systèmes qui pourraient survenir à la suite d'une action dans l'iFrame.

***Autoriser les popups***

Cette propriété permet d'activer / désactiver les popups lors de la navigation dans le site web de l'iFrame.

*NOTE*
<br>
Cela peut avoir pour effet de désactiver certains formulaires de connexion.


***Autoriser les formulaire***

Cette propriété permet d'activer / désactiver les formulaires lors de la navigation dans la Synapp.
<br>
**Attention**
<br>
Si l'on désactive cette option, il ne sera plus possible d'utiliser les formulaires de connexion, les formulaires de contact, etc ...