---
title: "Reflet"
parent: "Modèles REDY"
grand_parent: "Modèles de données"
api_model: redy/ReflectBase
nav_order: 2
redirect_from:
  - /script-api/Synapps.Reflect.ReflectAgenda.html
  - /script-api/Synapps.Reflect.ReflectAnalog.html
  - /script-api/Synapps.Reflect.ReflectAnalogCommand.html
  - /script-api/Synapps.Reflect.ReflectBase.html
  - /script-api/Synapps.Reflect.ReflectBoiler.html
  - /script-api/Synapps.Reflect.ReflectBoilerCommand.html
  - /script-api/Synapps.Reflect.ReflectBurner.html
  - /script-api/Synapps.Reflect.ReflectDigital.html
  - /script-api/Synapps.Reflect.ReflectDigitalCommand.html
  - /script-api/Synapps.Reflect.ReflectState.html
  - /script-api/Synapps.Reflect.ReflectText.html
  - /script-api/Synapps.Reflect.ReflectTextCommand.html
  - /script-api/Synapps.Reflect.ReflectValve.html
  - /script-api/Synapps.Reflect.ReflectValveCommand.html
  - /script-api/synapps-ui_addon_services_data-stores_models_reflect-agenda.js.html
  - /script-api/synapps-ui_addon_services_data-stores_models_reflect-analog.js.html
  - /script-api/synapps-ui_addon_services_data-stores_models_reflect-base.js.html
  - /script-api/synapps-ui_addon_services_data-stores_models_reflect-boiler.js.html
  - /script-api/synapps-ui_addon_services_data-stores_models_reflect-burner.js.html
  - /script-api/synapps-ui_addon_services_data-stores_models_reflect-digital.js.html
  - /script-api/synapps-ui_addon_services_data-stores_models_reflect-state.js.html
  - /script-api/synapps-ui_addon_services_data-stores_models_reflect-text.js.html
  - /script-api/synapps-ui_addon_services_data-stores_models_reflect-valve.js.html
---

{% include table_of_content.html %}

# Reflet

Objet qui représente un *reflet* d'un REDY : l'image, dans la synapp, d'une ressource du REDY (une mesure, une consigne, un équipement…), avec son état, sa valeur et, s'il est commandable, la commande à lui envoyer. Chaque type de reflet a ses propres champs, en plus des champs communs.

On le trouve :

- dans l'information `reflect` des acteurs à reflet : [Détails de reflet]({{ site.baseurl }}/concepts/actor-types/redy/reflect-details.html), reflets techniques ;
- dans la donnée (`data`) d'un [fournisseur de reflet]({{ site.baseurl }}/concepts/actor-types/redy/reflect-source.html), utilisable par liaison (`data.value`…) ;
- dans les réponses du [magasin REDY]({{ site.baseurl }}/concepts/scripts/reference/data-store.html) (`getReflect()`, `searchReflects()`).

Les types de reflet que les acteurs savent afficher sont listés avec l'acteur [Détails de reflet]({{ site.baseurl }}/concepts/actor-types/redy/reflect-details.html#reflets-du-redy-supportés-par-synapps).

{% include script_api/legend.md %}

# Champs communs

Champs présents sur tous les reflets.

{% include script_api/model_fields.md model="redy/ReflectBase" %}

# Méthodes

{% include script_api/model_methods.md model="redy/ReflectBase" %}

# Commander un reflet

Un reflet est commandable quand son champ `allowCommand` est vrai. Sa commande se prépare dans son objet `command`, dont les champs (`command.valueCmd`…) dépendent du type de reflet, puis s'envoie avec la méthode `commandReflect()` du [magasin REDY]({{ site.baseurl }}/concepts/scripts/reference/data-store.html). `resetCommand()` remet l'objet de commande aux valeurs actuelles du reflet.

# Types de reflet

Le type REDY d'un reflet est donné par son champ `redyType`. Seuls les champs propres au type sont listés ci-dessous.

## Analogique

{{ site.data.script_api.models["redy/ReflectAnalog"].description }}

Types REDY : `analog`, `analog_thresholds` (avec seuils), `analog_Forced` (avec seuils et forçage).

{% include script_api/model_fields.md model="redy/ReflectAnalog" exclude="redy/ReflectBase" %}

## Digital

{{ site.data.script_api.models["redy/ReflectDigital"].description }}

Types REDY : `digital`, `digital_Forced` (forçable).

{% include script_api/model_fields.md model="redy/ReflectDigital" exclude="redy/ReflectBase" %}

## Texte

{{ site.data.script_api.models["redy/ReflectText"].description }}

Types REDY : `text`.

{% include script_api/model_fields.md model="redy/ReflectText" exclude="redy/ReflectBase" %}

## État

{{ site.data.script_api.models["redy/ReflectState"].description }}

Types REDY : `state`.

## Tableau de consignes

{{ site.data.script_api.models["redy/ReflectSetpointsTable"].description }}

Types REDY : `setpoint_list`.

{% include script_api/model_fields.md model="redy/ReflectSetpointsTable" exclude="redy/ReflectBase" %}

## Agenda

{{ site.data.script_api.models["redy/ReflectAgenda"].description }}

Types REDY : `agenda`, `agenda_App`.

{% include script_api/model_fields.md model="redy/ReflectAgenda" exclude="redy/ReflectBase" %}

## PID

{{ site.data.script_api.models["redy/ReflectPid"].description }}

Types REDY : `PID`, `PIDSVA`.

{% include script_api/model_fields.md model="redy/ReflectPid" exclude="redy/ReflectBase" %}

## Courbe de chauffe

{{ site.data.script_api.models["redy/ReflectHeatingCurve"].description }}

Types REDY : `HeatingCurve`.

{% include script_api/model_fields.md model="redy/ReflectHeatingCurve" exclude="redy/ReflectBase" %}

## Pompe

{{ site.data.script_api.models["redy/ReflectPump"].description }}

Types REDY : `HVACPump`.

{% include script_api/model_fields.md model="redy/ReflectPump" exclude="redy/ReflectBase" %}

## Vanne

{{ site.data.script_api.models["redy/ReflectValve"].description }}

Types REDY : `Valve`.

{% include script_api/model_fields.md model="redy/ReflectValve" exclude="redy/ReflectBase" %}

## Fil pilote

{{ site.data.script_api.models["redy/ReflectPilotWire"].description }}

Types REDY : `FilPilote`.

{% include script_api/model_fields.md model="redy/ReflectPilotWire" exclude="redy/ReflectBase" %}

## Brûleur

{{ site.data.script_api.models["redy/ReflectBurner"].description }}

Types REDY : `Burner`.

{% include script_api/model_fields.md model="redy/ReflectBurner" exclude="redy/ReflectBase" %}

## Chaudière

{{ site.data.script_api.models["redy/ReflectBoiler"].description }}

Types REDY : `Boiler`.

{% include script_api/model_fields.md model="redy/ReflectBoiler" exclude="redy/ReflectBase" %}

## Inconnu

{{ site.data.script_api.models["redy/ReflectUnknown"].description }}

Types REDY : tout type non reconnu.
