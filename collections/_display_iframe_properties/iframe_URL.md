---
title: URL
section: specifics
propName: url
propPath: properties.url
scriptApiClass: Actor.Display.IframeProperties
order: 1
---

Jokerable
{: .label }

Cette propriété permet de renseigner une URL d'un élément à afficher dans l'acteur.

Cet élément doit être une adresse qui référence une ressource WEB ou plus fréquemment une page WEB de n'importe quel site WEB accessible.

> ⚠️ **ATTENTION**<br>
> Il faut noter que certains sites WEB interdisent l'accès au travers d'une iFrame.

**Jokerable**

Il est possible de placer des jokers (ex.: {% raw %}`{{jokerKey}}`{% endraw %}) dans la définition de l'URL qui seront remplacés par la valeur d'additionnelles de même clé.

Par exemple :

{% raw %}
```URL
https://www.wit.fr/{{section}}/
```
{% endraw %}
Une additionnelle de clé `section` de type *texte* remplacera le joker par sa valeur.
