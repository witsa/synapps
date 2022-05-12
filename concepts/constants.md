---
title: "Librairie de constantes"
parent: Concepts
---

{% include table_of_content.html %}

# Librairie de constantes

La librairie de constante permet de stocker des chaines afin de les utiliser au sein d'une synapp.

## Accès à la librairie

Les constantes se trouvent dans la section librairie à gauche de la fenêtre de Studio.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/library.PNG)

A l'intérieur de cette section, vous pourrez trouver la liste des constantes disponibles.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/libraryList.PNG)


## Création de donnée dans la librairie

Afin de créer de nouvelles constantes il faut cliquer sur le bouton d'ajout situé en bas à gauche de la fenêtre.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addConstant.PNG)

Une fenêtre s'ouvre alors et permet de saisir la `clé` et la `valeur` de la constante.

La `Clé` correspond à l'identifiant qui va être attribué à la constante.
<br>
La `Valeur` correspond à la valeur que prend la constante, cela doit être soit une chaîne de caractère soit un nombre SANS OPÉRATEUR ( +, -, *, /, etc ..).

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/newConstant.PNG)

## Modification de donnée dans la librairie

Pour modifier une donnée dans la libraire de constante, il faut cliquer directement sur la constante que l'on souhaite modifier.

L'interface de modification s'ouvre alors, permettant de saisir une nouvelle `clé` ainsi qu'une nouvelle `valeur`.


## Utilisation des constantes de la librairie dans une synapp

Il y a deux méthodes pour utiliser une donnée issue d'une librairie au sein d'une synapp :

>- Accès grâce aux [liaisons](binding.md).
>- Accès via les [scripts](scripts/index.md).
>
>[⚡ Synapps.Synapp.html#colors]({{ site.baseurl }}/script-api/Synapps.Synapp.html#constants){:target="_blank"}


>Les constantes sont stockés sous format JSON avec la syntaxe suivante pour chaque constante :
>
>`"clé"` : `"valeur"`
>
> Le JSON est directement éditable depuis l'interface.
