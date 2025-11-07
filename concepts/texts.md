---
title: "Librairie de textes"
parent: Concepts
---
{% include table_of_content.html %}

# Librairie de textes

La librairie de textes permet de définir des clés qui seront associées à la traduction d'un texte dans plusieurs langues.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/textsDesigner.PNG)

## Accès à la librairie

Les textes se trouvent dans la section librairie à gauche de la fenêtre de Studio.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/library.PNG)

A l'intérieur de cette section, vous pourrez trouver la liste des textes disponibles.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/libraryList.PNG)


## Création d'un texte

Afin de créer de nouveaux textes, il faut cliquer sur le bouton d'ajout situé en bas à gauche de la fenêtre.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/addText.PNG)

Une fenêtre s'ouvre alors et permet de saisir la `clé` du texte à ajouter, par défaut, une clé unique est renseignée. Mais il est possible de la modifier.


La `Clé` correspond à l'identifiant qui va être utilisé dans une liaison pour référencer le texte dans la bonne langue.

> **✅ Conseil :**<br>
> Choisissez une clé significative pour le texte que vous ajoutez, cela facilitera son identification et son utilisation ultérieure dans la synapp.

## Langues

Chaque colonne du tableau correspond à une langue disponible dans la librairie de texte et permet de renseigner la traduction du texte dans cette langue.

Par défault, il n'y a que le langage `fr` (français) de disponible dans la librairie de texte.

La clé de langue correspond au code ISO 639-1 de la langue.

Pour créer une nouvelle langue, il faut cliquer sur le bouton d'ajout à droite de la ligne des langues.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/addLang.PNG)

Un nouveau langage est ajouté avec une clé unique, celui-ci permet de référencer de nouvelles traduction pour un ou plusieurs textes.

Si vous cliquez plusieurs fois sur le bouton d'ajout, l'italien `it`, l'espagnol `es`, le catalan `ca` et l'anglais `en` seront ajoutés. Si vous continuez à cliquer, des clés génériques `lang1`, `lang2`, etc. seront ajoutées.

Vous pouvez modifier librement la clé de la langue après sa création en cliquant dessus.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/modifyLang.gif)

Une fenêtre s'ouvre et permet de renseigner une nouvelle clé pour la langue, il est possible de supprimer une langue depuis cette fenêtre.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/popupChangeKeyLang.PNG)

### Clé de langue

Comme indiqué précédemment, la clé de langue doit correspondre au code ISO 639-1 de la langue.

Les langues peuvent tout à fait être les ISO de type `en-US`, `en-GB`, etc.

### Langue par défaut

La première langue de la liste est celle par défaut utilisée lorsqu'il n'y a pas de traduction disponible pour la langue de prévisualisation de la synapp. Pour la changer, il suffit de déplacer la colonne de la langue souhaitée en première position.

>![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/switchLang.gif)


### Langue de prévisualisation

La langue de prévisualisation de la synapp est indiquée par une icône située à côté de la clé de la langue. Il est possible de changer la langue de prévisualisation en cliquant sur cette icône.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/preview.png)

Le même bouton est disponible dans les designers de Scènes/Composites pour changer rapidement de langue de prévisualisation.

## Modification des lignes de texte

### Clé de texte

Afin de modifier la clé d'un texte, il faut cliquer sur la clé du texte.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/modifyText.gif)

Une fenêtre s'ouvre et permet de renseigner une nouvelle clé pour le texte.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/popupChangeKeyText.PNG)

> 📌 **REMARQUE**<br>
> Chaque clé doit être unique et ne peut pas être vide.<br>

Afin de supprimmer un texte, il faut cliquer sur la corbeille sur la ligne correspondante au texte que l'on souhaite supprimer.

> ⚠️ **ATTENTION**<br>
>  Lorsqu'un texte est supprimé, toutes ses traductions sont également supprimés.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/removeText.PNG)

### Traductions

La traduction de chaque texte peut être renseignée en la saisissant dans chaque cellule la traduction correspondante.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/text/enterContent.gif)

Laisser une cellule vide signifie qu'il n'y a pas de traduction disponible pour cette langue. La langue par défaut sera alors utilisée.

### Navigation entre cellules

Il est possible de naviguer entre les différents champs de saisie de la librairie de texte avec différents raccourcis :

- `TAB` : Passage à la prochaine cellule de texte.
- `ENTRER` : Passage à la cellule de texte situé en dessous de la cellule selectionnée.

## Utilisation des textes

La méthode principale pour utiliser les textes de la librairie est via les [liaisons](binding.md).

Il faut définir une liaison de type Librairie/Texte sur une propriété d'un acteur. Dans la définition de la liaison, il faut sélectionner la clé du texte que l'on souhaite utiliser dans la liste déroulante.

Une méthode alternative est l'utilisation via les scripts [⚡ Synapps.Synapp.html#text]({{ site.baseurl }}/script-api/Synapps.Synapp.html#texts){:target="_blank"}.

## Format de stockage des textes JSON

> ⚠️ **Attention** à manipuler avec précaution. Toute erreur de syntaxe peut rendre la librairie de textes inutilisable.

Les textes sont stockés sous format JSON avec la syntaxe suivante pour chaque texte :

```JSON
"text1" : {
   "lang1" : "traduction1",
   "lang2" : "traduction2"
 }
```

Une clé de texte possède donc plusieures langues qui contiennent chacun une traduction.

Le JSON est directement éditable depuis l'interface via l'onglet "Configuration des textes" en bas à droite de la page.
