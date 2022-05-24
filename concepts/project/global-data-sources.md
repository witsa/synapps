---
title: "Fournisseurs de donnée"
parent: "Projet"
grand_parent: Concepts
nav_order: 8
---

# Fournisseurs de donnée globaux

Cette sous-section est dédiée à la définition d'acteurs [fournisseurs de ressource](../actor-types/redy-resource-source.md), [de variable](../actor-types/redy-wos-variable-source.md) et [de variable relative](../actor-types/redy-wos-relative-variable-source.md) qui pourront être utilisés dans tous le projet.

Il sont disponibles par liaison de type *fournisseur de variable* ou dans le champ clé parent des acteurs fournisseur de variable relative.

Un acteur fournisseur de variable est toujours défini à la création d'un projet. Il pointe sur `easy.RESS`. Il sert à faciliter la définition de liaisons de type *fournisseur de variable*.

>⚠️ **ATTENTION**<br>
A moins d'avoir une bonne raison, *ne supprimez pas cet acteur*.

# Designer

Le designer reprend complètement celui d'une scène, à la différence prés qu'il n'y a pas d’aperçu.

# Particularité

Le mode de récupération des acteurs fournisseurs sont par défaut *Relatif*. C'est à dire qu'ils attendent d'être consommées, d'une manière ou d'une autre, pour commencer à réaliser des requêtes.

Si vous désirez que les requêtes soient réalisée dès le chargement de la scène de départ, vous pouvez utiliser le mode *Automatique*.
