---
title: "Contexte d'évènement"
parent: "Référence"
grand_parent: Scripts
nav_order: 2
redirect_from:
  - /script-api/Event.BaseContext.html
  - /script-api/Event.BaseContextUtils.html
  - /script-api/Event.PropertyChangedContext.html
  - /script-api/Event.RequestDataContext.html
  - /script-api/synapps-ui_addon_components_events-manager.js.html
  - /script-api/synapps-ui_addon_tools_is-values-equal.js.html
---

{% include table_of_content.html %}

# Contexte d'évènement

> 📖 Concept : [Scripts](../index.md)

Objet `context` passé à tous les scripts (évènements, transformations de liaison). Chaque évènement peut y ajouter ses propres membres : ils sont décrits avec l'évènement.

{% include script_api/legend.md %}

# Informations
{: #informations }

{% include script_api/fields.md object="context" prefix="context" %}

# Méthodes
{: #methodes }

{% include script_api/methods.md object="context" prefix="context" %}

# Utilitaires
{: #utilitaires }

Fonctions accessibles par `context.utils`.

{% include script_api/methods.md object="context-utils" prefix="context.utils" %}
