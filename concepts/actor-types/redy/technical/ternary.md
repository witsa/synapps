---
title: "Reflet ternaire"
parent: "Technique"
grand_parent: "REDY"
nav_order: 1
api_type: redy/technical/ternary
since:
  studio: 1.6.0
  runtime: 2.8.0
  redy: 16.4.0
---

# Acteur Reflet Ternaire

L'acteur Reflet Ternaire permet d'afficher un des trois états distincts en fonction d'un reflet. Tous les reflet sont supportés mais le digital est privilégié.

{: .info }
>
> C'est la version avec reflet de l'acteur [Ternaire](../../technical/ternary.md).

1.  **État Vrai** : Lorsque la valeur est vraie
2.  **État Faux** : Lorsque la valeur est fausse
3.  **État de Défaut** : Lorsque le reflet est en défaut (cet état a la priorité sur les autres).

Nous retrouvons les mêmes possibilités de personnalisation que pour l'acteur Ternaire classique, avec la possibilité de configurer une LED ou une image et un comportement de clignotement spécifique pour chaque état. Seule la propriété texte n'est pas personnalisable car elle est directement issue du reflet.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

Ces propriétés contrôlent l'état global de l'acteur.

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
