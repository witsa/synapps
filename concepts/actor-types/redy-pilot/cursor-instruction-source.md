---
title: "Fournisseur d'instruction"
parent: "REDY Pilot"
api_type: redy/data-source/cursor-instruction
since:
  studio: 1.7.0
  runtime: 2.8.0
  redy_pilot: 1.0.0
---

{% include table_of_content.html %}

# Fournisseur d'instruction

Cet acteur permet de créer une source de curseur instructions pour le pilote REDY. Il consomme un curseur d'instruction, demande son exécution au pilote REDY suivant des éventuels paramètres, et fournit les résultats dans son champ de données `data`.

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

## Paramètres de l'instruction

Si le curseur d'instruction SQL utilise des paramètres, Studio propose de créer des additionnels pour les fournir.

# Informations
{: #informations }

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

{% include script_api/fields.md type=page.api_type %}

# Méthodes
{: #methodes }

{% include script_api/methods.md type=page.api_type %}

# Événements
{: #evenements }

Les évènements communs à tous les acteurs sont décrits avec l'[acteur de base]({{ site.baseurl }}/concepts/actor/).

{% include script_api/events.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}
