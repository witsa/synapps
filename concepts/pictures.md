---
title: "Librairie d'images"
parent: Concepts
---

{% include table_of_content.html %}

# Librairie d'images

La librairie d'image permet de stocker des images dans le dossier `pictures` du projet en cours.<br>
Le but de cette librairie est de rassembler toutes les images les plus volumineuses de la Synapp afin d'y avoir un accès plus rapide et donc d'optimiser les performances de la Synapp.

## Ajout d'images dans la librairie

Il y a deux méthodes afin d'ajouter une image dans la librairie :

**Première méthode**

Via l'aide intégrée à studio.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture.PNG)

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture2.PNG)

Il suffit ici de préciser le nom de l'image qui se situe dans le dossier picture et de valider.<br>
Il est également possible de modifier la clé de l'image.

>*Exemple*
>
>![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture3.PNG)

**Seconde méthode**

Pour cette seconde méthode, il faut ajouter manuellement l'image dans le fichier d'images du projet.

Il est possible d'ouvrir le répertoire à l'aide du bouton suivant :
![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture5.PNG)

Une fois l'image ajoutée, il est nécessaire d'actualiser la librairie.

![SynApps]( {{ site.baseurl }}/assets/concepts/libraries/addPicture4.PNG)

Les images ainsi ajoutées seront par la suite disponible dans la librairie d'image.

## Utilisation des images de la librairie dans une Synapp

Il y a deux méthodes pour utiliser une donnée issue d'une librairie d'image au sein d'une Synapp :

>- Accès grâce aux [liaisons](binding.md).
>- Accès via les [scripts](scripts/index.md).
>
>[⚡ Synapps.Synapp.html#colors]({{ site.baseurl }}/script-api/Synapps.Synapp.html#pictures){:target="_blank"}