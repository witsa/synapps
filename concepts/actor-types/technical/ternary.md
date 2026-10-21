---
title: "Ternaire"
parent: "Technique"
grand_parent: "Types d'acteur"
nav_order: 2
api_type: technical/ternary
since:
  studio: 1.6.0
  runtime: 2.8.0
  redy: 16.4.0
---

# Acteur Ternaire

L'acteur Ternaire permet d'afficher un des trois états distincts en fonction d'une valeur et d'un état de défaut :

1.  **État Vrai** : Lorsque la `value` est vraie.
2.  **État Faux** : Lorsque la `value` est fausse.
3.  **État de Défaut** : Lorsqu'un défaut est signalé via `isFault` (cet état a la priorité sur les autres).

Chaque état est entièrement personnalisable, permettant de configurer un texte, une LED ou une image et un comportement de clignotement spécifique.

La led est affichée si vous ne fournissez pas d'image personnalisée.

{: .pin }

> Par défaut, l'acteur Ternaire affiche une LED verte allumée pour l'état Vrai, une LED verte éteinte pour l'état Faux, et une LED rouge clignotante pour l'état de Défaut.

![Synapps](../../../synapps-studio-releases/notes/assets/1.6/ternary.gif)

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

Ces propriétés contrôlent l'état global de l'acteur.

{% include script_api/properties.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
