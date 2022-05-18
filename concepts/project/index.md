---
title: "Projet"
parent: Concepts
has_children: true
nav_order: 1
---

{% include table_of_content.html %}

# Le projet

Le projet représente l'ensemble des éléments qui permettent de réaliser une synapp. Le projet se matérialise pas un dossier dans votre système de fichier. Il continent tous les fichiers de configuration de la synapp, les définitions de scènes, de composites, des librairies, les images, etc.

## Création d'un projet

Pour créer un nouveau projet, il vous suffit de cliquer sur le bouton **Nouveau projet** dans le menu **Fichier**.

L'interface de choix de projet de base s'affichera alors.

Vous aurez le choix de créer un projet à partir des modèles de base de Studio ou bien utiliser un fichier modèle.

Pour en savoir plus sur la [création de projet](../../quick-start/first-project.md).

Pour en savoir plus sur les [modèles de projet](./project-model.md).

> ⚠️ **ATTENTION**<br>
> **Ne dupliquez pas un projet.** Vous produiriez des problèmes lors de la publication de la synapp et dans la gestion des mots de passe de vos hôtes. Si vous l'avez fait, pour récupérer la situation, modifiez à la main dans le fichier de figuration, le `guid` d'un des deux projets, de préférence avant de l'ouvrir avec Studio.
>
> Pour dupliquer un projet correctement un projet, il faut tout simplement l'exporter sous forme de modèle et créer le nouveau projet à partir de celui-ci.
## Ouvrir un projet

Pour ouvrir un projet présent sur votre système, cliquez sur le bouton **Ouvrir projet** dans le menu **Fichier** et allez chercher le dossier qui le contient.

## Voir le dossier du projet

Pour afficher le dossier du projet ouvert, il suffit de cliquer sur le bouton **Ouvrir le dossier du projet...** dans le menu **Projet**


# la section projet

La section *Projet* dans Synapps Studio permet de définir les éléments essentiels à l'exécution de l'application et à sa construction.

## Généralités

Dans la sous section *Généralités* de la section *Projet*, vous pouvez définir les éléments essentiels de celui-ci.

### Nom du projet
Vous pouvez changer ici le nom de votre projet.

### Nom et label de la synapp
Dans la partie *Identité de la synapp*, vous pouvez définir le nom de la synapp qui apparaîtra dans le REDY, ainsi que le *label* qui sera utilisé pour la récupération de la synapp dans le REDY.

### Numéro de version
Vous pouvez renseigner un numéro de version pour vous aider à suivre les évolution du projet en cours.

### Langues de la synapp
Dans la partie *Divers*, vous pouvez définir les langues qui seront supportées par votre synapp.

Exemple : `fr,es,en` pour indiquer que le *français*, l'*espagnol* et l'*anglais* seront supportés. Le format attendu est le même que celui de la liste des langues disponibles sur [Liste des codes ISO 639-1](https://fr.wikipedia.org/wiki/Liste_des_codes_ISO_639-1).

### Style global de la synapp
Dans la partie *Style global*, vous avez la possibilité de définir la couleur de fond de la synapp. Vous pourrez également définir la couleur d'avant plan , c'est à dire, la couleur *par défaut* des textes de la synapp.

## Hôtes

Dans la sous-section des [hôtes](./host.md), vous pouvez définir les ULI sur lesquels vous pourrez vous connecter pour élaborer votre synapp.
C'est dans cette section aussi que vous pouvez publier votre synapp dans une ULI.

## Fournisseurs de données

Dans cette sous-section, vous pouvez définir les [fournisseurs de données globaux](./data-sources.md) qui seront utilisés par votre synapp.

## Icônes

Vous avez la possibilité de définir [icônes](./icons.md) de votre synapp dans la sous-section dédiée.

## Inclusions

Dans la sous-section [inclusions](./inclusions.md), vous pouvez définir les sources `Javascript` et `CSS` qui seront incluses au chargement de votre synapp.

## Lisez-moi

Cette sous section vous permettra de renseigner et prendre connaissance des informations essentielles de votre projet. C'est une documentation que vous pouvez rédiger vous même.

> Dans chaque modèle de projet, le *lisez-moi* vous donnera les éléments importants qui le caractérisent et vous expliquera comment le personnaliser.

La rédaction du *lisez-moi* s'effectue dans un éditeur intégré dans le language `markdown`, très simple à prendre en main. [`Pour en savoir plus`](https://fr.wikipedia.org/wiki/Markdown)

# Exécution du projet

Dans le menu **Exécuter**, vous pouvez ouvrir un onglet qui exécutera votre synapp dans un onglet dédiée.

## Changement d'hôte

> TODO

## Changement de langue

> TODO

## Exécution dans le navigateur

> TODO
