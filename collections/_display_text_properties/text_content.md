---
title: Contenu
section: text
propName: ActorText
propPath: properties.Actor.Display.Text
scriptApiClass: Actor.Display.Text
order: 1
---
La propriété spécifique `contenu` de l'acteur texte permet de rédiger du texte afin de l'afficher dans la Synapp.

Il est possible d'ajouter des additionnelles au sein de cet acteur.

La clé de l'additionnelle peut être utilisée au sein du `contenu` de l'acteur texte avec un joker.
Pour utiliser la clé au sein du contenu de l'acteur texte il faut OBLIGATOIREMENT utiliser le joker {% raw %}`{{cle_additionnelle}}`{% endraw %}.

***Exemple :***

**Cas de base :**

Contenu basique de l'acteur :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/BaseC.PNG)

Résultat du contenu de l'acteur :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/BaseT.PNG){: width="450" }

**Cas avec une additionnelle :**

Contenu avec le joker {% raw %}`{{cle}}`{% endraw %} :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/AddiC.PNG)

Résultat dans l'inspecteur avec l'ajout automatique d'une aditionnelle renseignée avec un texte :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/AddiI.PNG)

Résultat du contenu de l'acteur texte :

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_text/AddiT.PNG){: width="450" }



**Pour vous aider :**
La documentation concernant les jokers et leurs utilisations peut être trouvée [à cette adresse]().