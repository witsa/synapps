---
title: "Additionnelles"
parent: Concepts
nav_order: 7
---

{% include table_of_content.html %}

# Additionnelles

Les additionnelles sont des propriétés comme vous pouvez en retrouver sur les acteurs mais qu'il est possible d'ajouter sur des objets de Synapps.
L'avantage ici est, qu'une fois créée, cette nouvelle propriété est disponible dans l'inspecteur de l'objet auquel elle appartient.

Les acteurs, les scènes et les composites peuvent accueillir des additionnelles. C'est ainsi que l'on crée des paramètres de scène et les propriétés spécifiques d'un composite.

Un additionnelle peut être le siège ou la source d'une [liaison](./binding.md). Elle peut être utilisée dans un script. Elle donne lieu également aux [évènements de changement de valeur de propriété](./scripts/actor-life-cycle.md#changement-de-valeur-de-propriété-dun-acteur).

## Options communes

### Clé
Une additionnelle est identifiée grace à sa clé. Elle doit être unique sur l'objet auquel elle appartient.

### Nom
Dans l'inspecteur, vous pouvez définir le nom qui apparaîtra en face de la propriété créée. Si vous ne le définissez pas, c'est sa clé qui sera utilisée en guise de nom.

### Description

Vous pouvez définir une description de l'additionnelle pour aider à comprendre son rôle. Elle s'affiche au survol du nom de la propriété et dans le cas du type *texte* en impression dans la zone de saisie vide.

### Aide
Vous pouvez définir un texte d'aide qui s'affiche en dessous de l'additionnelle.

### Vide accepté ?

Cette option permet d'indiquer si l'additionnelle peut être vide ou pas.

### Lecture seule ?

Parfois, vous voudrez que l'additionnelle ne soit pas éditable dans le designer. Cette option permet de désactiver l'édition.

### Modification

Dans le cas des additionnelles sur acteur et composite, il est possible de spécifier le type de modification que l'additionnelle entraîne dans son cycle de vie. Voir dans la section qui explique [les modifications](./scripts/actor-life-cycle.md#changement-de-valeur-de-propriété-dun-acteur)

### Présent dans l'URL ?

Dans le cas d'un paramètre de scène, il est possible d'indiquer s'il doit apparaitre ou pas dans l'URL. Voir dans la section qui explique les [paramètres de scène](./scene.md#paramètres-de-scène)

## Types d'additionnelle

Il existe plusieurs type d'additionnelle :

- Texte

Permet d'obtenir une propriété pour saisir du texte.

- Nombre

Permet d'obtenir une propriété pour saisir un nombre.

Il est possible de définir aussi un maximum et un minimum, ainsi que le pas lors d'un changement de valeur par glissement. Il est possible d'ajouter une unité informative.

- Taille

Permet d'obtenir une propriété pour saisir une taille. Ressemble à la propriété *Nombre* mais permet en plus de gérer les unités de type taille.

Il est possible de définir la valeur neutre.

Voir [la section qui explique les unités de taille](./sizes.md)

- Booléen

Permet d'obtenir une propriété avec un bouton à bascule.

- Image

Permet d'obtenir une propriété pour ajouter une image.

- Couleur

Permet d'obtenir une propriété pour saisir une couleur.

- Icône
Permet d'obtenir une propriété pour obtenir la clé d'une icône de la bibliothèque de Synapps.

<!-- ![image](https://user-images.githubusercontent.com/35595723/124151000-646ede80-da92-11eb-8003-4235f467aaa1.png) -->

- Date

Permet d'obtenir une propriété pour saisir une date avec en option une date minimum et une date maximum.

- Sélection simple **ALPHA**

Permettra dans un avenir proche la saisie d'un option parmi une liste.

- Sélection multiple **ALPHA**

Permettra dans un avenir proche la saisie de plusieurs options parmi une liste.

- Acteur

Permet de choisir la clé d'un acteur parmi ceux de la scène ou du composite courant. Une option permet d'activer ou pas la possibilité de choisir l'acteur actuel. Il est possible de filtrer les acteurs disponibles par leur type.

- Scène

Permet de choisir la clé d'une scène parmi celles de la synapp. Une option permet d'activer ou pas la possibilité de choisir la scène actuelle.

- Composite

Permet de choisir la clé d'un composite parmi ceux de la synapp. Une option permet d'activer ou pas la possibilité de choisir le composite actuel.

- Code

Permet de saisir du code dans différents langages, notamment le `HTML`, le `CSS`, le `JavaScript`, le `Markdown`, le `JSON` et du `texte`.

L'éditeur de code de cette additionnelle est conçu principalement comme un outil d'aide à la syntaxe. Il permet aux utilisateurs de saisir du code de manière efficace en fournissant des suggestions et des corrections automatiques. Il est important de noter que la valeur stockée dans l'additionnelle est une chaîne de caractères.

- Chemin de variable

Permet de choisir un chemin de variable REDY. Plusieurs options permettent d'affiner les possibilités affichée par l'explorateur de variable.

### Additionnelles de complément

Dans certains types d'acteur, des additionnelles peuvent être utilisées pour compléter des définitions de propriétés. C'est le cas pas exemple des acteurs à contenu comme le [bouton](./actor-types/input-button.md) ou il est possible de compléter des jokers par les valeurs d'additionnelle.

Les paramètres de scènes sont renseignés par des additionnelles également dans les acteur écran pour paramétrer la scène choisie.
