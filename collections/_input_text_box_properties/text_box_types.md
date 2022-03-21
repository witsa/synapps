---
title: "Type de saisie"
section: specifics
propName: inputTextBox
propPath: properties.inputTextBox
scriptApiClass: Actor.Input.TextBoxProperties
order: 2
---

**TEXTE / MOT DE PASSE**

*Valeur*

La propriété spécifique `Valeur` permet de définir la valeur actuelle de l'acteur.

- Pour `TEXTE` la valeur attendue est une chaine de caractère.

- Pour `MOT DE PASSE` la valeur attendue est une chaine de caractère et celle-ci ne sera pas affiché en clair au niveau du champ de saisie.

*Texte si vide*

La propriété spécifique `Texte si vide` permet de définir le texte à afficher lorsque le champ de saisie de l'acteur est vide.
La valeur attendue est une chaine de caractère.

*Options*

- Pour `TEXTE` UNIQUEMENT

Permet de suggérer à l'utilisateur certaines options en dessous du champ de saisie lorsque le curseur est placé dans le champ de saisie.

Pour suggérer des éléments, il est nécessaire de suivre la syntaxe qui suit :

```["Un Texte","autre texte","un exemple"]```

**NOMBRE**

*Valeur*

La propriété spécifique `Valeur` permet de définir la valeur actuelle de l'acteur.

La valeur attendue est un nombre.

*Texte si vide*

La propriété spécifique `Texte si vide` permet de définir le texte à afficher lorsque le champ de saisie de l'acteur est vide.

La valeur attendue est une chaine de caractère.

*Valeur Min*

Conditionne la valeur que doit prendre le `Nombre` en lui attribuant une borne négative.

*Valeur Max*

Conditionne la valeur que doit prendre le `Nombre` en lui attribuant une borne positive.

*Pas entre deux valeur*

Permet de conditionner l'incrémentation de la `Valeur`.

*Options*

Permet de suggérer à l'utilisateur certaines options de saisie en dessous du champ de saisie lorsque le curseur est placé dans le champ de saisie. Cependant, la valeur suggérée doit forcément respecter la valeur attendue dans le champ `Valeur`.

Pour suggérer des éléments, il est nécessaire de suivre la syntaxe qui suit :

```["45","5000","1337"]```

**CURSEUR**

*Valeur Min*

Conditionne la valeur que doit prendre le `Curseur` en lui attribuant une borne négative.

*Valeur Max*

Conditionne la valeur que doit prendre le `Curseur` en lui attribuant une borne positive.

*Pas entre deux valeur*

Permet de conditionner le pas du `Curseur`.

**DATE**

*Valeur Min*

Conditionne la valeur que doit prendre la `Date` en lui attribuant une borne négative.

Il est possible depuis l'inspecteur d'ouvrir l'aide à la sélection d'une date.

*Valeur Max*

Conditionne la valeur que doit prendre la `Date` en lui attribuant une borne positive.

Il est possible depuis l'inspecteur d'ouvrir l'aide à la sélection d'une date.


**HEURE**

*Valeur Min*

Conditionne la valeur que doit prendre l'`Heure` en lui attribuant une borne négative.

Il est possible depuis l'inspecteur d'ouvrir l'aide à la sélection d'une horaire.

*Valeur Max*

Conditionne la valeur que doit prendre l'`Heure` en lui attribuant une borne positive.

Il est possible depuis l'inspecteur d'ouvrir l'aide à la sélection d'une horaire.


**COULEUR**

*Valeur*

La propriété spécifique `Valeur` permet de définir la couleur de l'acteur.

La valeur attendue est un code hexadécimal.

Un outil permet de récupérer les codés héxadécimaux des couleur et est disponible [à cette adresse](https://htmlcolorcodes.com/fr/).

Il est également possible de cliquer sur le bouton dans l'interface afin de choisir une couleur.