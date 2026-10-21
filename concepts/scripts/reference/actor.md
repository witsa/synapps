---
title: "Acteur"
parent: "Référence"
grand_parent: Scripts
nav_order: 3
redirect_from:
  - /concepts/actor/script-reference.html
---

{% include table_of_content.html %}

# Acteur

> 📖 Concept : [Acteur](../../actor/index.md)

Informations, méthodes et évènements communs à tous les acteurs, accessibles par script via
`this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur. Les
propriétés communes sont décrites par catégorie dans les pages [Aspect](../../actor/category-aspect.md),
[Texte](../../actor/category-text.md), [Disposition](../../actor/category-disposition.md), [Tailles](../../actor/category-size.md),
[Espaces](../../actor/category-space.md), [Bordures](../../actor/category-border.md) et [Effets](../../actor/category-effects.md) ;
celles propres à un type d'acteur, sur la page de ce [type d'acteur](../../actor-types/index.md).

{% include script_api/legend.md %}

# Informations
{: #informations }

{% include script_api/fields.md type="common" %}

# Méthodes
{: #methodes }

{% include script_api/methods.md type="common" %}

# Événements
{: #evenements }

{% include script_api/events.md type="common" %}

# Propriétés et additionnelles
{: #proprietes-et-additionnelles }

Les propriétés (`this.properties`) et les additionnelles (`this.additionals`) d'un acteur donnent
accès à chaque propriété ou additionnelle par son nom (`this.properties.width`), et offrent :

{% include script_api/methods.md object="properties" prefix="this.properties" %}

# Évènements des propriétés et additionnelles
{: #evenements-des-proprietes }

Scripts définis dans l'inspecteur sur une propriété ou une additionnelle donnée (`<nom>` est son
nom) : changement de valeur et transformations de [liaison](./binding.md).

{% include script_api/events.md type="common" list="property_events" %}
