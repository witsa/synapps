---
title: "IFrame"
parent: "Affichage"
grand_parent: "Types d'acteur"
api_type: display/iframe
nav_order: 5
---

{% include links_actor.md apiClass="Actor.Display.Iframe" %}

# IFrame

L'acteur Iframe permet d'intégrer une page web dans votre scène.

{% include table_of_content.html %}

{% include script_api/legend.md %}

# Propriétés
{: #proprietes }

{% include script_api/properties.md type=page.api_type %}

# Informations
{: #informations }

Accessibles par script, via `this` dans un script de l'acteur ou `context.getActor('clé')` depuis un autre acteur.

{% include script_api/fields.md type=page.api_type %}

# Hérite de
{: #herite-de }

{% include script_api/inherits.md type=page.api_type %}

# Quelques exemples

## iframe vers REDY

<div class="code-example" markdown="1">

Voici un exemple d'iFrame qui montre une page du REDY.

![SynApps](../../../assets/concepts/actor/display_iframe/iframe01.png)

L'additionnelle *Chemin REDY* permet de définir le chemin vers la page, depuis la racine du REDY (ici, on affiche le tableau de bord).

</div>

```text
SYNAPPS-STUDIO-ACTOR|{"type":"display/iframe","key":"iframe1","properties":{"verticalAlignment":"expand"},"additionalDefs":{"redyPath":{"type":"text","label":"Chemin REDY"}},"additionals":{"redyPath":"/easy/dashboard"},"bindings":{"properties.url":{"sourceType":"relative","sourcePath":"self","path":"additionals.redyPath"}},"events":{"properties/url/binding/onReadTransform":["return  `${this.dataStores.redy.host.domain}/WSID${this.dataStores.redy.host.session.sid}${context.value}`;"]}}
```
