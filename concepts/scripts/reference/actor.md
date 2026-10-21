---
title: "Acteur"
parent: "Référence"
grand_parent: Scripts
nav_order: 3
redirect_from:
  - /concepts/actor/script-reference.html
  - /script-api/Accessory.BaseAccessory.html
  - /script-api/Actor.BaseActor.html
  - /script-api/Actor.BaseActorProperties.html
  - /script-api/Behavior.DataContextual.html
  - /script-api/Behavior.Destroyable.html
  - /script-api/Behavior.Jokerable.html
  - /script-api/Behavior.Parenthood.html
  - /script-api/Behavior.SourceOfInternalBinding.html
  - /script-api/Behavior.Stage.html
  - /script-api/Behavior.WithAdditionals.html
  - /script-api/Behavior.WithEvents.html
  - /script-api/Behavior.WithProperties.html
  - /script-api/REDY.Accessory.WosRelativeVariableAccessory.html
  - /script-api/REDY.Behavior.WosRelativeVariableAble.html
  - /script-api/Synapps.PrototypedBase.html
  - /script-api/synapps-ui-redy_addon_accessories_wos-relative-variable.js.html
  - /script-api/synapps-ui-redy_addon_behaviors_wos-relative-variable-able.js.html
  - /script-api/synapps-ui_addon_accessories_base.js.html
  - /script-api/synapps-ui_addon_bases_user-agent.js.html
  - /script-api/synapps-ui_addon_bases_user.js.html
  - /script-api/synapps-ui_addon_behaviors_data-contextual.js.html
  - /script-api/synapps-ui_addon_behaviors_destroyable.js.html
  - /script-api/synapps-ui_addon_behaviors_source-of-internal-binding.js.html
  - /script-api/synapps-ui_addon_behaviors_with-additionals.js.html
  - /script-api/synapps-ui_addon_behaviors_with-properties.js.html
  - /script-api/synapps-ui_addon_components_behaviors_jokerable.js.html
  - /script-api/synapps-ui_addon_components_behaviors_parenthood.js.html
  - /script-api/synapps-ui_addon_components_behaviors_stage.js.html
  - /script-api/synapps-ui_addon_components_behaviors_with-events.js.html
  - /script-api/synapps-ui_addon_prototyped_base.js.html
---

{% include table_of_content.html %}

# Acteur

> 📖 Concept : [Acteur](../../actor/index.md)

Informations, méthodes et évènements communs à tous les acteurs, accessibles par script via
`this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur. Les
propriétés communes sont décrites par catégorie dans les pages [Aspect](../../actor/category-aspect.md),
[Texte](../../actor/category-text.md), [Disposition](../../actor/category-disposition.md), [Tailles](../../actor/category-size.md),
[Espaces](../../actor/category-space.md), [Bordures](../../actor/category-border.md) et [Effets](../../actor/category-effects.md) ;
celles propres à un type d'acteur, sur la page de ce [type d'acteur](../../actor-types/index.md).

{% include script_api/legend.md %}

# Informations
{: #informations }

{% include script_api/fields.md type="common" %}

# Méthodes
{: #methodes }

{% include script_api/methods.md type="common" %}

# Événements
{: #evenements }

{% include script_api/events.md type="common" %}

# Propriétés et additionnelles
{: #proprietes-et-additionnelles }

Les propriétés (`this.properties`) et les additionnelles (`this.additionals`) d'un acteur donnent
accès à chaque propriété ou additionnelle par son nom (`this.properties.width`), et offrent :

{% include script_api/methods.md object="properties" prefix="this.properties" %}

# Évènements des propriétés et additionnelles
{: #evenements-des-proprietes }

Scripts définis dans l'inspecteur sur une propriété ou une additionnelle donnée (`<nom>` est son
nom) : changement de valeur et transformations de [liaison](./binding.md).

{% include script_api/events.md type="common" list="property_events" %}
