---
title: Contenu
section: specifics
propName: content
propPath: properties.content
scriptApiClass: Actor.Display.TextProperties
order: 1
---

Jokerable
{: .label }


La propriété spécifique `contenu` permet de rédiger du texte que l'acteur affichera dans la scène.


***Exemple :***

**Cas de base :**

Contenu basique de l'acteur :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/BaseC.PNG)

Résultat du contenu de l'acteur :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/BaseT.PNG){: width="450" }


**Jokerable**

Il est possible de placer des jokers dans le contenu qui seront remplacés par la valeur d'additionnelles de même clé.

Contenu avec le joker {% raw %}`{{cle}}`{% endraw %} :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/AddiC.PNG)

Résultat dans l'inspecteur avec l'ajout automatique d'une additionnelle renseignée avec un texte :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/AddiI.PNG)

Résultat du contenu de l'acteur texte :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/AddiT.PNG){: width="450" }

**Pour vous aider :**
La documentation concernant les jokers et leurs utilisations peut être trouvée [à cette adresse]().
