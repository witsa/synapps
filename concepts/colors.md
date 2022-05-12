---
title: "Librairie de couleur"
parent: Concepts
---


{% include table_of_content.html %}

# Librairie de couleur

La librairie de couleur permet de stocker des codes couleurs afin de les utiliser au sein d'une synapp.

Chaque projet démarre avec une librairie de couleur déjà fournie.

## Accès à la librairie

Les couleurs se trouvent dans la section librairie à gauche de la fenêtre Studio.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/library.PNG)

A l'intérieur de cette section, vous pourrez trouver la liste des couleurs disponibles.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/libraryList.PNG)

## Création de donnée dans la librairie

Afin de créer de nouvelles variables couleur il faut cliquer sur le bouton d'ajout situé en bas à gauche de la fenêtre.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addColor.PNG)

Une fenêtre s'ouvre alors et permet de saisir la `clé` et la `valeur` de la couleur.

La `Clé` correspond à l'identifiant qui va être attribué à la variable couleur.
<br>
La `Valeur` correspond à la valeur que prend la variable couleur, cela doit être soit [un code hexadécimal](https://htmlcolorcodes.com/fr/) soit l'un des [noms d'une couleur](https://developer.mozilla.org/fr/docs/Web/CSS/color_value) soit un code RGB de format RGB(X,X,X).
Une aide est également disponible directement lors de l'édition.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/newColor.PNG)

## Modification de donnée dans la librairie

Pour modifier une donnée dans la libraire de couleur, il faut cliquer directement sur la variable que l'on souhaite modifier.

L'interface de modification s'ouvre alors, permettant de saisir une nouvelle `clé` ainsi qu'une nouvelle `valeur`.


## Utilisation des couleurs de la librairie dans une synapp

Il y a deux méthodes pour utiliser une donnée issue d'une librairie au sein d'une synapp :

>- Accès grâce aux [liaisons](binding.md).
>- Accès via les [scripts](scripts/index.md).
>
>[⚡ Synapps.Synapp.html#colors]({{ site.baseurl }}/script-api/Synapps.Synapp.html#colors){:target="_blank"}


>Les variables sont stockés sous format JSON avec la syntaxe suivante pour chaque couleur :
>
>`"clé"` : `"valeur"`
>
> Le JSON est directement éditable depuis l'interface.
