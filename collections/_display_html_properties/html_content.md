---
title: Contenu
section: specifics
propName: content
propPath: properties.content
scriptApiClass: Actor.Display.HtmlProperties
order: 7
---

Jokerable
{: .label }

Cette propriété permet de définir du contenu HTML de l'acteur.

**Exemple :**

```html
<div style="background-color: red;">
    <p>
        Ceci est <i>un</i> <b>paragraphe</b>.
    </p>
</div>
```
Résultat :
<div style="background-color: red;">
    <p>
        Ceci est <i>un</i> <b>paragraphe</b>.
    </p>
</div>

**Jokerable**

Il est possible de placer des jokers (ex.: {% raw %}`{{jokerKey}}`{% endraw %}) dans le contenu qui seront remplacés par la valeur d'additionnelles de même clé.

Par exemple :

{% raw %}
```html
<div style="background-color: {{theColor}};">
    <p>
        Ceci est un paragraphe.
    </p>
</div>
```
{% endraw %}
Une additionnelle de clé `theColor` de type *couleur* remplacera le joker par sa valeur.

> **Astuce**<br>
> S'il est possible d'ajouter du style CSS avec une balise HTML `<style>`, il n'est par contre pas possible d'ajouter du code Javascript.
> Pour cela, il faut utiliser les évènements de l'acteur.

**Pour vous aider :**
La documentation concernant les jokers et leurs utilisations peut être trouvée [à cette adresse]().
