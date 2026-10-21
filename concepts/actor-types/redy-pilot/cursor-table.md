---
title: "Tableau de curseur"
parent: "REDY Pilot"
api_type: redy/cursor-table
since:
  studio: 1.7.0
  runtime: 2.8.0
  redy_pilot: 1.0.0
---

{% include table_of_content.html %}

# Tableau de curseur

C'est un acteur [tableau de données](../display/data-table.md) alimenté directement par le résultat d'un curseur requête.

Il permet d'afficher des données paginées issues d'une base de données SQL via le curseur requête choisi. Les colonnes peuvent être automatiquement créées en fonction des données reçues ou définies manuellement.

Comme pour le tableau de données classique, de nombreux évènements sont disponibles pour interagir avec le tableau ou chaque cellule et le personnaliser.

> Voir la page [Tableau de données](../display/data-table.md) pour plus de détails sur les fonctionnalités du tableau de données.

En revanche, certaines fonctionnalités spécifiques au tabldeau de donndées classique ne sont pas disponibles dans le tableau de curseur, comme la modification directe des données, la pagination manuelle.
Les propriétés *Lignes de données* et *Nombre de pages* sont remplies par l'acteur à chaque réponse du curseur : une valeur saisie est remplacée.

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

## Pagination de la requête

Contrairement au [fournisseur de requête](./cursor-request-source.md), le tableau de curseur n'a pas de propriétés *Mode*, *Limite de résultats* ni *Décalage des résultats* : la limite et le décalage de la requête sont calculés à partir de la *Taille page* et de la page affichée.

## Paramètres de requête

Comme pour le fournisseur de requête, si le curseur SQL utilise des paramètres, Studio propose de créer des additionnels pour les fournir.

## Generation automatique des colonnes

Dans Studio, il est possible d'ajouter une ou toutes les colonnes automatiquement en fonction des données reçues du curseur requête.

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

## ⚡Evènements souris et tactile

C'est la même définition que les [⚡Evènements souris et tactile](../display/data-table.md#evènements-souris-et-tactile) pour le tableau de données classique.

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
