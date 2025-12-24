---
title: "Cellule de tableau de données"
parent: "Affichage"
nav_order: 2
---

# Cellule de tableau de données

Studio **1.5.0**
{: .label .label-green }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-green }

{: .important-title }

> 💎 Acteur Avancé
>
> Le tableau de données est un acteur qui nécessite une bonne compréhension de son fonctionnement et de ses propriétés ainsi que des notions de JSON et parfois du JavaScript.

Ce type d'acteur est particulier car il ne peut pas être utilisé directement dans une scène ou un composite. Il est utilisé uniquement comme style d'acteur pour les colonnes d'un acteur **Tableau de données**.

Chaque colonne d'un tableau de données utilise un style d'acteur cellule de tableau de données. Des styles par défaut sont fournis pour chaque type de colonne (voir la page [Tableau de données](./data-table) pour plus de détails).

{: .info }

> Il est possible de créer d'autres styles d'acteur Cellule de donnée pour les personnaliser. Ils seront basés sur les styles par défaut pour les utiliser dans les colonnes de type correspondant.<br/>
> Voir la page [Tableau de données](./data-table) pour plus de détails.

{% include table_of_content.html %}

## Types de colonnes

Chaque type de colonne utilise un jeu de propriétés spécifiques pour configurer l'affichage des données dans les cellules. Les types de colonnes disponibles sont décrits dans la page [Tableau de données](./data-table#types-de-colonnes).

Lorsqu'on crée un style d'acteur cellule de tableau de données, il est important de se baser sur le style correspondant au type de colonne souhaité. Ainsi, les propriétés spécifiques au type de colonne seront disponibles pour la configuration.

Par exemple, pour créer un style d'acteur cellule de tableau de données pour une colonne de type **Nombre**, il faut créer un nouveau style et le baser sur le style par défaut _Nombre_ `table-cell-number`. Cela permettra d'accéder aux propriétés spécifiques pour configurer l'affichage des nombres dans les cellules de cette colonne.

Autre exemple, pour créer un style d'acteur cellule de tableau de données pour l'utiliser comme en-tête de colonne, il faut créer un nouveau style et le baser sur le style par défaut _Texte entête_ `table-header-cell` ou _Texte_ `table-cell-string`. Cela permettra d'accéder aux propriétés spécifiques pour configurer l'affichage des en-têtes de colonnes.

## Propiétés communes

### Valeur

La propriété principale à configurer est la valeur à afficher dans la cellule. Par défaut, la valeur de la donnée est utilisée.

### Dépassement de texte

Par défaut, le texte est tronqué si la largeur de la cellule est insuffisante pour l'afficher en entier. Il est possible de configurer le comportement en cas de dépassement de texte.

- **Tronquer** `truncate`: le texte est coupé et des points de suspension sont ajoutés à la fin.
- **Retour à la ligne** `wrap`: le texte est affiché sur plusieurs lignes si nécessaire.
- **Retour à la ligne (Cassure)** `break`: le texte est affiché sur plusieurs lignes si nécessaire, en cassant les mots si besoin.
- **Sans retour à la ligne** `nowrap`: le texte est affiché en une seule ligne, même s'il dépasse la largeur de la cellule.

> ⚡Chemin d’accès depuis l’acteur `properties.textOverflow`.

### Position verticale

Il est possible de configurer l'alignement vertical du texte dans la cellule. Par défaut, le texte est centré verticalement.

- **Haut** `start`: le texte est aligné en haut de la cellule.
- **Milieu** `center`: le texte est centré verticalement dans la cellule.
- **Bas** `end`: le texte est aligné en bas de la cellule.

> ⚡Chemin d’accès depuis l’acteur `properties.verticalPosition`.

## Basé sur _Texte_ `table-cell-string`

Ce style est utilisé pour les colonnes de type **Texte**. Il permet de configurer l'affichage des données textuelles dans les cellules.

## Basé sur _Nombre_ `table-cell-number`

Ce style est utilisé pour les colonnes de type **Nombre**. Il permet de configurer l'affichage des données numériques dans les cellules.

