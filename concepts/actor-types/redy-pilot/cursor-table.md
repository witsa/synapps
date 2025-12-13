---
title: "Tableau de curseur BETA"
parent: "REDY Pilot BETA"
---

{% include links_actor.md apiClass="REDY.Actor.CursorTable" %}

# Tableau de curseur

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY Pilot **1.0.0**
{: .label .label-yellow }

C'est un acteur [tableau de données](../display/data-table.md) alimenté directement par un curseur requête.

Il permet d'afficher des données paginées issues d'une base de données SQL via le curseur requête choisi. Les colonnes peuvent être automatiquement créées en fonction des données reçues ou définies manuellement.

Comme pour le tableau de données classique, de nombreux évènements sont disponibles pour interagir avec le tableau ou chaque cellule et le personnaliser.
