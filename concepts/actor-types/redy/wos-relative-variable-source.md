---
title: "Fournisseur de variable relative"
parent: "REDY"
---

{% include links_actor.md apiClass="REDY.Actor.WosRelativeVariableSource" %}

# Fournisseur relatif de variable

Cet acteur fournisseur de donnnée permet de compléter des acteurs [fournisseur de variable](./wos-variable-source.md) ou [de ressource](./resource-source.md) pour communiquer avec une *variable WOS* enfant d'un REDY.

Il permet ainsi de récupérer une variable enfant ou même d'écrire une valeur d'une variable enfant en ne renseignant uniquement que le *sous-chemin* par rapport à une autre variable (définie dans un autre fournisseur).

La variable ou champ de variable qu'il récupère est stockée dans son information `Donnée`, comme pour les autres fournisseurs de donnée.

Il faut noter qu'il ne contient pas de paramètre de requête. En effet, c'est le fournisseur parent qui en est responsable.
D'ailleurs, ce n'est pas lui non plus qui réalise les requêtes mais bien son fournisseur parent.

La donnée récupérée est disponible pour les liaisons ou par script.

{% include table_of_content.html %}

# Propriétés

## Clé parent

Cette propriété permet de renseigner le fournisseur parent de l'acteur par sa clé. Vous aurez le choix parmi tous les fournisseurs de la même scène ou du même composite ainsi que ceux définis parmi les fournisseurs de donnée globaux.

Bien entendu, il sera tout a fait possible de choisir un autre fournisseur relatif de variable aussi.

> 📌 **REMARQUE**<br>
Quoi qu'il en soit, on trouvera un fournisseur normal en remontant dans l'ascendance des acteurs relatifs.

Si vous fournissez par liaison ou par script un fournisseur dans le contexte de donnée de l'acteur et que la clé du parent reste vide, ce fournisseur sera utilisé comme parent. C'est très utile pour paramétrer un composite qui contient un fournisseur relatif mais pas de normal.

## Chemin relatif

Cette propriété va contenir un *chemin relatif* vers la variable à récupérer. C'est un chemin au sens REDY mais par rapport à un autre chemin par ex : `R00001` ou même `R00001.Output`.

Le chemin de référence est une construction de tous les chemins en remontant dans les parents de l'acteur.

Par exemple :

- **Fournisseur 1** :
  - Chemin : `easy.RESS.R00001`

Ce fournisseur pointe sur la ressource `R00001`. Il réalisera les requêtes.

- **Fournisseur relatif 1** :
  - Parent : **Fournisseur 1**
  - Chemin relatif : `Output`

Ce fournisseur est relatif au premier. Il indique être intéressé par la variable enfant `Output` de ce qui est défini dans le fournisseur parent, ici, la ressource `R00001`. Le chemin en entier donne : `easy.RESS.R00001.Output`.

- **Fournisseur relatif 2** :
  - Parent : **Fournisseur relatif 1**
  - champ : *Valeur*

Finalement, ce fournisseur est relatif au *fournisseur relatif 1*. Il indique quant à lui être intéressé par le champ *Valeur* de ce qui résulte du fournisseur parent, ici, la variable `easy.RESS.R00001.Output`. Le chemin en entier donne encore : `easy.RESS.R00001.Output` mais c'est ça *valeur* qui sera inscrite dans la *donnée* de l'acteur.



Comme pour les fournisseurs normaux, un explorateur de paramétrage de REDY aide à saisir ce sous chemin.

## Champ de Variable REDY

Par défaut, c'est la variable toute entière qui est récupérée et placée dans le champ *Donnée*. Si vous voulez récupérer une partie de la variable, vous pouvez indiquer le nom du champ à récupérer parmi les possibilités que vous retrouverez [ici](./wos-variable-source.md#champ-de-variable-redy).

Choisissez *Valeur* si vous voulez écrire dans ce champ. Ainsi, en vous liant avec l'écriture activée à la donnée de l'acteur, vous pourrez écrire dans la variable REDY et envoyer cette valeur automatiquement si la propriété *Écriture au changement* est activée. Sinon par script.

## Mode de lecture

Cette propriété permet de renseigner comment le fournisseur principal doit aller chercher la cible de l'acteur. En effet, rappelons que c'est le fournisseur parent qui réalise les requêtes. Deux modes de lecture sont possibles :

