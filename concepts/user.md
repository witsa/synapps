---
title: "Utilisateur"
parent: Concepts
---

# L'utilisateur

{% include table_of_content.html %}

L'utilisateur est un objet global qui représente l'utilisateur connecté au REDY. Il contient des informations sur l'utilisateur comme son identifiant, son nom, son adresse e-mail, etc.


## Label

- Champ : `label`
- Type : `string`

Ce champ contient le label de l'utilisateur. C'est un identifiant unique pour chaque utilisateur dans le REDY.

## Nom

- Champ : `name`
- Type : `string`

Ce champ contient le nom complet de l'utilisateur.

## Mail

- Champ : `email`
- Type : `string`

Ce champ contient l'adresse e-mail de l'utilisateur si elle a été renseignée.

## Niveau

- Champ : `level`
- Type : `1|2|3|4`

Ce champ contient le niveau d'accès de l'utilisateur dans le REDY.

- Niveau 1 : Invité
- Niveau 2 : Exploitant
- Niveau 3 : Installateur
- Niveau 4 : Administrateur

{: .info }
> Ce champ est utile pour afficher ou masquer des éléments de l'interface en fonction du niveau d'accès de l'utilisateur.
