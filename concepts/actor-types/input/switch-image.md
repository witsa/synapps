---
title: "Images interrupteur"
parent: "Interrupteur"
grand_parent: "Intéraction"
api_type: input/switch-image
nav_order: 2
---

{% include links_actor.md apiClass="Actor.Input.SwitchImage" %}

# Images interrupteur

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/input_switch_image/sample01.gif)

Acteur d'interaction qui permet d'afficher un interrupteur à deux états en affichant alternativement des images.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Événements
{: #evenements }

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/scripts/reference/actor.html).

{% include script_api/events.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}

# Astuces

Cet acteur peut être très utile pour afficher un indicateur avec une image pour chaque état. Il suffit de bien choisir les deux images à afficher, désactiver l'acteur pour éviter qu'un clic de souris le fasse basculer.
