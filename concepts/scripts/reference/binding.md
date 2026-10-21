---
title: "Liaison"
parent: "Référence"
grand_parent: Scripts
nav_order: 4
redirect_from:
  - /concepts/binding-reference.html
  - /script-api/Binding.BasicBinding.html
  - /script-api/Binding.InternalBinding.html
  - /script-api/Binding.Setup.Actor.html
  - /script-api/Binding.Setup.Relative.html
  - /script-api/Binding.Setup.Stage.html
  - /script-api/synapps-ui_addon_bindings_basic.js.html
  - /script-api/synapps-ui_addon_bindings_internal.js.html
---

{% include table_of_content.html %}

# Liaison

> 📖 Concept : [Liaisons](../../binding.md)

Une liaison est accessible par script dans le contexte des [scripts de transformation](./actor.md#evenements-des-proprietes)
(`context.binding`), ou depuis l'acteur cible avec `this.getBinding('properties.<nom>')`.

{% include script_api/legend.md %}

# Informations
{: #informations }

{% include script_api/fields.md object="binding" prefix="binding" %}

# Méthodes
{: #methodes }

{% include script_api/methods.md object="binding" prefix="binding" %}
