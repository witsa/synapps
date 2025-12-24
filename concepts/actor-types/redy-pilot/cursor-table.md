---
title: "Tableau de curseur BETA"
parent: "REDY Pilot BETA"
---

{% include table_of_content.html %}

# Tableau de curseur

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY Pilot **1.0.0**
{: .label .label-yellow }

C'est un acteur [tableau de données](../display/data-table.md) alimenté directement par le résultat d'un curseur requête.

Il permet d'afficher des données paginées issues d'une base de données SQL via le curseur requête choisi. Les colonnes peuvent être automatiquement créées en fonction des données reçues ou définies manuellement.

Comme pour le tableau de données classique, de nombreux évènements sont disponibles pour interagir avec le tableau ou chaque cellule et le personnaliser.

> Voir la page [Tableau de données](../display/data-table.md) pour plus de détails sur les fonctionnalités du tableau de données.

En revanche, certaines fonctionnalités spécifiques au tabldeau de donndées classique ne sont pas disponibles dans le tableau de curseur, comme la modification directe des données, la pagination manuelle.
Les propriétés spécifiques et évènements suivants ne sont pas disponibles :

- Lignes de données
- Nombre de pages

## Propriétés spécifiques concernant le curseur

### Requête SQL

C'est la même définition que la propriété [Requête SQL](./cursor-request-source.md#requête-sql) pour le fournisseur de requête.

### Mode

C'est la même définition que la propriété [Mode](./cursor-request-source.md#mode) pour le fournisseur de requête.

### Auto rafraîchissement

C'est la même définition que la propriété [Auto rafraîchissement](./cursor-request-source.md#auto-rafraîchissement) pour le fournisseur de requête.

### Délai de rafraîchissement

C'est la même définition que la propriété [Délai de rafraîchissement](./cursor-request-source.md#délai-de-rafraîchissement) pour le fournisseur de requête.

### Limite de résultats

C'est la même définition que la propriété [Limite de résultats](./cursor-request-source.md#limite-de-résultats) pour le fournisseur de requête.

### Décalage des résultats

C'est la même définition que la propriété [Décalage des résultats](./cursor-request-source.md#décalage-des-résultats) pour le fournisseur de requête.

## Paramètres de requête

Comme pour le fournisseur de requête, si le curseur SQL utilise des paramètres, Studio propose de créer des additionnels pour les fournir.

## Propriétés spécifiques concernant le tableau

### Colonnes

C'est la même définition que la propriété [Colonnes](../display/data-table.md#colonnes) pour le tableau de données classique.

### Generation automatique des colonnes

Dans Studio, il est possible d'ajouter une ou toutes les colonnes automatiquement en fonction des données reçues du curseur requête.

### En-tête ?

C'est la même définition que la propriété [En-tête](../display/data-table.md#en-tête) pour le tableau de données classique.

### Pagination ?

C'est la même définition que la propriété [Pagination](../display/data-table.md#pagination) pour le tableau de données classique.

### Style d'acteur cellule d'en-tête

C'est la même définition que la propriété [Style d'acteur cellule d'en-tête](../display/data-table.md#style-dacteur-cellule-den-tete) pour le tableau de données classique.

## Évènements spécifiques

### ⚡onRequestDone

Événement déclenché lorsque la requête du curseur est terminée et que les résultats sont disponibles.
C'est la même définition que l'évènement [⚡onRequestDone](./cursor-request-source.md#onrequestdone) pour le fournisseur de requête.

### ⚡onWillCellRender

C'est la même définition que l'évènement [⚡onWillCellRender](../display/data-table.md#onwillcellrender) pour le tableau de données classique.

### ⚡onCellContentTransform

C'est la même définition que l'évènement [⚡onCellContentTransform](../display/data-table.md#oncellcontenttransform) pour le tableau de données classique.

### ⚡onDidCellRender

C'est la même définition que l'évènement [⚡onDidCellRender](../display/data-table.md#ondidcellrender) pour le tableau de données classique.

### ⚡onDidTableRender

C'est la même définition que l'évènement [⚡onDidTableRender](../display/data-table.md#ondidtablerender) pour le tableau de données classique.

### ⚡onChangeDataPage

C'est la même définition que l'évènement [⚡onChangeDataPage](../display/data-table.md#onchangedatapage) pour le tableau de données classique. Mais elle n'est pas faite pour alimenter le tableau de curseur car la pagination est gérée automatiquement.

### ⚡Evènements souris et tactile

C'est la même définition que les [⚡Evènements souris et tactile](../display/data-table.md#évènements-souris-et-tactile) pour le tableau de données classique.

## Champs d'informations

### Ligne de données

Le champ `dataRows` permet d'obtenir les ligne de données directement sous forme d'un tableau d'objets à la différence de la propriété qui contient le JSON sous forme de texte.

### Nombre de lignes

Le champ `rowsCount` permet d'obtenir le nombre de lignes de données actuellement présentes dans le tableau.

### Colonnes

Le champ `columns` permet d'obtenir les définitions des colonnes directement sous forme d'un tableau d'objets à la différence de la propriété qui contient le JSON sous forme de texte.

### Numéro de page

Le champ `page` permet d'obtenir le numéro de la page actuellement affichée dans le tableau de données.
