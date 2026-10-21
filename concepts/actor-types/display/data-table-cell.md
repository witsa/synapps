---
title: "Cellule de tableau de données"
parent: "Affichage"
grand_parent: "Types d'acteur"
nav_order: 8
api_type: display/data-table-cell
since:
  studio: 1.5.0
  runtime: 2.8.0
  redy: 16.4.0
---

# Cellule de tableau de données

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

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Informations
{: #informations }

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

{% include script_api/fields.md type=page.api_type %}

# Méthodes
{: #methodes }

{% include script_api/methods.md type=page.api_type %}

# Événements
{: #evenements }

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/scripts/reference/actor.html).

{% include script_api/events.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}

# Types de colonnes

Chaque type de colonne utilise un jeu de propriétés spécifiques pour configurer l'affichage des données dans les cellules. Les types de colonnes disponibles sont décrits dans la page [Tableau de données](./data-table#types-de-colonnes).

Lorsqu'on crée un style d'acteur cellule de tableau de données, il est important de se baser sur le style correspondant au type de colonne souhaité. Ainsi, les propriétés spécifiques au type de colonne seront disponibles pour la configuration.

Par exemple, pour créer un style d'acteur cellule de tableau de données pour une colonne de type **Nombre**, il faut créer un nouveau style et le baser sur le style par défaut _Nombre_ `table-cell-number`. Cela permettra d'accéder aux propriétés spécifiques pour configurer l'affichage des nombres dans les cellules de cette colonne.

Autre exemple, pour créer un style d'acteur cellule de tableau de données pour l'utiliser comme en-tête de colonne, il faut créer un nouveau style et le baser sur le style par défaut _Texte entête_ `table-cell-string-header` ou _Texte_ `table-cell-string`. Cela permettra d'accéder aux propriétés spécifiques pour configurer l'affichage des en-têtes de colonnes.

# Basé sur _Texte_ `table-cell-string`

Ce style est utilisé pour les colonnes de type **Texte**. Il permet de configurer l'affichage des données textuelles dans les cellules.

# Basé sur _Nombre_ `table-cell-number`

Ce style est utilisé pour les colonnes de type **Nombre**. Il permet de configurer l'affichage des données numériques dans les cellules.

La propriété **Valeur** est un nombre.

Par défaut l'alignement horizontal est à droite, mais il est possible de le modifier en utilisant la propriété **Alignement du texte** `textAlign` (gauche, centre, droite, justifié).

# Basé sur _Booléen_ `table-cell-boolean`

Ce style est utilisé pour les colonnes de type **Booléen**. Il permet de configurer l'affichage des données booléennes (vrai/faux) dans les cellules. Un texte est affiché selon la valeur (par défaut "Oui" pour vrai et "Non" pour faux).

La propriété **Valeur** est un booléen.

# Basé sur _Booléen image_ `table-cell-boolean-image`

Ce style est utilisé pour les colonnes de type **Booléen (image)**. Il permet de configurer l'affichage des données booléennes (vrai/faux) dans les cellules en utilisant des images et un texte au survol pour représenter les états vrai et faux. Le texte est affiché selon la valeur (par défaut "Oui" pour vrai et "Non" pour faux). Si aucune image n'est configurée, une bulle de couleur verte (vrai) ou rouge (faux) est affichée.

La propriété **Valeur** est un booléen.

# Basé sur _Date/Heure_ `table-cell-datetime`

Ce style est utilisé pour les colonnes de type **Date/Heure**. Il permet de configurer l'affichage des données de type date et heure dans les cellules.

La propriété **Valeur** est une date/heure au format ISO 8601 (YYYY-MM-DDTHH:mm:ss.sssZ) ou un timestamp (nombre de millisecondes depuis le 1er janvier 1970).

# Basé sur _Personalisé_ `table-cell-custom`

Ce style est utilisé pour les colonnes de type **Personnalisé**. Il permet de créer des cellules avec un affichage entièrement personnalisé en utilisant un composite. Par défaut, un composite basique est fourni, mais il est possible de créer un composite personnalisé.
