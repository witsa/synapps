---
title: Contenu
section: specifics
propName: content
propPath: properties.content
scriptApiClass: Actor.Display.HtmlProperties
order: 7
---
Cette propriété permet de définir du contenu HTML dans l'acteur.

**Exemple :**

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


Il est possible d'ajouter des additionnelles au sein de cet acteur.

La clé de l'additionnelle peut être utilisé au sein du `contenu` de l'acteur HTML avec un joker.
Pour utiliser la clé au sein du contenu de l'acteur HTML il faut OBLIGATOIREMENT utiliser le joker `{{cle_additionnelle}}`.

**Pour vous aider :**
La documentation concernant les joker et leurs utilisations peut être trouvée [à cette adresse]().
