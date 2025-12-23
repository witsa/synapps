---
title: Types
has_children: true
parent: API JavaScript
---

# Types

## `CssSizeString`

Taille CSS.

Voir les unités [ici](https://developer.mozilla.org/fr/docs/Web/CSS/length){: target="_blank"}

Exemples : `3px`, `1em`, `available`, `min-content`, `max-content`, `fit-content`, `auto`.

## `CssFontFamilyString`

Chaîne de caractères représentant une famille de polices CSS.

Voir les familles de polices [ici](https://developer.mozilla.org/fr/docs/Web/CSS/font-family){: target="_blank"}

Exemples : `Arial, sans-serif`, `"Times New Roman", serif`, `"Courier New", monospace`.

## `CssColorString`

Chaîne de caractères représentant une couleur CSS.

Voir les formats de couleurs [ici](https://developer.mozilla.org/fr/docs/Web/CSS/color_value){: target="_blank"}

Exemples : `#RRGGBB`, `rgb(255, 0, 0)`, `rgba(255, 0, 0, 0.5)`, `hsl(120, 100%, 50%)`, `hsla(120, 100%, 50%, 0.5)`, `red`, `blue`, `transparent`.

## `JSONString`

Chaîne de caractères contenant du JSON.

Exemples :

```js
// généralement obtenu via un `JSON.stringify(variable)`
JSON.stringify({ a: 1, b: 2 }); // '{"a":1,"b":2}'
JSON.stringify([1, 2, 3]); // "[1,2,3]"
JSON.stringify('test'); // '"test"'
JSON.stringify(null); // 'null'
```
