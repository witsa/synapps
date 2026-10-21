---
title: "Détails de reflet"
parent: "Reflets"
grand_parent: "REDY"
api_type: redy/reflect-details
nav_order: 2
---

# Détails de reflet

L'acteur *Détails de reflet* est un composant conçu pour afficher dynamiquement les informations détaillées et gérer les commandes pour n'importe quel type de reflet.

## Fonctionnement

Cet acteur s'adapte automatiquement au type de reflet que vous lui indiquez. Une fois configuré avec le chemin vers un reflet (par exemple, vers une chaudière ou une vanne) :

1.  Il **Affiche la vue détaillée appropriée** avec toutes les informations pertinentes et, le cas échéant, les commandes spécifiques à cet équipement.
2.  Il **gère l'envoi de commandes** si le reflet est commandable, le détail de reflet présente les commandes disponibles et permet à l'utilisateur de les exécuter directement depuis l'interface.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

Il existe deux types de configuration pour cet acteur :
- **Autonome** : L'acteur gère lui-même les requêtes vers le REDY lorsque la propriété **Autonome** `isAutonomous` est vraie afin obtenir et rafraîchir les données du reflet. Dans ce mode, il n'a pas besoin d'un acteur requêteur externe. La propriété **Requêteur** `requesterKey` est ignorée.
- **Non autonome** : L'acteur s'appuie sur un acteur requêteur de reflet lorsque la propriété **Autonome** `isAutonomous` est fausse afin d'effectuer les requêtes. Cela permet de centraliser les requêtes et d'optimiser les performances si plusieurs acteurs *Détails de reflet* ou d'autre acteur de reflet sont utilisés dans la même scène.

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

# Conseils et optimisations

**Centralisation des requêtes** : Si vous avez plusieurs acteurs "Détails de reflet" dans votre scène, il est recommandé de ne pas les paramétrer comme `autonome` et d'utiliser un **requêteur de reflet commun**.
Cette pratique permet de mutualiser les requête et d'optimiser les performances globales de votre scène. Cela permet également de synchroniser les détails de reflet entre eux.


# Reflets du REDY supportés par Synapps

Voici la liste des types de reflets REDY que Synapps est capable de reconnaître et d'afficher en détail.

Les champs de chaque type sont décrits dans le modèle [Reflet](../../data-models/redy/reflect.md).

| Reflet dans Synapps | type Synapps | Reflets dans REDY |
|---------------------|------| -------------------|
| [Agenda](../../data-models/redy/reflect.md#agenda) | `agenda` | - Reflet Agenda<br> - Reflet Agendapp |
| [Analogique](../../data-models/redy/reflect.md#analogique) | `analog` | - Reflet Analogique<br> - Reflet Analogique avec Seuils témoins<br> - Reflet Analogique avec Forçage |
| [Chaudière](../../data-models/redy/reflect.md#chaudière) | `boiler` | Reflet Chaudière |
| [Bruleur](../../data-models/redy/reflect.md#brûleur) | `burner` | Reflet Bruleur |
| [Digital](../../data-models/redy/reflect.md#digital) | `digital` | - Reflet Digital<br> - Reflet Digital avec Forçage |
| [Courbe de chauffe](../../data-models/redy/reflect.md#courbe-de-chauffe) | `heating-curve` | Reflet Courbe de chauffe |
| [Tableau de consignes](../../data-models/redy/reflect.md#tableau-de-consignes) | `setpoints-table` | Reflet Tableau de consignes |
| [PID](../../data-models/redy/reflect.md#pid) | `pid` | Reflet PID |
| [Fil Pilote](../../data-models/redy/reflect.md#fil-pilote) | `pilot-wire` | Reflet Fil Pilote |
| [Pompe](../../data-models/redy/reflect.md#pompe) | `pump` | Reflet Pompe |
| [Etat](../../data-models/redy/reflect.md#état) | `state` | Reflet Etat |
| [Texte](../../data-models/redy/reflect.md#texte) | `text` | Reflet Texte |
| [Vanne](../../data-models/redy/reflect.md#vanne) | `valve` | Reflet Vanne |
| [Inconnu](../../data-models/redy/reflect.md#inconnu) | `unknown` | Pour les reflet que Synapps ne connait pas encore. |
