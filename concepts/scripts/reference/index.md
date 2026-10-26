---
title: "Référence"
parent: Scripts
grand_parent: Concepts
has_children: true
nav_order: 1
redirect_from:
  - /script-api/Accessory.html
  - /script-api/Actor.DataSource.html
  - /script-api/Actor.DataSourceProperties.html
  - /script-api/Actor.Input.BaseFilter.html
  - /script-api/Actor.Input.BaseInput.html
  - /script-api/Actor.Input.BaseInputProperties.html
  - /script-api/Actor.Layout.BaseLayout.html
  - /script-api/Actor.Layout.BaseLayoutProperties.html
  - /script-api/Actor.ReflectDetailsBase.html
  - /script-api/Actor.ReflectDetailsBaseProperties.html
  - /script-api/Actor.Request.BaseRequest.html
  - /script-api/Actor.Request.BaseRequestList.html
  - /script-api/Actor.Request.BaseRequestListProperties.html
  - /script-api/Actor.Request.BaseRequestProperties.html
  - /script-api/Actor.Unknown.html
  - /script-api/Behavior.html
  - /script-api/Binding.html
  - /script-api/Event.html
  - /script-api/JSON.html
  - /script-api/REDY.Behavior.html
  - /script-api/REDY.Synapps.html
  - /script-api/REDY.html
  - /script-api/Synapps.Ajax.html
  - /script-api/Synapps.BaseDataStore.html
  - /script-api/Synapps.BaseSetupDataStore.html
  - /script-api/Synapps.Model.html
  - /script-api/Synapps.Reflect.html
  - /script-api/Synapps.Serializer.html
  - /script-api/Synapps.html
  - /script-api/global.html
  - /script-api/index.html
  - /script-api/list_class.html
  - /script-api/list_namespace.html
  - /script-api/synapps-ui_addon_components_actors_base-actor-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_base-actor.js.html
  - /script-api/synapps-ui_addon_components_actors_base-request-list-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_base-request-list.js.html
  - /script-api/synapps-ui_addon_components_actors_base-request-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_base-request.js.html
  - /script-api/synapps-ui_addon_components_actors_data-source-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_data-source.js.html
  - /script-api/synapps-ui_addon_components_actors_input_base-filter.js.html
  - /script-api/synapps-ui_addon_components_actors_input_base-input-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_input_base-input.js.html
  - /script-api/synapps-ui_addon_components_actors_layout_base-layout-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_layout_base-layout.js.html
  - /script-api/synapps-ui_addon_components_actors_reflects_reflect-details-base-prototype-setup.js.html
  - /script-api/synapps-ui_addon_components_actors_reflects_reflect-details-base.js.html
  - /script-api/synapps-ui_addon_components_actors_unknown.js.html
  - /script-api/synapps-ui_addon_services_ajax.js.html
  - /script-api/synapps-ui_addon_services_data-stores_base-setup.js.html
  - /script-api/synapps-ui_addon_services_data-stores_base.js.html
  - /script-api/synapps-ui_addon_services_data-stores_model.js.html
  - /script-api/synapps-ui_addon_services_data-stores_serializer.js.html
---

# Référence

Objets accessibles dans les scripts, générés depuis le code :

- [Contexte d'évènement](./context.md) : `context`, présent dans tous les scripts, et ses utilitaires `context.utils` ;
- [Acteur](./actor.md) : membres communs à tous les acteurs (`this`), propriétés et additionnelles, et leurs évènements ;
- [Liaison](./binding.md) : `context.binding` dans les scripts de transformation, `this.getBinding(...)` ;
- [Synapp](./synapp.md) : `context.synapp` ;
- [Scène](./scene.md) : `context.scene`, `context.rootScene` ;
- [Composite](./composite.md) : le composite qui contient l'acteur ;
- [Hôte](./host.md) : le REDY auquel la synapp est connectée (`context.dataStores.redy.host`) ;
- [Session](./session.md) : la session de l'utilisateur (`context.dataStores.redy.session`) ;
- [Utilisateur](./user.md) : l'utilisateur connecté (`context.dataStores.redy.session.user`) ;
- [Afficheur](./user-agent.md) : l'appareil qui affiche la synapp (`context.synapp.userAgent`) ;
- [Magasins de données](./data-stores.md) : `context.dataStores`, qui donne accès au magasin REDY ;
- [Magasin REDY](./data-store.md) : les données du REDY, chargées et écrites par script (`context.dataStores.redy`).

Les objets renvoyés par le magasin (variable WOS, reflet, évènements) sont décrits dans les [modèles de données](../../data-models/index.md).

Les membres propres à chaque type d'acteur sont décrits avec ce [type d'acteur](../../actor-types/index.md).
