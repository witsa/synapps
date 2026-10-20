---
title: "Fournisseur de variable"
parent: "REDY"
api_type: redy/data-source/wos-variable
---

{% include links_actor.md apiClass="REDY.Actor.WosVariableSource" %}

# Fournisseur de variable

Acteur qui permet de communiquer avec une *variable WOS* d'un REDY. Le fournisseur s'occupe de récupérer la variable déterminée par la propriété *Chemin* et va la placer dans le champ d'information *Donnée*. Il est possible d'indiquer plutôt un champ de la variable à placer dans la donnée de l'acteur.

Aussi, l'acteur permet de définir la manière avec laquelle la variable est récupérée et rafraîchie et d'activer ou pas l'écriture dans sa valeur pour l'enregistrer dans le REDY.

La donnée récupérée est disponible pour les liaisons ou par script.

L'acteur sert de fournisseur de base aux éventuels [fournisseurs de variable relative](./wos-relative-variable-source.md) ou liaisons de type [fournisseur de variable](../../binding.md#fournisseur-de-variable) qui pointeraient dessus.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés

{% include script_api/properties.md type=page.api_type %}

# Informations

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

{% include script_api/fields.md type=page.api_type %}

# Méthodes

{% include script_api/methods.md type=page.api_type %}

# Événements

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/actor/).

{% include script_api/events.md type=page.api_type %}

# Hérite de

{% include script_api/inherits.md type=page.api_type %}

# Usage

Il est possible de créer des fournisseurs dans vos scènes ou composites. Vous pouvez également les créer de manière globale dans la sous-section [Projet / Fournisseurs de variable](../../project/variable-source.md) pour en faire profiter toute votre synapp.


> ✔️ **CONSEIL**<br>
> Essayez de mutualiser les fournisseurs de variable dans vos scènes et composites. Rappelez-vous que des requêtes de données sont réalisées pour chaque fournisseur de variable. Ce qui est responsable d'un trafic de données qui pourrait être important pour l'équipement qui exécute votre synapp. Ceci est particulièrement sensible pour les équipements nomades comme les smartphones et tablettes.
