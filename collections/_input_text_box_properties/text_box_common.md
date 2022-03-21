---
title: Boite de saisie
section: specifics
propName: inputTextBox
propPath: properties.inputTextBox
scriptApiClass: Actor.Input.TextBoxProperties
order: 1
---

L'acteur boite de saisie possède le champ `Type de saisie` qui va dicter le comportement de cet acteur en fonction du type selectionné dont chaque choix sera détaillé plus bas.

Cependant, l'acteur possède 7 champs de saisies qui possèdent toujours le même comportement peut importe le `Type de saisie` :

**Taille**

Permet de selectionner entre 3 valeurs de taille :

- Par défaut
- Grand
- Petit

**Longueur Max**

Permet de limiter la taille de la chaine de caractère de `Valeur`.

*Note*
Le caractère vide 'espace' est comptabilisé comme tout autre caractère.

**Mode de saisie**

Ce champ permet de conditionner le type de clavier qui s'affiche sur les appareils mobiles et tablettes.

**Auto Completion?**

Permet d'activer / désactiver la saisie automatique sur les navigateurs.

Ce champ est inutile pour les `Type de saisie` suivants : Mot de passe / Curseur / Couleur.

**Lecture seule?**

Permet d'activer / désactiver la saisie de valeur dans le champ de saisie.

Ce champ est inutile pour les `Type de saisie` suivants : Curseur / Couleur.

**Etat de validation**

Permet de donner une décoration au champ de saisie.

**Actif**

Permet d'activer / désactiver le champ de saisie.