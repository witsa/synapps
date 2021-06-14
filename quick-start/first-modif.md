---
title: Premières modifications
parent: Guide de démarrage
nav_order: 4
---

{% include table_of_content.html %}


# Premières modifications : la scène d'accueil

Nous allons modifier le projet de manière à afficher un message de bienvenue en accueil.

Mais d'abord, quelques concepts :

## La scène

Une synapp est composée d’unités d'interface graphique que nous appelons **scène**.

L'application est constituée d’une ou plusieurs scènes que l’utilisateur affiche en navigant de l’une vers l’autre.

![SynApps](../assets/scenes-nav.png)

## Ouverture du designer de scène

Nous allons sélectionner une des scènes du projet. Affichons l'arborescence des scènes du projet :

![SynApps](../assets/first-modif-01.png)

La scène avec le ![SynApps](../assets/start-scene-icon.png) est la celle de démarrage. Mais ce n'est pas cette scène que nous allons modifier ici.

Sélectionnez la scène **Accueil** pour afficher son **designer**.

![SynApps](../assets/first-modif-03.png)

- Au centre se trouve l'**aperçu** de la scène *(A)*
- En dessous de la liste des scènes, sur la gauche, vous trouverez le **plan des acteurs** *(B)*.
- Sur la gauche s'affiche l'**inspecteur** de l'objet que vous sélectionnerez dans le panneau de gauche *(C)*.

## L'acteur

Chaque scène contient les instructions et la programmation des éléments d'interface appelées **acteurs** qui vont du plus simple des boutons d'action à l'acteur qui affiche le détail d'un reflet.
Les acteurs permettent de construire et d’articuler n’importe quel type d’interface, du formulaire au tableau de bord.

![SynApps](../assets/scene-actors.png)

Ils sont organisés sous forme d'arborescence :

![SynApps](../assets/first-modif-04.png)


Le premier acteur, l'**acteur principal** de la scène, `stack1` est de type **Empilement**.

C'est un acteur de disposition. Son role est de disposer les acteurs qu'il va contenir. Dans le cas d'un empilement, il va empiler les acteurs verticalement par défaut.
D'autres types de disposition existent *(voir doc - todo)*.

Nous allons ajouter un acteur **Texte** à l'empilement.

### Ajout

Pour ajouter un acteur, vous allez effectuer un clic droit sur `stack1`. Le menu d'action sur les acteurs va s'afficher.

> **Remarque :** La gestion des scènes s'effectue également par l'intermédiaire d'un menu contextuel sur les éléments de l'arborescence.

![SynApps](../assets/first-modif-05.png)

Choisissez *Ajouter un acteur...*. Le panneau de choix de nouvel acteur va s'afficher.

![SynApps](../assets/first-modif-06.png)


Cliquez sur l'acteur *Texte* qui se trouve dans la section *Affichage*.

L'acteur `text2` a été ajouté dans l'arborescence :

![SynApps](../assets/first-modif-07.png)

Dans l'aperçu, l'acteur se retrouve empilé en dessous de `text1`.

![SynApps](../assets/first-modif-08.png)

### Suppression

Nous allons supprimer le premier acteur qui va être inutile ici, toujours à l'aide du menu contextuel d'acteur.

Cliquez droit sur l'acteur `text1` et choisissez *Supprimer*.

L'acteur à disparu :

![SynApps](../assets/first-modif-09.png)

Et dans l'aperçu :

![SynApps](../assets/first-modif-11.png)


### Modification

Nous allons positionner le texte au centre de la scène. Il s'affichera en dessous de celui qui est déja présent.

Si ce n'est pas déjà le cas, sélectionner l'acteur `text2`.

> Remarque : vous pouvez aussi sélectionner un acteur en cliquant simplement sur son aperçu.

Concentrons nous sur l'inspecteur :

![SynApps](../assets/first-modif-12.png)

Déroulez la partie *Disposition*.

![SynApps](../assets/first-modif-13.png)

