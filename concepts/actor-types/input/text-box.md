---
title: Boite de saisie
parent: "Intéraction"
---

{% include links_actor.md apiClass="Actor.Input.TextBox" %}

# Boite de saisie

L'acteur boite de saisie permet de créer des champs de saisies personnalisables.

{% include table_of_content.html %}

# Propriétés spécifiques

L'acteur boite de saisie possède le champ `Type de saisie` qui va dicter le comportement de cet acteur en fonction du type sélectionné dont chaque choix sera détaillé plus bas.

Cependant, l'acteur possède 7 champs de saisies qui possèdent toujours le même comportement peut importe le `Type de saisie` :

**Taille**

{% include property_size.md %}

**Longueur Max**

Permet de limiter la taille de la chaine de caractère de `Valeur`.

>📌 *REMARQUE*<br>
>Le caractère vide 'espace' est comptabilisé comme tout autre caractère.

**Mode de saisie**

Ce champ permet de conditionner le type de clavier qui s'affiche sur les appareils mobiles et tablettes.

**Auto Completion?**

Permet d'activer / désactiver la saisie automatique sur les navigateurs.

Ce champ est inutile pour les `Type de saisie` suivants : Mot de passe / Curseur / Couleur.

**Lecture seule?**

Permet d'activer / désactiver la saisie de valeur dans le champ de saisie.

Ce champ est inutile pour les `Type de saisie` suivants : Curseur / Couleur.

**État de validation**

Permet de donner une décoration prédéfinie au champ de saisie.

**Actif**

Permet d'activer / désactiver le champ de saisie.

## Type de saisie

**TEXTE / MOT DE PASSE**

*Valeur*

La propriété spécifique `Valeur` permet de définir la valeur actuelle de l'acteur.

- Pour `TEXTE` la valeur attendue est une chaine de caractère.

- Pour `MOT DE PASSE` la valeur attendue est une chaine de caractère et celle-ci ne sera pas affiché en clair au niveau du champ de saisie.

*Texte si vide*

La propriété spécifique `Texte si vide` permet de définir le texte à afficher lorsque le champ de saisie de l'acteur est vide.
La valeur attendue est une chaîne de caractère.

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

La valeur attendue est une chaîne de caractère.

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

Un outil permet de récupérer les codes hexadécimaux des couleur et est disponible [à cette adresse](https://htmlcolorcodes.com/fr/){:target="_blank"}.

Il est également possible de cliquer sur le bouton dans l'interface afin de choisir une couleur.
