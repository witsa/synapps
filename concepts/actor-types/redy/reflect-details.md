---
title: "Détails de reflet"
parent: "REDY"
---

{% include table_of_content.html %}

# Détails de reflet

L'acteur *Détails de reflet* est un composant conçu pour afficher dynamiquement les informations détaillées et gérer les commandes pour n'importe quel type de reflet.

## Fonctionnement

Cet acteur s'adapte automatiquement au type de reflet que vous lui indiquez. Une fois configuré avec le chemin vers un reflet (par exemple, vers une chaudière ou une vanne) :

1.  Il **Affiche la vue détaillée appropriée** avec toutes les informations pertinentes et, le cas échéant, les commandes spécifiques à cet équipement.
2.  Il **gère l'envoi de commandes** si le reflet est commandable, le détail de reflet présente les commandes disponibles et permet à l'utilisateur de les exécuter directement depuis l'interface.

## Propriétés spécifiques

Il existe deux types de configuration pour cet acteur :
- **Autonome** : L'acteur gère lui-même les requêtes vers le REDY lorsque la propriété **Autonome** `isAutonomous` est vraie afin obtenir et rafraîchir les données du reflet. Dans ce mode, il n'a pas besoin d'un acteur requêteur externe. La propriété **Requêteur** `requesterKey` est ignorée.
- **Non autonome** : L'acteur s'appuie sur un acteur requêteur de reflet lorsque la propriété **Autonome** `isAutonomous` est fausse afin d'effectuer les requêtes. Cela permet de centraliser les requêtes et d'optimiser les performances si plusieurs acteurs *Détails de reflet* ou d'autre acteur de reflet sont utilisés dans la même scène.

### Autonome
- **Type** : `Boolean`
- **Description** : Indique si l'acteur fonctionne de manière autonome, sans nécessiter d'acteur requêteur.

> ⚡Chemin d’accès depuis l’acteur `properties.isAutonomous`.

### Requêteur

{: .info }
>
> Cette propriété est uniquement prise en compte lorsque le mode **Autonome** est **désactivé**.

- **Type** : `String`
- **Description** : La clé de l'acteur requêteur responsable de la communication avec le serveur REDY. Nécessaire si `isAutonomous` est désactivé.

> ⚡Chemin d’accès depuis l’acteur `properties.requesterKey`.


### Auto raffraichi?
- **Type** : `Boolean`
- **Description** : Indique si l'acteur doit automatiquement rafraîchir les données du reflet lorsque de nouvelles données sont disponibles.

> ⚡Chemin d’accès depuis l’acteur `properties.autoRefresh`.

### Délai

{: .info }
>
> Cette propriété est uniquement prise en compte lorsque le mode **Autonome** est **activé**.

- **Type** : `Number`
- **Description** : Le délai en secondes entre chaque rafraîchissement automatique des données du reflet.

> ⚡Chemin d’accès depuis l’acteur `properties.autoRefreshDelay`.

### Reflet
- **Type** : `String`
- **Description** : Le chemin vers le reflet que cet acteur doit afficher depuis `:easy.RESS`. Par exemple, `R00001` pour une ressource spécifique. C'est la propriété principale pour lier l'acteur à un équipement.

> ⚡Chemin d’accès depuis l’acteur `properties.reflectPath`.

### Avec icône
- **Type** : `Boolean`
- **Description** : Active ou désactive l'affichage de l'icône associée au reflet.

> ⚡Chemin d’accès depuis l’acteur `properties.withIcon`.

### Avec nom
- **Type** : `Boolean`
- **Description** : Active ou désactive l'affichage du nom du reflet.

> ⚡Chemin d’accès depuis l’acteur `properties.withName`.

### Avec date
- **Type** : `Boolean`
- **Description** : Active ou désactive l'affichage de la date de dernière mise à jour des données du reflet.

> ⚡Chemin d’accès depuis l’acteur `properties.withLastRefreshDate`.

### Commandable?
- **Type** : `Boolean`
- **Description** : Si activée (`true`), permet à l'utilisateur d'envoyer des commandes au reflet via l'interface fournie par cet acteur, si, bien entendu, le reflet est lui-même commandable.

> ⚡Chemin d’accès depuis l’acteur `properties.allowCommand`.

### Vertical?
- **Type** : `Boolean`
- **Description** : Si activée (`true`), organise les éléments (icône, nom, détails) verticalement. Sinon, ils sont disposés horizontalement.

> ⚡Chemin d’accès depuis l’acteur `properties.isVertical`.

### Mode de commande
- **Type** : `String`
- **Description** : Définit le mode des commandes.

  - Confirmation `action`: Chaque commande nécessite une confirmation de l'utilisateur avant d'être envoyée.
  - Sans confirmation `auto`: Les commandes sont envoyées immédiatement après un changement, sans confirmation.
  - Manuel `manual`: Les commandes sont mises en attente et doivent être envoyées manuellement, par script.

> ⚡Chemin d’accès depuis l’acteur `properties.submitMode`.

## Conseils et optimisations

**Centralisation des requêtes** : Si vous avez plusieurs acteurs "Détails de reflet" dans votre scène, il est recommandé de ne pas les paramétrer comme `autonome` et d'utiliser un **requêteur de reflet commun**.
Cette pratique permet de mutualiser les requête et d'optimiser les performances globales de votre scène. Cela permet également de synchroniser les détails de reflet entre eux.


## Reflets du REDY supportés par Synapps

Voici la liste des types de reflets REDY que Synapps est capable de reconnaître et d'afficher en détail.

| Reflet dans Synapps | type Synapps | Reflets dans REDY |
|---------------------|------| -------------------|
| Agenda | `agenda` | - Reflet Agenda<br> - Reflet Agendapp |
| Analogique | `analog` | - Reflet Analogique<br> - Reflet Analogique avec Seuils témoins<br> - Reflet Analogique avec Forçage |
| Chaudière | `boiler` | Reflet Chaudière |
| Bruleur | `burner` | Reflet Bruleur |
| Digital | `digital` | - Reflet Digital<br> - Reflet Digital avec Forçage |
| Courbe de chauffe | `heating-curve` | Reflet Courbe de chauffe |
| Tableau de consignes | `setpoints-table` | Reflet Tableau de consignes |
| PID | `pid` | Reflet PID |
| Fil Pilote | `pilot-wire` | Reflet Fil Pilote |
| Pompe | `pump` | Reflet Pompe |
| Etat | `state` | Reflet Etat |
| Texte | `text` | Reflet Texte |
| Vanne | `valve` | Reflet Vanne |
| Inconnu | `unknown` | Pour les reflet que Synapps ne connait pas encore. |

## Évènements spécifiques

### ⚡`onRequestDone`

L'évènement `onRequestDone` est déclenché lorsque l'acteur a terminé une requête vers le REDY pour obtenir ou rafraîchir le reflet.

L'évènement comporte un objet `context` avec les propriétés suivantes :
- `data`  : Le reflet obtenu du REDY, cet objet contient toutes les informations relative au reflet (nom, chemin, etc ...).
- `error` : Un message d'erreur si la requête a échoué, ou `null` si elle a réussi.

### ⚡`onDidReflectChange`

L'évènement `onDidReflectChange` est déclenché lorsque le reflet a changé.

L'évènement comporte un objet `context` avec les propriétés suivantes :
- `reflect` : Le nouveau reflet obtenu.

### ⚡`onDidCommand`

L'évènement `onDidCommand` est déclenché lorsqu'une commande a été envoyée au reflet.
- `data`  : Le modèle du reflet mis à jour.
- `error` : Un message d'erreur si la requête a échoué, ou `null` si elle a réussi.
