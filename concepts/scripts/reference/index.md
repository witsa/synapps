---
title: "Référence"
parent: Scripts
grand_parent: Concepts
has_children: true
nav_order: 1
---

# Référence

Objets accessibles dans les scripts, générés depuis le code :

- [Contexte d'évènement](./context.md) : `context`, présent dans tous les scripts, et ses utilitaires `context.utils` ;
- [Acteur](./actor.md) : membres communs à tous les acteurs (`this`), propriétés et additionnelles, et leurs évènements ;
- [Liaison](./binding.md) : `context.binding` dans les scripts de transformation, `this.getBinding(...)` ;
- [Synapp](./synapp.md) : `context.synapp` ;
- [Scène](./scene.md) : `context.scene`, `context.rootScene` ;
- [Composite](./composite.md) : le composite qui contient l'acteur ;
- [Session](./session.md) : la session de l'utilisateur et l'hôte (`context.dataStores.redy.session`, `context.dataStores.redy.host`) ;
- [Utilisateur](./user.md) : l'utilisateur connecté (`context.dataStores.redy.session.user`) ;
- [Afficheur](./user-agent.md) : l'appareil qui affiche la synapp (`context.synapp.userAgent`).

Les membres propres à chaque type d'acteur sont décrits avec ce [type d'acteur](../../actor-types/index.md).
