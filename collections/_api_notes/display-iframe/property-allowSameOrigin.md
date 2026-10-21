---
api_type: display/iframe
kind: property
name: allowSameOrigin
---
Cette propriété permet de d'autoriser que le site web affiché de même origine soit considéré de la sorte.

Si cette propriété est désactivée, les ressources du site d'origine seront donc inaccessible pour l'iFrame alors même qu'il est vraiment sur la même origine. De plus, le site à l'intérieur de l'iFrame aura une origine 'null' ce qui peut empêcher certaines requêtes et limiter certains accès.

*Pour en apprendre plus sur les origines et leurs fonctionnements :*
La documentation MDN peut être trouvée [à cette adresse](https://developer.mozilla.org/fr/docs/Web/Security/Same-origin_policy){:target="_blank"}.
