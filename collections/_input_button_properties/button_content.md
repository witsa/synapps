---
title: Contenu
section: specifics
propName: content
propPath: properties.content
scriptApiClass: Actor.input.ButtonProperties
order: 1
---

Jokerable
{: .label }

Cette propriété permet de définir du contenu HTML de l'acteur.

**Exemple :**

<div class="code-example" markdown="1">

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_button/button01.png)

</div>


```html
Ceci est <i>un</i> <b style="background-color: red;">bouton</b>
```


**Jokerable**

Il est possible de placer des jokers (ex.: {% raw %}`{{jokerKey}}`{% endraw %}) dans le contenu qui seront remplacés par la valeur d'additionnelles de même clé.

Par exemple :

{% raw %}
```html
Ceci est <i>un</i> <b style="background-color: {{theColor}};">bouton</b>.

```
{% endraw %}
Une additionnelle de clé `theColor` de type *couleur* remplacera le joker par sa valeur.



> **Astuce**<br>
> S'il est possible d'ajouter du style CSS avec une balise HTML `<style>`, il n'est par contre pas possible d'ajouter du code Javascript.
> Pour cela, il faut utiliser les évènements de l'acteur.

**Pour vous aider :**
La documentation concernant les jokers et leurs utilisations peut être trouvée [à cette adresse]().
