---
title: "Évènement WOS"
parent: "Modèles REDY"
grand_parent: "Modèles de données"
api_model: redy/WosEvent
nav_order: 3
---

# Évènement WOS

Objet qui représente un *évènement WOS* d'un REDY (apparition, disparition d'un défaut…) : c'est ce qu'affiche le [Journal des variables]({{ site.baseurl }}/concepts/actor-types/redy/wos-event-log.html), et les éléments de la liste `events` que renvoie la méthode `loadWosEvents()` du [magasin REDY]({{ site.baseurl }}/concepts/scripts/reference/data-store.html).

{% include script_api/legend.md %}

# Champs

{% include script_api/model_fields.md model=page.api_model %}
