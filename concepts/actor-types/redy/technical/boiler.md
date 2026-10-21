---
title: "Reflet Chaudière"
parent: "Chaufferie & ECS"
grand_parent: "REDY"
nav_order: 1
api_type: redy/technical/boiler
since:
  studio: 1.6.0
  runtime: 2.8.0
  redy: 16.4.0
---

# Reflet Chaudière

L'acteur **Reflet Chaudière** permet une visualisation détaillée d'une ressource chaudière REDY avec reflet.

{: .info }
>
> C'est la version avec reflet de l'acteur [Chaudière](../../technical/boiler/boiler.md).

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

Cet acteur se connecte directement à la source de données de la chaudière (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.
Si une ressource brûleur accompagnée d'un reflet est présent avec la chaudière, l'acteur intègre également son état dans l'affichage.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

La chaudière peut être associée à un brûleur, les [états du brûleur](../../technical/boiler/burner.md) sont également pris en charge.

{: .pin}
>
> Les états du brûleurs sont affichés uniquement si la chaudière poussède un ressource brûleur avec un reflet *Bruleur* activé.

{: .warning}
>
> Ne changez pas le label `RessBurner` du brûleur dans le paramétrage. Sinon, l'association entre la chaudière et le brûleur ne fonctionnera pas correctement.

# Types de reflets compatibles

- Reflet Chaudière
  - Optionnel: sous ressource avec un reflet Brûleur
