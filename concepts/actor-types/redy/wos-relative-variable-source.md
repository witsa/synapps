---
title: "Fournisseur de variable relative"
parent: "REDY"
api_type: redy/data-source/wos-relative-variable
---

{% include links_actor.md apiClass="REDY.Actor.WosRelativeVariableSource" %}

# Fournisseur relatif de variable

Cet acteur fournisseur de donnnée permet de compléter des acteurs [fournisseur de variable](./wos-variable-source.md) ou [de ressource](./resource-source.md) pour communiquer avec une *variable WOS* enfant d'un REDY.

Il permet ainsi de récupérer une variable enfant ou même d'écrire une valeur d'une variable enfant en ne renseignant uniquement que le *sous-chemin* par rapport à une autre variable (définie dans un autre fournisseur).

La variable ou champ de variable qu'il récupère est stockée dans son information `Donnée`, comme pour les autres fournisseurs de donnée.

Il faut noter qu'il ne contient pas de paramètre de requête. En effet, c'est le fournisseur parent qui en est responsable.
D'ailleurs, ce n'est pas lui non plus qui réalise les requêtes mais bien son fournisseur parent.

La donnée récupérée est disponible pour les liaisons ou par script.

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

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/actor/).

{% include script_api/events.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}

# Usage

Il est possible de créer des fournisseurs dans vos scènes ou composites. Vous pouvez également les créer de manière globale dans la sous-section [Projet / Fournisseurs de variable](../../project/variable-source.md) pour en faire profiter toute votre synapp.


## Grouper des requêtes.

Utiliser les fournisseurs relatifs est une bonne manière de mutualiser les fournisseurs de variable dans vos scènes et composites. Si vous attachez plusieurs relatifs à un même fournisseur de variable, il récupérera en même temps toutes les variables désignées.

Par exemple vous pouvez grouper la requête des sous variables d'une ressource :

- **Fournisseur 1 :** *pour accéder à une ressource*
  - chemin : `easy.RESS.R00001`

- **Fournisseur relatif 1 :** *pour accéder à son état*
  - parent : **Fournisseur 1**
  - champ : *État*

  ▶️ Champ *État* de `easy.RESS.R00001`

- **Fournisseur relatif 2 :** *pour accéder à sa valeur brute*
  - parent : **Fournisseur relatif 1**
  - chemin relatif : `Output`
  - champ : *Valeur*

  ▶️ Champ *Valeur* de `easy.RESS.R00001.Output`


- **Fournisseur relatif 2 :** *pour accéder à son unité*
  - parent : **Fournisseur relatif 2**
  - chemin relatif : `Unit`
  - champ : *Valeur*

  ▶️ Champ *Valeur* de `easy.RESS.R00001.Unit`

Le *Fournisseur 1* réalise en une seule requête la récupération de toutes les variables désignées.

## Chemin dynamique
Avec les fournisseurs relatifs, il est possible de construire un chemin cible dont les segments sont dynamiques :

- **Fournisseur 1 :**
  - chemin : `easy.RESS`

- **Fournisseur relatif 1 :**
  - parent : **Fournisseur 1**
  - chemin relatif : <span style="color: green;">*le sous chemin que vous souhaitez, renseigné par liaison par exemple.*</span>

- **Fournisseur relatif 2 :**
  - parent : **Fournisseur relatif 1**
  - chemin relatif : `Output`
  - champ : *Valeur*
