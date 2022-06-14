---
title: "Inclusions"
parent: "Projet"
grand_parent: Concepts
nav_order: 8
---

Les inclusions offrent la possibilité de charger des fichiers à l'ouverture d'une synapp.

{% include table_of_content.html %}

# Les inclusions à l'exécution

Il est possible d'intégrer des fichiers source dans une synapp. Ils seront charger dans l'ordre de définition, l'un après l'autre. Ensuite, la [scène principale](../scene.md#scène-de-démarrage) s'affiche.

Cela permet de charger des librairies `Javascript` ou `CSS` qui seront utilisées dans vos scènes.

Les fichiers inclus sont soient *distants* soit *locaux*. Les fichiers distants sont chargés depuis l'adresse fournie lors de leur définition. Les fichiers locaux font partie du paramétrage de la synapp.

# Gestion des inclusions

Vous pouvez gérer les inclusions dans la section *Projet/Inclusions*.

Pour l'instant, il n'y a pas de designer pour cette partie. Il faudra éditer un fichier JSON de configuration.

Il se compose de la liste des inclusions à charger. Chaque inclusion est définie par un objet JSON,

- pour un fichier JS distant :


```json
   {
    "url": "https://example.com/script.js",
    "description": "Base 1view",
    "type": "js",
    "isRemote": true
  }
```

- pour un fichier JS local :

```json
   {
    "fileName": "nom-du-fichier.js",
    "description": "Base 1view",
    "type": "js",
    "isRemote": false
  }
```

Dans ce cas, le fichier `nom-du-fichier.js` doit être dans le répertoire `includes` de la synapp.

Pour des fichiers CSS, il suffit d'indiquer `"css"` pour le champ `type`.

## Exemple d'inclusion de la librairie Leaflet

Voici un exemple de configuration qui charge la librairie API de cartographie [Leaflet](https://leafletjs.com/reference.html) au démarrage de la synapp :


```json
 [
  {
    "fileName": "https://unpkg.com/leaflet@1.8.0/dist/leaflet.js",
    "description": "ceci est un test",
    "type": "js",
    "isRemote": false
  },
  {
    "fileName": "https://unpkg.com/leaflet@1.8.0/dist/leaflet.css",
    "type": "css",
    "isRemote": false
  }
]
```
# Exemple d'inclusion dans 1view

Le code source qui gère les scènes d'exploitation dans le modèle de projet **1view** est un exemple d'inclusion de fichiers `JavaScript` :

```json

[
  {
    "fileName": "oneview-base-comp.js",
    "description": "Base 1view",
    "type": "js",
    "isRemote": false
  },
  {
    "fileName": "oneview-desktop-comp.js",
    "description": "1view pour desktop",
    "type": "js",
    "isRemote": false
  },
  {
    "fileName": "oneview-smartphone-comp.js",
    "description": "1view pour smartphone",
    "type": "js",
    "isRemote": false
  }
]

```

Dans le dossier `includes` du projet, vous trouverez les 3 fichiers inclus.
