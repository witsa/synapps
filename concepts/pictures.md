---
title: "Librairie d'images"
parent: Concepts
---

{% include table_of_content.html %}

# Librairie d'images

La librairie d'images permet de stocker des images dans le dossier `pictures` du projet en cours.<br>
Le but de cette librairie est de rassembler toutes les images les plus volumineuses de la Synapp afin d'y avoir un accès plus rapide et donc d'optimiser les performances de la Synapp.

## Accès à la librairie

La librairie se trouve dans la section librairie à gauche de la fenêtre Synapps.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/library.PNG)

A l'intérieur de cette section, vous pourrez trouver la liste des librairies disponibles.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/libraryList.PNG)


## Ajout d'images dans la librairie

Afin d'ajouter une image dans la librairie, il faut impérativement ajouter l'image souhaitée dans le dossier `pictures` du projet.

Il est possible d'accéder à ce dossier par le bouton suivant :

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture5.PNG)

>📌*Remarque*
>
>Il est possible d'insérer des dossiers et sous dossiers d'images. <br>
>La fonction d'actualisation parcours toute l'arborescence des fichiers afin de référencer toutes les images contenue dans le dossier `pictures`.


Une fois l'image ajoutée dans le dossier, il y a deux méthodes pour ajouter cette image à la librairie.

**Ajout automatique à la librairie**

Celle-ci devient disponible à l'ajout via l'aide :

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/helpAddPic.PNG)

Toutefois, si l'image n'apparait pas, il est possible d'actualiser afin de détecter les éventuels ajouts dans le dossier `pictures`.

>📌*Remarque*
>
>Lorsque l'on ajoute plusieurs images dans le dossier, il est possible d'utiliser l'option `Ajouter toutes les images` afin d'ajouter toutes les images listées directement à la librairie.

**Ajout manuel à la librairie**

L'image peut être ajoutée manuellement de la façon suivante :

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture.PNG)

>Préciser le chemin de l'image depuis le dossier `pictures`.
>![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture2.PNG)

>Une prévisualisation de l'image est disponible.<br>
>Il est également possible de changer la clé de l'image que l'on s'apprêtte à ajouter.<br>
>![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture3.PNG)<br>
>Valider une fois les informations renseignés pour ajouter l'image à la librairie.





## Utilisation des images de la librairie dans une Synapp

Il y a deux méthodes pour utiliser une donnée issue d'une librairie d'images au sein d'une Synapp :

>- Accès grâce aux [liaisons](binding.md).
>- Accès via les [scripts](scripts/index.md).
>
>[⚡ Synapps.Synapp.html#pictures]({{ site.baseurl }}/script-api/Synapps.Synapp.html#pictures){:target="_blank"}