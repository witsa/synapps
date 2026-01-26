---
title: "Fournisseur de requête BETA"
parent: "REDY Pilot BETA"
---

{% include table_of_content.html %}

# Fournisseur de requête

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY Pilot **1.0.0**
{: .label .label-yellow }

Cet acteur permet de créer une source de curseur requêtes pour le pilote REDY. Il consomme un curseur de requête, demande son exécution au pilote REDY suivant des éventuels paramètres, et fournit les résultats dans son champ de dosnnées `data`.

## Propriétés spécifiques

### Requête SQL

Le curseur de requête SQL à exécuter par le pilote REDY.

> ⚡Chemin d’accès depuis l’acteur `properties.label`.

### Mode

Le mode d'exécution de la requête.

- Automatique : la requête est exécutée automatiquement à chaque modification des paramètres.
- Manuel : la requête n'est exécutée que lorsque la fonction `refresh` ou `request` est déclenchée.

> ⚡Chemin d’accès depuis l’acteur `properties.mode`.

### Auto rafraîchissement

Si activé, la requête est automatiquement rafraîchie à intervalle régulier.

> ⚡Chemin d’accès depuis l’acteur `properties.autoRefresh`.

### Délai de rafraîchissement

Le délai en secondes entre chaque rafraîchissement automatique de la requête.

> ⚡Chemin d’accès depuis l’acteur `properties.autoRefreshDelay`.

### Limite de résultats

Le nombre maximum de résultats à retourner par la requête. Par défaut : `10`.

{: note }

> Placez la valeur `-1` pour ne pas appliquer de limite.

> ⚡Chemin d’accès depuis l’acteur `properties.limit`.

### Décalage des résultats

Le nombre de résultats à ignorer au début de la requête. Par défaut : `0`.

> ⚡Chemin d’accès depuis l’acteur `properties.offset`.

## Paramètres de requête

Si le curseur de requête SQL utilise des paramètres, Studio propose de créer des additionnels pour les fournir.

## Événements spécifiques

### ⚡ `onRequestDone`

Événement déclenché lorsque la requête est terminée et que les données sont disponibles.

Dans `data`, vous trouverez un objet avec les propriétés suivantes :

| Propriété | Type                | Description                                                                                                |
| --------- | ------------------- | ---------------------------------------------------------------------------------------------------------- |
| columns   | Tableau de Colonnes | Tableau contenant les définitions des colonnes                                                             |
| rows      | Tableau de tableaux | Les lignes de résultats, chaque ligne étant un tableau de valeurs correspondant aux colonnes, dans l'ordre |
| totalRows | Nombre              | Le nombre total de lignes disponibles (avant application de la limite et du décalage)                      |

L'objet de Colonne contient les propriétés suivantes :

| Propriété | Type   | Description                      |
| --------- | ------ | -------------------------------- |
| key       | Chaîne | Le nom unique de la colonne      |
| type      | Chaîne | Le type de données de la colonne |

En cas d'erreur, un champ `error` est présent dans l'objet de contexte avec les informations de l'erreur.

Exemple de données retournées :

```json
{
  "columns": [
    { "key": "id", "type": "Integer" },
    { "key": "name", "type": "String" }
  ],
  "rows": [
    [1, "Alice"],
    [2, "Bob"]
  ],
  "totalRows": 50
}
```

## Usages

Ce fournisseur de requête peut être utilisé avec des acteurs consommateurs de curseur. Un bon exemple est la [Liste de choix déroulante](../input/dropdown-list.md).

Imaginons que nous voulons remplir une liste déroulante avec les utilisateurs de la base de données.

1. Créez un acteur **Fournisseur de requête REDY Pilot** avec la requête SQL suivante :

```sql
SELECT id AS value, name AS text FROM users ORDER BY name
```

2. Créez un acteur **Liste de choix déroulante**.
3. Dans la propriété **Options** de la liste déroulante, liez-la à la Liste des lignes dans les informations du fournisseur de requête.
4. Ajouter la transformation de la liaison, et ajouter la transformation suivante :

```javascript
return context.getActor("<clé du fournisseur de requête>").getOptionsFromData();
```

Cela remplira automatiquement la liste déroulante avec les utilisateurs de la base de données, en utilisant `id` comme valeur et `name` comme texte affiché.

{: .note }

> Cela marche ici, parce que les colonnes de la requête SQL sont nommées `value` et `text`, ce qui correspond directement aux attentes de la liste déroulante pour ses options.
>
> Si la requête SQL n'a pas les bon noms de colonnes, dans la transformation, vous pouvez faire quelque chose comme ceci :
>
> ```javascript
> return context.getActor("<clé du fournisseur de requête>").getOptionsFromData("id", "name");
> ```
>
> où `id` et `name` sont les noms des colonnes dans les résultats de la requête SQL qui correspondent respectivement à la valeur et au texte des options.

{: .tip }

> Si la liste n'a pas vocation à changer, assurez-vous que la propriété _Auto rafraîchissement_ du fournisseur de requête est désactivée.
