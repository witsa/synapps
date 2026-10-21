---
title: "Référence pour les scripts"
parent: Liaisons
grand_parent: Concepts
nav_order: 1
---

{% include table_of_content.html %}

# Liaison : référence pour les scripts

> 📖 Concept : [Liaisons](./binding.md)

Une liaison est accessible par script dans le contexte des [scripts de transformation](./actor/script-reference.md#evenements-des-proprietes)
(`context.binding`), ou depuis l'acteur cible avec `this.getBinding('properties.<nom>')`.

{% include script_api/legend.md %}

# Informations
{: #informations }

{% include script_api/fields.md object="binding" %}
