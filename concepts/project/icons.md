---
title: "Icônes"
parent: "Projet"
grand_parent: Concepts
nav_order: 7
---

{% include table_of_content.html %}

# Gestion des icônes dans Synapps Studio

Les icônes de la synapp permettent de personnaliser, de caractériser votre application.

Ce sont des images carrées, de type `png`. Ils sont de différentes tailles pour correspondre aux attentes du navigateur et appareil mobile. Ils sont 11 au totale.

Par défaut, les icônes de votre synapp sont le logo de Synapps.

## Logo de la synapp

L'icône incontournable est celle qui va servir de logo à la synapp. C'est elle qui est affichée en *splash screen* c'est à dire au démarrage de la synapp, pendant son chargement. c'est aussi lui qui la représente lorsqu'on affiche une liste de synapp.

La taille de cette icône est `255x255`.

## Icônes pour le navigateur

Les icônes de tailles `16x16` et `32x32` sont utilisées par les navigateurs pour illustrer les favoris et les onglets.

## Autres icônes

Tous les autres icônes sont utilisées par les mobiles lorsque la synapp est installée dessus en *progressive web app* (PWA). Voir la procédure([TODO]).


## Poids des icônes

Dans l'absolu, il vaut mieux que les icônes soient légères : quelques `ko` ou dizaines de `ko`. C'est surtout valable pour les 3 principales icônes. Les autres ne seront chargées qu'une seule fois.

## Accès aux icônes

Les icônes se situent dans la sous section "icônes" de la section "Projet".

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconsAccess.PNG)

## Barre d'outil des icônes

La barre d'outil des icônes est visible tout en haut de la fenêtre de gestion des icônes.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconsToolBar.PNG)

L'icône de rafraîchissement sert à actualiser les icônes qui auraient pû être changer dans le dossier des icônes.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/refresh.PNG)

L'icônes de suppression permet de réinitialiser toutes les icônes à celles de base fournies par Synapps.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/deleteAll.PNG)

Enfin, le dernier bouton permet d'ouvrir directement le dossier ou se situent les icônes.

## Modification / Réinitialisation / Génération des icônes

L'interface d'une icône se présente ainsi :

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/icon.PNG)

### Afin de modifier une icône, il y a deux possibilités :

- Cliquer sur l'icône permet de définir manuellement l'icône que l'on souhaite associé à la taille définie.

- Utiliser le bouton `Ouvrir le dossier des icônes du projet ...` et remplacer l'icône souhaitée.
>⚠️ **ATTENTION**<br>
>Pour la seconde méthode, il est nécessaire de remplacer l'icône souhaité avec une image et de lui donner le MEME NOM que l'icône à remplacer.

### Pour réinitialiser une icône vers l'icône de base de Synapps Studio :

Il suffit de cliquer sur le bouton de suppression en haut de l'interface de l'icône.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconToolBar.PNG)

### Pour générer une icône automatiquement à partir d'une image :

Dans un premier temps, il est nécessaire de déposer une image en haut à droit de la fenêtre a l'aide d'un clic sur la zone prévue à cet effet.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconGen.PNG)

Une fois l'image déposée, il est possible de générer des icônes pour toutes les tailles d'icônes à l'aide du bouton situé au dessus de l'interface du générateur d'icône.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconGenready.png)

Il est également possible de générer l'image adaptée pour une seule icône à l'aide du bouton situé au dessus de l'interface d'une icône.

![SynApps]( {{ site.baseurl }}/assets/concepts/icons/iconGenready.png)
