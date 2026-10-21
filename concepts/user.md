---
title: "Utilisateur"
parent: Concepts
---

# L'utilisateur

> ⚡ Par script : [référence pour les scripts](./scripts/reference/user.md)

L'utilisateur est un objet global qui représente l'utilisateur connecté au REDY. Il contient des informations sur l'utilisateur comme son identifiant, son nom, son adresse e-mail, etc.

{% include table_of_content.html %}

## D'où vient l'utilisateur

L'utilisateur est le compte REDY avec lequel la [session](./session.md) a été ouverte : celui qui s'est connecté sur la page de connexion, ou celui enregistré dans l'hôte actif quand la synapp s'exécute dans Studio. Il change quand un autre utilisateur se connecte.

## Niveau d'accès

Chaque utilisateur a un niveau d'accès défini dans le REDY : invité, exploitant, installateur ou administrateur. C'est le moyen le plus simple d'adapter une synapp à celui qui l'utilise : afficher, masquer ou désactiver des acteurs selon son niveau.

## Utiliser l'utilisateur

L'utilisateur est accessible :

- **par liaison** : source de type *Utilisateur*, par exemple vers son niveau (`level`) ;
- **par script** : `context.dataStores.redy.session.user`.

Son contenu (identifiant, label, nom, mail, niveau) est décrit dans la [référence pour les scripts](./scripts/reference/user.md).

Tutoriels :

- [Droits d'accès en fonction du niveau utilisateur](../tutorials/user-rules/user-level.md)
- [Droits d'accès en fonction du groupe de ressource](../tutorials/user-rules/user-goup.md)