La propriété **Valeur** est un nombre.

Par défaut l'alignement horizontal est à droite, mais il est possible de le modifier en utilisant la propriété **Alignement du texte** `textAlign` (gauche, centre, droite, justifié).

## Basé sur _Booléen_ `table-cell-boolean`

Ce style est utilisé pour les colonnes de type **Booléen**. Il permet de configurer l'affichage des données booléennes (vrai/faux) dans les cellules. Un texte est affiché selon la valeur (par défaut "Oui" pour vrai et "Non" pour faux).

La propriété **Valeur** est un booléen.

## Basé sur _Booléen image_ `table-cell-boolean-image`

Ce style est utilisé pour les colonnes de type **Booléen (image)**. Il permet de configurer l'affichage des données booléennes (vrai/faux) dans les cellules en utilisant des images et un texte au survol pour représenter les états vrai et faux. Le texte est affiché selon la valeur (par défaut "Oui" pour vrai et "Non" pour faux). Si aucune image n'est configurée, une bulle de couleur verte (vrai) ou rouge (faux) est affichée.

La propriété **Valeur** est un booléen.

### Textes pour vrai/faux

Deux propriétés permettent de configurer le texte affiché pour les états vrai et faux.

Par défaut, les textes sont "Oui" et "Non", mais ils peuvent être personnalisés en utilisant les propriétés suivantes :

> ⚡Chemin d’accès depuis l’acteur `properties.trueText` et `properties.falseText`.

## Basé sur _Date/Heure_ `table-cell-datetime`

Ce style est utilisé pour les colonnes de type **Date/Heure**. Il permet de configurer l'affichage des données de type date et heure dans les cellules.

La propriété **Valeur** est une date/heure au format ISO 8601 (YYYY-MM-DDTHH:mm:ss.sssZ) ou un timestamp (nombre de millisecondes depuis le 1er janvier 1970).

### Format date/heure

Il est possible de configurer le format d'affichage de la date/heure en utilisant la propriété **Format**. Vous pouvez utiliser les formats de [Moment.js](https://momentjs.com/docs/#/displaying/format/){:target="\_blank"} pour personnaliser l'affichage selon vos besoins.

Par défaut, le format est `DD/MM/YYYY HH:mm:ss`.

## Basé sur _Personalisé_ `table-cell-custom`

Ce style est utilisé pour les colonnes de type **Personnalisé**. Il permet de créer des cellules avec un affichage entièrement personnalisé en utilisant un composite. Par défaut, un composite basique est fourni, mais il est possible de créer un composite personnalisé.

### Composite

Pour personnaliser réellement l'affichage, il faut créer un composite qui va définir comment afficher la donnée et ajouter un style d'acteur cellule de tableau de données basé sur _Personnalisé_ `table-cell-custom` qui utilise ce composite.

#### Passage par le contexte de données

Le composite à créer reçoit les mêmes éléments de la cellule que dans l'évènement [`onDidCellRender`](./data-table#contexte-des-évènements) de l'acteur **Tableau de données**. Ils sont disponibles dans le [contexte de données](../../context.md) du composite. Ainsi, elle sont accessibles par script ou via des liaisons vers le contexte de données.

#### Passage par les propriétés du composite

Il est également possible de commander des propriétés du composite en passant un objet dans l'évènement [`onCellContentTransform`](./data-table#oncellcontenttransform) de l'acteur **Tableau de données**.

```javascript
// onCellContentTransform

if (!context.isHeader && context.columnKey === "custom1") {
  // la clé de la colonne est "custom1"
  // Personnalisation de la cellule
  return {
      // Passage d'une propriété "color" au composite
      color: context.rowData.status === "active" ? "green" : "red",
      // Passage d'une propriété "label" au composite
      label: context.rowData.name,
    },
  };
}
```

Dans cet exemple, on passe deux propriétés `color` et `label` au composite de la cellule. La couleur du composite sera changée en fonction de la valeur du champ `status` de la ligne de données, et la propriété scpécifique qui a comme clé `label` sera définie avec la valeur du champ `name` de la ligne de données.
