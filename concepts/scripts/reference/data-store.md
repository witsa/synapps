---
title: "Magasin REDY"
parent: "Référence"
grand_parent: Scripts
nav_order: 12
redirect_from:
  - /script-api/REDY.Synapps.RedyStore.html
  - /script-api/synapps-ui-redy_addon_services_data-stores_redy.js.html
---

{% include table_of_content.html %}

# Magasin REDY

> 📖 Concept : [Magasin de donnée](../data-store.md)

Le magasin de donnée du REDY auquel la synapp est connectée, accessible par `context.dataStores.redy`. Il charge les variables WOS, les reflets, les évènements et les curseurs du REDY, et leur envoie les écritures et les commandes. Les objets qu'il renvoie sont décrits dans les [modèles de données]({{ site.baseurl }}/concepts/data-models/).

{% include script_api/legend.md %}

# Informations
{: #informations }

{% include script_api/fields.md object="data-store" prefix="context.dataStores.redy" %}

# Méthodes
{: #methodes }

{% include script_api/methods.md object="data-store" prefix="context.dataStores.redy" %}
