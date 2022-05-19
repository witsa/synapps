---
title: "Scripts"
parent: Concepts
has_children: true
---

# Scripts

Synapps Studio offre un environnement de développement complètement programmables.

Le langage utilisé est le `Javascript`. Une API est fournie pour manipuler et accéder en l'ensemble des objets de votre synapp.

Voir la [documentation des scripts]({{ site.baseurl }}/script-api/){:target="_blank"}

## Scripts dans les évènements

Synapps est un framework de développement évènementiel. C'est à dire que les acteurs et propriétés déclenches des évènements (`onClick`, `onPropertyChange`, etc.) qui permettent de lancer des scripts.
Le [cycle de vie](./actor-life-cycle.md) d'un acteur produit des évènement. Mais chaque acteur peut avoir également des évènements spécifiques.

## Scripts dans les inclusions

Il est possible d'inclure un fichier `JavaScript` grâce aux [inclusions](../project/includes.md).
