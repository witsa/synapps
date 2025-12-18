---
title: "Fournisseur d'instruction BETA"
parent: "REDY Pilot BETA"
---

{% include table_of_content.html %}

# Fournisseur d'instruction

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY Pilot **1.0.0**
{: .label .label-yellow }

Cet acteur permet de créer une source de curseur instructions pour le pilote REDY. Il consomme un curseur d'instruction, demande son exécution au pilote REDY suivant des éventuels paramètres, et fournit les résultats dans son champ de données `data`.

## Propriétés spécifiques

### Requête SQL

Le curseur d'instruction SQL à exécuter par le pilote REDY.

> ⚡Chemin d’accès depuis l’acteur `properties.label`.

### Mode

Le mode d'exécution de l'instruction.

- Automatique : l'instruction est exécutée automatiquement à chaque modification des paramètres.
- Manuel : l'instruction n'est exécutée que lorsque la fonction `refresh` ou `request` est déclenchée.

> ⚡Chemin d’accès depuis l’acteur `properties.mode`.

### Auto rafraîchissement

Si activé, l'instruction est automatiquement relancée à intervalle régulier.

> ⚡Chemin d’accès depuis l’acteur `properties.autoRefresh`.

### Délai de rafraîchissement

Le délai en secondes entre chaque rafraîchissement automatique de l'instruction.

> ⚡Chemin d’accès depuis l’acteur `properties.autoRefreshDelay`.

## Paramètres de l'instruction

Si le curseur d'instruction SQL utilise des paramètres, Studio propose de créer des additionnels pour les fournir.

## Événements spécifiques

### ⚡ `onRequestDone`

Événement déclenché lorsque l'instruction est terminée et que les résultats sont disponibles.

Dans `data`, vous trouverez un objet avec les propriétés suivantes :

| Propriété | Type   | Description                         |
| --------- | ------ | ----------------------------------- |
| totalRows | Nombre | Le nombre total de lignes impactées |

En cas d'erreur, un champ `error` est présent dans l'objet de contexte avec les informations de l'erreur.