Cette section permet de gérer la disposition de l'acteur dans son acteur parent. ici, vous pouvez changer l'alignement de l'acteur et choisir *centré* verticalement et horizontalement.

![SynApps](../assets/first-modif-14.png)

Et dans l'aperçu :

![SynApps](../assets/first-modif-15.png)

> **Remarque :** Les actions réalisées dans le designer sont *annulables*. <br>![SynApps](../assets/first-modif-10.png)<br>Raccourci **Ctrl+Z** / **Ctrl+Shift+Z**

Profitez-en pour jeter un oeil sur les autres sections offertes par l'inspecteur de l'acteur.

Nous allons maintenant changer le contenu du texte :

Cela se passe dans la section *Spécifiques*.

![SynApps](../assets/first-modif-16.png)

Comme son nom l'indique, cette section varie en fonction du type d'acteur qui est sélectionné.

Ici, vous pouvez modifier le texte affiché par l'acteur en cliquant sur le bouton avec un stylo. Le panneau d'édition de texte s'affiche :

![SynApps](../assets/first-modif-17.png)

Saisissez `Salut le monde!` à la place de `Text`. Puis cliquez sur le bouton pour sauver votre saisie.

> **Astuce :** Raccourci pour sauver la saisie **Ctrl+S**

Vous pouvez fermer le panneau en cliquant ailleurs ou directement sur la croix. Le texte a changé dans l'aperçu.

![SynApps](../assets/first-modif-18.png)


## Sauvegarde et Exécution

Nous allons sauvegarder les modifications réalisées en cliquant sur le bouton dédié dans la barre d'action au dessus de l'aperçu de la scène.

> **Astuce :** Raccourci pour sauver la scène **Ctrl+S**

Maintenant, si vous exécuter la synapp (pensez à **Ctrl+R**), vous pourrez voir :

![SynApps](../assets/first-modif-19.png).

## Encore quelques modifications

### Utilisation de librairie

Nous allons maintenant changer la couleur du texte. Pour celà, nous allons nous intéresser à la section *Texte* et plus paticulièrement, le champ *Couleur*.

![SynApps](../assets/first-modif-20.png).

Ce champ attend une [couleur CSS](http://localhost:4000/script-api/global.html#CssColorString){:target="_blank"} qu'il est possible de saisir ou de choisir à l'aide du sélecteur proposé. Vous pouvez en essayer pour visualiser le résultat.

![SynApps](../assets/first-modif-26.png).

Nous allons utiliser la **librairie** de couleur définie dans la synapp et en profiter pour aborder le sujet de la **liaison**.

La simplicité d'édition des interfaces repose entre autres sur ce concept. Les champs des acteurs peuvent être liés à d'autres éléments de l'application, un autre acteur, une couleur, un texte, une image et une donnée dans l’ULI...

Cliquez sur le bouton d'option de champ sur la droite, en forme d'engrenage et choisissez *Lier à...*.

![SynApps](../assets/first-modif-21.png).


Le panneau d'édition de liaison s'affiche alors.

![SynApps](../assets/first-modif-22.png).

Pour l'instant, aucune liaison n'est définie. Mais si vous ouvrez le menu déroulant, vous pourrez observer les sources de liaisons possibles. Choisissez *Librairies/Couleur*.

L'interface a changé :

![SynApps](../assets/first-modif-23.png).

Dans le champ couleur qui est apparu, vous allez pouvoir choisir une des couleurs définies dans la librairie :

![SynApps](../assets/first-modif-24.png).

Choisissez `themeColor` et cliquer sur le bouton *Lier à...* en bas pour valider la création de la liaison.

![SynApps](../assets/first-modif-25.png).

> **Remarque :** La librairie de couleur, comme toutes les autres librairies est accessible dans la rubrique dédiée ![SynApps](../assets/libraries.png) et ne possède pas encore son *designer*. Il faut modifier un fichier `JSON`.

## Prochaine étape
Maintenant, vous pouvez continuer en affichant une variable du REDY [Visualiser un reflet du REDY](./add-scene) de projet Studio.
