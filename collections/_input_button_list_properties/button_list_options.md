---
title: Options
section: input_list
propName: ActorButtonListOptions
propPath: properties.Actor.Input.Button
scriptApiClass: Actor.Input.Button
order: 4
---
La propriété spécifique `Options` permet de renseigner les boutons avec le format JSON.

Il y a trois paramètres à renseigner afin de créer un nouveau bouton via le format JSON :
- value (OBLIGATOIRE):
<br>
Renseigne la valeur du bouton.
<br>
La valeur attendue est une chaine de caractère.

- text (OBLIGATOIRE):
<br>
Renseigne le texte qui est affiché sur le bouton.
<br>
La valeur attendue est une chaine de caractère.

- disabled (OPTIONNEL):
<br>
Permet d'activer / désactiver le bouton.
<br>
La valeur attendue est un booléen (true/false).
<br>
Si cette option n'est pas précisée, la valeur par défaut est `False`.

**EXEMPLE**
Voici une liste de 3 boutons, dont le dernier est désactivé :

```
[
  {
    "value": "bouton1",
    "text": "Button 1"
  },
  {
    "value": "bouton2",
    "text": "Button 2"
  },
  {
    "value": "bouton3",
    "text": "Button 3",
    "disabled": true
  }
]
```
