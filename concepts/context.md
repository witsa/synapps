---
title: "Contexte de donnée"
parent: Concepts
---

# Contexte de donnée

{% include table_of_content.html %}

{: .important-title }

> 💎 Avancé
>
> Ce concept est destiné aux utilisateurs avancés souhaitant comprendre un fonctionnemment avancé de la Synapps.

Le contexte de donnée (ou _data context_ en anglais) est un concept clé dans le fonctionnenement interne de Synapps. Il permet de définir l'environnement dans lequel un acteur opère, en fournissant des informations sur de la donnée qui est lui est disponible par liaison ou par script.

## Le contexte de donnée d'un acteur

Chaque acteur possède un contexte de donnée. Ce contexte est hérité de son parent dans l'arborescence des acteurs, mais peut être modifié pour un acteur donnée.

Le champ de Contexte de données `dataContext` d'un acteur permet de définir ce contexte et de l'utiliser.

{: .info}

> Le contexte de donnée peut être n'importe quelle type : chaîne de caractères, nombre, objet, tableau, etc ...

## Héritage du contexte de donnée

Le contexte de donnée est hérité de l'acteur parent. Ainsi, si un acteur n'a pas de contexte de donnée défini, il hérite de celui de son parent.

Imaginons l'arborescence suivante :

```
- Scène
  - Acteur A (dataContext: "contextA")
    - Acteur B
      - Acteur C (dataContext: "contextC")
        - Acteur D
    - Acteur E
  - Acteur F
```

| Acteur   | Contexte de donnée      |
| -------- | ----------------------- |
| Acteur A | `contextA` défini sur A |
| Acteur B | `contextA` hérité de A  |
| Acteur C | `contextC` défini sur C |
| Acteur D | `contextC` hérité de C  |
| Acteur E | `contextA` hérité de A  |
| Acteur F | Aucun contexte défini   |

## Composite

Le contexte de donnée traverse l'arborescence des acteurs, même le contenu d'un composite.

Exemple :

```
- Scène
  - Acteur A (dataContext: "contextA")
    - Composite X
      - Acteur interne 1

```

| Acteur           | Contexte de donnée               |
| ---------------- | -------------------------------- |
| Acteur A         | `contextA` défini sur A          |
| Composite X      | `contextA` hérité de A           |
| Acteur interne 1 | `contextA` hérité de Composite X |

{: .tip }

> C'est un excéllent moyen de communiquer des paramètres à l'intérieur d'un composite qui n'a pas de propriété dédiée pour cela ou qu'il n'est pas possible d'accéder à ses propriétés.

## Définition du contexte de donnée

Pour définir le contexte de donnée d'un acteur, il suffit de renseigner le champ `dataContext` dans les propriétés avancées de l'acteur.

### Par liaison

Le champ `dataContext` peut accueillir une liaison. Ainsi, le contexte de donnée peut être dynamique et dépendre d'une autre donnée.

{: .warning }

> Ne pas utiliser une liaison de type contexte de donnée sous peine de provoquer des boucles infinies.<br>
> En effet, vous définiriez le contexte de données d'un acteur en fonction de son propre contexte de données!

### Par script

Le champ `dataContext` peut également être défini par script en utilisant la propriété `dataContext` de l'acteur.

```javascript
actor.dataContext = "newContext";
```

## Utilisation du contexte de donnée

Le contexte de donnée peut être utilisé dans les liaisons et les scripts pour accéder à la donnée associée.

### Par liaison

Dans une liaison, le contexte de donnée peut être utilisé en utilisant une liaison de type contexte de donnée.

Par exemple, imaginons qu'un acteur Texte ait un contexte de données "Un texte exemple". Si vous réalisz une liaison de type contexte de donnée sur le contenu de l'acteur, le texte affiché sera "Un texte exemple".

Autre exemple, si le contexte de donnée est un objet avec une propriété `name`, vous pouvez accéder à cette propriété dans une liaison de type contexte de donnée en renseignant le chemin `name`.

{: .info }
En réalité, toute liaison n'est que la récupération d'un champ dans son contexte de donnée. Les types de liaison comme vers un acteur ou vers la scène ne sont rien d'autre que des raccourcis qui vont chercher l'objet cible pour le placer dans le contexte de donnée de la liaison. Lorsque vous utilisez une liaison de type contexte de donnée, vous récupérez la donnée dans le contexte de donnée courant.

### Par script

Dans un script, le contexte de donnée peut être accédé via la propriété `dataContext` de l'acteur.

```javascript
let context = actor.dataContext;
console.log("Contexte de donnée :", context);
```
