---
title: "Reflet Pompe double"
parent: "Chaufferie & ECS"
grand_parent: "REDY"
nav_order: 4
api_type: redy/technical/double-pump
since:
  studio: 1.6.0
  runtime: 2.8.0
  redy: 16.4.0
---

# Reflet Pompe double

L'acteur **Reflet Pompe double** permet une visualisation détaillée d'une ressource pompe double avec reflet.

{: .info }
>
> C'est la version avec reflet de l'acteur [Pompe double](../../technical/boiler/double-pump.md).

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Informations
{: #informations }

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

{% include script_api/fields.md type=page.api_type %}

# Méthodes
{: #methodes }

{% include script_api/methods.md type=page.api_type %}

# Événements
{: #evenements }

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/scripts/reference/actor.html).

{% include script_api/events.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}

# Fonctionnement

Cet acteur se connecte directement à la source de données de la pompe double (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

# Types de reflets compatibles

- Reflet pompe double
