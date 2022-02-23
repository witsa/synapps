---
title: Contenu
section: specifics
propName: content
propPath: properties.content
scriptApiClass: Actor.Display.HtmlProperties
order: 7
---
Cette propriété permet de définir du contenu HTML dans l'acteur.

Exemple :
```
<div style="background-color: red;">
    <p>
        Ceci est un paragraphe.
    </p>
</div>
```


> **Indication** Il est possible d'ajouter du Style CSS par l'intermédiaire de classe à l'intérieur d'une balise HTML `<style>`.
>
> Il n'est par contre pas possible d'ajouter du code Javascript. Pour cela, il faut utiliser les évènements de l'acteur.


Cette propriété peut contenir des jokers  (ex.: `{{name}}`) qui seront complétés par des additionnelles [TODO liens]().
