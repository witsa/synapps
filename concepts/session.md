---
title: "Session"
parent: Concepts
---

# La session

> ⚡ Par script : [référence pour les scripts](./scripts/reference/session.md)


La session est un objet global qui représente la session en cours de l'utilisateur. Elle contient des informations sur l'état de la session créée sur le REDY.

{% include table_of_content.html %}

## Ouverture

Pour exécuter une synapp, l'utilisateur doit être authentifié sur le REDY qui l'héberge : c'est l'[hôte](./project/hosts.md) de la synapp.

- Quand la synapp est servie par le REDY, l'utilisateur saisit son identifiant et son mot de passe sur la page de connexion.
- Dans Studio, la connexion utilise les identifiants enregistrés dans l'hôte actif du projet.

Une fois l'authentification réussie, le REDY ouvre une session : un jeton, un identifiant de session, un délai d'expiration et l'[utilisateur](./user.md) connecté, avec son niveau d'accès.

La session est mémorisée par le navigateur : recharger la page ou rouvrir la synapp ne demande pas de se reconnecter tant qu'elle n'a pas expiré.

## Expiration

La session expire au-delà d'un délai sans activité, fixé par le REDY. Chaque requête de la synapp vers le REDY (lecture d'une variable, d'un reflet...) repousse la date d'expiration de ce délai : tant que la synapp travaille, la session reste ouverte.

## Déconnexion

Un script peut déconnecter l'utilisateur et afficher la page de connexion :

```javascript
context.dataStores.redy.logout();
```

## Utiliser la session

La session est accessible :

- **par liaison** : source de type *Session* ; par exemple, le champ `sid` (identifiant de session) permet de construire des URL vers les pages du REDY ;
- **par script** : `context.dataStores.redy.session`, et l'utilisateur connecté par `context.dataStores.redy.session.user`.

Son contenu (identifiant, dates, état d'authentification, utilisateur, hôte) est décrit dans la [référence pour les scripts](./scripts/reference/session.md).
