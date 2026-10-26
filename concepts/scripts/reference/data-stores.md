---
title: "Magasins de données"
parent: "Référence"
grand_parent: Scripts
nav_order: 12
---

{% include table_of_content.html %}

# Magasins de données

> 📖 Concept : [Magasin de donnée](../data-store.md)

Les magasins de données de la synapp, accessibles par `context.dataStores` dans tout script (et par `this.dataStores` depuis un acteur). Ils donnent accès au [magasin REDY](./data-store.md) : `context.dataStores.redy`.

{% include script_api/legend.md %}

# Informations
{: #informations }

{% include script_api/fields.md object="data-stores" prefix="context.dataStores" %}
