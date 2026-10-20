---
title: "Référence pour les scripts"
parent: Acteur
grand_parent: Concepts
nav_order: 8
---

{% include table_of_content.html %}

# Référence pour les scripts

Informations, méthodes et évènements communs à tous les acteurs, accessibles par script via
`this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur. Les
propriétés communes sont décrites par catégorie dans les pages [Aspect](./category-aspect.md),
[Texte](./category-text.md), [Disposition](./category-disposition.md), [Tailles](./category-size.md),
[Espaces](./category-space.md), [Bordures](./category-border.md) et [Effets](./category-effects.md) ;
celles propres à un type d'acteur, sur la page de ce [type d'acteur](../actor-types/index.md).

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

{% include script_api/methods.md object="properties" %}

# Évènements des propriétés et additionnelles
{: #evenements-des-proprietes }

Scripts définis dans l'inspecteur sur une propriété ou une additionnelle donnée (`<nom>` est son
nom) : changement de valeur et transformations de [liaison](../binding-reference.md).

{% include script_api/events.md type="common" list="property_events" %}
