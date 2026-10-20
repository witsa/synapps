---
title: "Fournisseur de requête"
parent: "REDY Pilot"
api_type: redy/data-source/cursor-request
since:
  studio: 1.7.0
  runtime: 2.8.0
  redy_pilot: 1.0.0
---

{% include table_of_content.html %}

# Fournisseur de requête

{% include script_api/badges.md %}

Cet acteur permet de créer une source de curseur requêtes pour le pilote REDY. Il consomme un curseur de requête, demande son exécution au pilote REDY suivant des éventuels paramètres, et fournit les résultats dans son champ de dosnnées `data`.

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

## Paramètres de requête

Si le curseur de requête SQL utilise des paramètres, Studio propose de créer des additionnels pour les fournir.

# Informations
{: #informations }

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

{% include script_api/fields.md type=page.api_type %}

# Méthodes
{: #methodes }

{% include script_api/methods.md type=page.api_type %}

# Événements
{: #evenements }

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/actor/).

{% include script_api/events.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}

# Usages

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
