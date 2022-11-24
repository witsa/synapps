---
title: "Librairie de textes"
parent: Concepts
---
{% include table_of_content.html %}

# Librairie de textes

La librairie de textes permet de renseigner des clés de texte ainsi que plusieurs traductions associées qui permettent une traduction dynamique de la synapp.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/textsDesigner.PNG)


## Accès à la librairie

Les textes se trouvent dans la section librairie à gauche de la fenêtre de Studio.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/library.PNG)

A l'intérieur de cette section, vous pourrez trouver la liste des textes disponibles.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/libraryList.PNG)


## Création de donnée dans la librairie

### Texte

Afin de créer de nouveaux textes, il faut cliquer sur le bouton d'ajout situé en bas à gauche de la fenêtre.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/addText.PNG)

Une fenêtre s'ouvre alors et permet de saisir la `clé` du texte à ajouter, par défaut, une clé unique est renseignée.

La `Clé` correspond à l'identifiant qui va être attribué au texte et qui pourra être utilisée dans la synapp.

### Lanuge

Pour créer une nouvelle langue, il faut cliquer sur le bouton d'ajout à droite de la ligne des langues.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/addLang.PNG)

Un nouveau langage est ajouté avec une clé unique, celui-ci permet de référencer de nouvelles traduction pour un ou plusieurs textes.

## Modification de donnée dans la librairie

### Texte

Afin de modifier un texte, il faut cliquer sur la clé du texte.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/modifyText.GIF)

Une fenêtre s'ouvre et permet de renseigner une nouvelle clé pour le texte.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/popupChangeKeyText.PNG)

> 📌 **REMARQUE**<br>
>Chaque clé doit être unique et ne peut pas être vide.<br>
>Il convient de respecter cette règle particulièrement lorsque l'on modifie directement le JSON.<br>
>Lorsqu'un texte est supprimé, toutes ses traductions sont également supprimés.

Afin de supprimmer un texte, il faut cliquer sur la corbeille sur la ligne correspondante au texte que l'on souhaite supprimer.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/removeText.PNG)

### Langue

Pour modifier une langue, il faut cliquer sur la clé de la langue.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/modifyLang.GIF)

Une fenêtre s'ouvre et permet de renseigner une nouvelle clé pour la langue, il est possible de supprimer une langue depuis cette fenêtre.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/popupChangeKeyLang.PNG)

> 📌 **REMARQUE**<br>
>Chaque clé doit être unique et ne peut pas être vide.<br>

### Traduction

Les traductions de chaque textes peuvent être renseignées en saisisant dans chaque cellule la traduction correspondante.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/enterContent.GIf)

## Accessibilité de la librairie de textes

>### Pagination
>La tableau de la librairie de texte contient un nombre limité d'élément par page.<br>
>Il est possible de naviguer d'une page à l'autre grâce aux boutons en haut à droite de la page.<br>
>Il est également possible de changer le nombre d'éléments affichés par page en haut à droite de la page.
>
>![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/pages.PNG)
> 📌 **REMARQUE**<br>
>Si la librairie ne contient qu'une seule page, ce navigateur de page n'est pas accessible.

>### Prévisualisation
>La langue de prévisualisation de la synapp est indiquée par une icône située à côté de la clé de la langue.<br>
>
>![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/preview.PNG)
> 📌 **REMARQUE**<br>
>Si la langue de prévisualition est supprimée, c'est la première lanuge du tableau qui devient la langue de prévisualisation.


>### Organisation des colonnes
>Il est possible d'ordonner les différentes colonnes de la librairie depuis les cellules de clé de la langue.<br>
>
>![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/switchLang.GIF)

>### Navigation
>Il est possible de naviguer entre les différents champs de saisie de la librairie de texte avec différents raccourcis :
>- TAB : Passage à la prochaine cellule de texte.
>- ENTRER : Passage à la cellule de texte situé en dessous de la cellule selectionnée.

## Utilisation des textes de la librairie dans une synapp

Il y a deux méthodes pour utiliser une donnée issue d'une librairie au sein d'une synapp :

>- Accès grâce aux [liaisons](binding.md).
>- Accès via les [scripts](scripts/index.md).
>
>[⚡ Synapps.Synapp.html#text]({{ site.baseurl }}/script-api/Synapps.Synapp.html#texts){:target="_blank"}


>Les textes sont stockés sous format JSON avec la syntaxe suivante pour chaque texte :
>
>"text1" : {<br>
>   "lang1" : "traduction1",<br>
>   "lang2" : "traduction2"<br>
> }
>
> Une clé de texte possède donc plusieures langues qui contiennent chacun une traduction.<br>
> Le JSON est directement éditable depuis l'interface via l'onglet "JSON" en bas à droite de la page.
