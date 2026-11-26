---
title: "Journal des reflets"
parent: "Reflets"
grand_parent: "REDY"
api_type: redy/reflect-event-log
nav_order: 3
---

# Journal des reflets

L'acteur *Journal des reflets* affiche, page par page, les évènements des reflets du REDY, filtrés selon ses propriétés (période, reflet, site, équipement, zone, ensemble, groupes, texte…).

Le _Filtre site_ n'affiche que les évènements des reflets d'un site du REDY, choisi dans la liste des sites comme sur le [Journal des variables](./wos-event-log.md). Vide, le journal montre tous les sites. Par script, la propriété `site` prend le chemin du site, et un chemin qui ne correspond à aucun site n'affiche aucun évènement. Pour laisser l'utilisateur choisir le site, liez cette propriété à l'information `value` d'un [Filtre de site](./filter/site-filter.md) en sélection simple.

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