- **Une seule fois** Le fournisseur parent ne fournira la cible que la première fois. Puis, ses autres requêtes n'iront plus la rafraîchir.
- **A chaque rafraîchissement** L'acteur rafraichira la cible à chaque fois que le fournisseur parent fera une requête.

## Écriture au changement?

Cette propriété active/désactive l'enregistrement de la valeur d'une variable dans le REDY si la *donnée* est modifiée par liaison ou par script. Il faut bien entendu que ce soit le *champ* ***Valeur*** qui soit inscrit dans la donnée.

Aussi, pour déclencher l'enregistrement de la donnée changée dans le REDY, il faudra appeler la méthode [⚡ `write()`]({{ site.baseurl }}/script-api/REDY.Actor.WosRelativeVariableSource.html#method:write){:target="_blank"} de l'acteur.

# Événements

## `onDidDataStore`

L'évènement `onDidDataStore` est déclenché à chaque fois que le fournisseur parent a réaliser une requête et que la donnée cible est écrite dans l'information *Donnée*.

> [⚡ `onDidDataStore`]({{ site.baseurl }}/script-api/REDY.Actor.WosRelativeVariableSource.html#event:onDidDataStore){:target="_blank"}

## `onWriteDone`

L'évènement `onWriteDone` est déclenché à chaque fois que l'acteur a réaliser une écriture vers le REDY.

> [⚡ `onWriteDone`]({{ site.baseurl }}/script-api/REDY.Actor.WosRelativeVariableSource.html#event:onWriteDone){:target="_blank"}

# Informations

## Donnée

Vous trouverez dans ce champ la variable ou le champ de variable désigné par l'acteur.

Une liaison avec l'écriture activée permet de modifier la valeur de la variable REDY si l'acteur la désigne.

## Requête en cours ?

Cette information permet de savoir si l'acteur parent est en train de réaliser une requête.

> 💡 **ASTUCE**<br>
Liez la visibilité d'une acteur sur cette information pour le visualiser lorsqu'il est en train de réaliser une requête.


# Usage

Il est possible de créer des fournisseurs dans vos scènes ou composites. Vous pouvez également les créer de manière globale dans la sous-section [Projet / Fournisseurs de variable](../../project/variable-source.md) pour en faire profiter toute votre synapp.


## Grouper des requêtes.

Utiliser les fournisseurs relatifs est une bonne manière de mutualiser les fournisseurs de variable dans vos scènes et composites. Si vous attachez plusieurs relatifs à un même fournisseur de variable, il récupérera en même temps toutes les variables désignées.

Par exemple vous pouvez grouper la requête des sous variables d'une ressource :

- **Fournisseur 1 :** *pour accéder à une ressource*
  - chemin : `easy.RESS.R00001`

- **Fournisseur relatif 1 :** *pour accéder à son état*
  - parent : **Fournisseur 1**
  - champ : *État*

  ▶️ Champ *État* de `easy.RESS.R00001`

- **Fournisseur relatif 2 :** *pour accéder à sa valeur brute*
  - parent : **Fournisseur relatif 1**
  - chemin relatif : `Output`
  - champ : *Valeur*

  ▶️ Champ *Valeur* de `easy.RESS.R00001.Output`


- **Fournisseur relatif 2 :** *pour accéder à son unité*
  - parent : **Fournisseur relatif 2**
  - chemin relatif : `Unit`
  - champ : *Valeur*

  ▶️ Champ *Valeur* de `easy.RESS.R00001.Unit`

Le *Fournisseur 1* réalise en une seule requête la récupération de toutes les variables désignées.

## Chemin dynamique
Avec les fournisseurs relatifs, il est possible de construire un chemin cible dont les segments sont dynamiques :

- **Fournisseur 1 :**
  - chemin : `easy.RESS`

- **Fournisseur relatif 1 :**
  - parent : **Fournisseur 1**
  - chemin relatif : <span style="color: green;">*le sous chemin que vous souhaitez, renseigné par liaison par exemple.*</span>

- **Fournisseur relatif 2 :**
  - parent : **Fournisseur relatif 1**
  - chemin relatif : `Output`
  - champ : *Valeur*
