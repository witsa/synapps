---
title: "Fournisseurs de donnée"
parent: "Projet"
grand_parent: Concepts
nav_order: 8
---

# Fournisseurs de donnée

Cette partie est dédiée à la définition d'acteurs [fournisseurs de ressource](../actor-types/redy/resource-source.md), [de variable](../actor-types/redy/wos-variable-source.md) et de [requêteur de reflet](../actor-types/redy-reflect-requester.md) qui seront utilisables dans tous le projet.

Il sont disponibles :
- par liaison de type *fournisseur de variable* ou *de reflet*
- ou dans le champ clé parent d'cteur *fournisseur relatif de variable* et *fournisseur de reflet*.

Il sont repérables par le préfixe `global/` dans la liste des champ *Clé parent* ou *Requêteur*.

![Synapp]({{ site.baseUrl }}\assets\concepts\project\global-data-sources\picture1.png)


Un acteur fournisseur de variable est toujours défini à la création d'un projet. Il pointe sur `easy.RESS`. Il sert à faciliter la définition de liaisons de type *fournisseur de variable*.
Un autre acteur requêteur de reflet est également défini à la création d'un projet. Il pointe sur `easy.RESS` aussi. Il sert à faciliter la définition de liaisons de type *Fournisseur de reflet*.

>⚠️ **ATTENTION**<br>
A moins d'avoir une bonne raison, *ne supprimez pas ces deux acteur*.

En plus de ces deux acteurs de base, vous pouvez définir autant d'acteurs fournisseurs de ressource, de variable et de requêteurs de reflet que vous le souhaitez.

Il vont tous s'instancier automatiquement dans toutes les scènes du projet.

## Designer

Le designer reprend complètement celui d'une scène, à la différence prés qu'il n'y a pas d’aperçu. Tout ce passe comme avec les acteurs d'une scène : pour ajouter, paramétrer, supprimer un acteur. Il y juste une réstriction sur les types d'acteurs disponibles, et sur les types de liaison possibles.

> 📌 **Remarque**<br>
> Les laisons vers un acteur, vers un scène/composite vers un fournisseur ou une donnée de fournisseur sont impossibles ici.

## Mode de récupération relatif par défaut

Le mode de récupération des acteurs fournisseurs sont par défaut *Relatif*. C'est à dire qu'ils attendent d'être consommées, d'une manière ou d'une autre, pour commencer à réaliser des requêtes. Il faut entendre par consommation, une liaison de type *fournisseur de variable* ou *fournisseur de reflet* ou une utilisateur dans un acteur *fournisseur relatif de variable* ou *fournisseur de reflet*.

Pour ce qui concerne uniquement les fournisseurs de variable/ressource, si vous désirez que les requêtes soient réalisées dès le chargement de la scène de départ, vous pouvez utiliser le mode *Automatique*.
