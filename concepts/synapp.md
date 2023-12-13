---
title: "Synapp"
parent: Concepts
nav_order: 2
---

La synapp est l'application IHM à proprement parler. Elle contient les définitions essentielles à son exécution.

La synapp a une identité, un nom, une icône qui lui est propre.

C'est cet objet qui orchestre l'affichage de la scène en cours et qui va contenir tous les éléments de l'application comme les librairies, les fournisseurs de données, les composites, etc.


![SynApps](../assets/scenes-nav.png)


## Dans Studio

Les réglages de la synapp sont gérés dans Studio dans la sous-section [Projet/Généralités](./project/index.md#généralités).

## Identifiant de la synapp

### Le label

C'est ainsi que le REDY identifie la synapp. Le paramétrage de la synapp dans le REDY est d'ailleurs stockée dans chemin `:easy.SynApps.<son label>`.


### Le `guid`
La synapp porte le `guid` du projet qui a servi à sa création et publication. C'est ce qui permet à un projet de reconnaître **sa** synapp dans le REDY. C'est ce qui permet à Synapps Studio de reconnaître ce projet dans votre système.

> ⚠️ **ATTENTION**<br>
> **Ne dupliquez pas un projet.** En effet, le `guid` serait le même ce qui entraînera des erreurs de publication et de gestion des mots de passe de vos hôtes. Ce n'est vraiment pas recommandé mais si vous l'avez fait, pour récupérer la situation, modifiez à la main dans le fichier de figuration, le `guid` du projet d'un des deux projets, de préférence avant de l'ouvrir avec Studio.
>
> Pour dupliquer un projet correctement un projet, il faut tout simplement l'exporter sous forme de modèle et créer le nouveau projet à partir de celui-ci.

### Le nom de la synapp

Le nom de la synapp est le titre qui apparaît dans l'onglet du navigateur ou la liste des synapps d'un REDY.
