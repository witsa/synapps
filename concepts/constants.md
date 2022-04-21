---
title: "Librairie de constantes"
parent: Concepts
---

{% include table_of_content.html %}

# Librairie de constantes

La librairie de constante permet de stocker des variables stables afin de pouvoir utiliser ces variables au sein d'une Synapp.

>Les variables sont stockés sous format JSON avec la syntaxe suivante pour chaque constante :
>
>`"clé"` : `"valeur"`

## Accès à la librairie

La librairie se trouve dans la section librairie à gauche de la fenêtre Synapps.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/library.PNG)

A l'intérieur de cette section, vous pourrez trouver la liste des librairies disponibles.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/libraryList.PNG)


## Création de donnée dans la librairie

Afin de créer de nouvelles variables constantes, il est nécessaire d'ajouter un couple `"Clé"` : `"Valeur"` au sein du JSON.

La `Clé` correspond à l'identifiant qui va être attribué à la variable constante.
<br>
La `Valeur` correspond à la valeur que prend la variable constante, cela doit être soit une chaine de caractère soit un nombre SANS OPERATEUR ( +, -, *, /, etc ..).

>*Exemples de création de nouvelles variables constantes :*
>
>"Aventurier" : "Casanova",<br>
>"Date de naissance" : 1725

## Utilisation des constantes de la librairie dans une Synapp

Il y a deux méthodes pour utiliser une donnée issue d'une librairie au sein d'une Synapp :

>- Accès grâce aux [liaisons](binding.md).
>- Accès via les [scripts](scripts/index.md).
>
>[⚡ Synapps.Synapp.html#colors]({{ site.baseurl }}/script-api/Synapps.Synapp.html#constants){:target="_blank"}
