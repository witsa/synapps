---
title: "Session"
parent: Concepts
---

# La session

La session est un objet global qui représente la session en cours de l'utilisateur. Elle contient des informations sur l'état de la session créée sur le REDY.

{% include table_of_content.html %}

## L'identifiant de session

- Champ : `sid`
- Type : `string`

Chaque session possède un identifiant unique.

{: .tip }
> On le retrouve dans l'URL des REDY sous la forme `/WSID<sid>/easy/...`. C'est d'ailleurs grâce à cet identifiant qu'il est possible de construire des URL directes vers des éléments du REDY.

Exemple d'utilisation en liaison : Vous désirez afficher dans une iframe les tableaux de bord du REDY. Vous pouvez construire l'URL de l'iframe en utilisant un joker et une liaison vers le champ `sid` de la session.

{% raw %}
```
/WSID{{sid}}/easy/dashboard
```
{% endraw %}

Ensuite, sur l'additionnelle pour compléter l'URL, vous ajoutez une liaison vers le champ `sid` de la session.

Exemple  de l'acteur :
{% raw %}
```
SYNAPPS-STUDIO-ACTOR|{"type":"display/iframe","key":"iframe1","properties":{"url":"/WSID{{sid}}/easy/dashboard","height":"680px","width":"1280px"},"additionalDefs":{"sid":{"type":"text"}},"bindings":{"additionals.sid":{"sourceType":"session","path":"sid"}}}
```
{% endraw %}

## Délai d'expiration

- Champ : `expirationTimeout`
- Type : `number`

Ce champ indique le délai d'expiration de la session en secondes.

## Date d'expiration

- Champ : `expirationDate`
- Type : `MomentJS Date`

Ce champ indique la date et l'heure d'expiration de la session au format MomentJS.

{: .info }
> Ce champ est mis à jour automatiquement en fonction de l'activité de requêtes :  à chaque requête, la date d'expiration est recalculée en fonction du délai d'expiration.

## Authentifié ?

- Champ : `isAuthenticated`
- Type : `boolean`

Ce champ indique si la session est authentifiée ou non.

## Authenification en cours ?

- Champ : `isAuthenticating`
- Type : `boolean`

Ce champ indique si la session est en cours d'authentification.

## Utilisateur

- Champ : `user`
- Type : `User Object`

Ce champ contient l'objet utilisateur associé à la session. Voir la page [Utilisateur](./user.md) pour plus de détails sur l'objet utilisateur.

## Hôte

- Champ : `host`
- Type : `Host Object`

Ce champ contient l'objet hôte associé à la session. Voir la page [Hôte](./project/hosts.md) pour plus de détails sur l'objet hôte.
