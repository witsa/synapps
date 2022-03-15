---
title: Dépassement de texte
section: specifics
propName: textOverflow
propPath: properties.textOverflow
scriptApiClass: Actor.Input.ButtonListProperties

order: 6
---
La propriété spécifique `Dépassement de texte` permet de gérer l'affichage du texte dans le cas ou la taille du conteneur ne suffit pas à afficher l'entièreté du texte.


Il existe donc trois options pour cette propriété :

- Sans retour à la ligne.
- Retour à la ligne.
- Tronqué.

Voici des exemples pour chacun des exemples :

**Sans retour à la ligne**

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_button/buttonClassic.PNG)

**Retour à la ligne**

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_button/buttonOverwrite.PNG)

**ATTENTION :**
La taille verticale de l'acteur est automatiquement adaptée à la taille du texte sauf si celle ci est fixée.

**Tronqué**

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_button/buttonTruncat.PNG)
