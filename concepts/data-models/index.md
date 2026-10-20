---
title: "Modèles de données"
parent: Concepts
has_children: true
nav_order: 6
---

# Modèles de données

Les modèles de données sont les objets fournis par les équipements, comme le REDY : une variable
WOS, un reflet... On les retrouve :

- dans la donnée des [fournisseurs]({{ site.baseurl }}/concepts/actor-types/) (`data`), par
  exemple une variable WOS pour un fournisseur de variable ;
- dans les [liaisons]({{ site.baseurl }}/concepts/binding.html), dont le chemin désigne un champ
  du modèle (`data.value`) ;
- dans les scripts, par la donnée d'un fournisseur ou par les magasins de données
  (`context.dataStores`).

Chaque page décrit les champs du modèle, générés depuis le code : libellé dans Studio quand il
existe, nom du champ, type et description.
