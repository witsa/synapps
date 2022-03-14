---
title: Contenu
section: input
propName: ActorButtonContent
propPath: properties.Actor.input.Button
scriptApiClass: Actor.input.Button
order: 1
---
La propriété spécifique `contenu` de l'acteur bouton permet de rédiger du code HTML à intégrer dans le contenu du bouton.

> **Indication** Il est possible d'ajouter du Style CSS par l'intermédiaire de classe à l'intérieur d'une balise HTML `<style>`.
>
> Il n'est par contre pas possible d'ajouter du code Javascript. Pour cela, il faut utiliser les évènements de l'acteur.

Il est possible d'ajouter des additionnelles au sein de cet acteur.

La clé de l'additionnelle peut être utilisée au sein du `contenu` de l'acteur bouton avec un joker.
Pour utiliser la clé au sein du contenu de l'acteur bouton il faut OBLIGATOIREMENT utiliser le joker {% raw %}`{{cle_additionnelle}}`{% endraw %}.

De plus, si un joker de la forme : {% raw %}`{{cle_additionnelle}}`{% endraw %} est utilisé dans le contenu, une  aide à la création de l'additionnelle sera disponible en dessous du champ `contenu` et l'additionnelle portant la clé renseignée pourra être créée.


**Pour vous aider :**
La documentation concernant les jokers et leurs utilisations peut être trouvée [à cette adresse]().