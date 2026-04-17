---
title: "Reflet Vanne 2 voies"
parent: "Technique REDY"
grand_parent: "REDY"
---

{% include table_of_content.html %}

# Reflet Vanne 2 voies

Studio **1.6.0**
{: .label .label-green }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-green }

L'acteur **Reflet Vanne 2 voies** permet une visualisation détaillée d'une ressource vanne 2 voies avec reflet.

{: .info }
>
> C'est la version avec reflet de l'acteur [Vanne 2 voies](../../technical/valve-2-ports.md).

## Fonctionnement

Cet acteur se connecte directement à la source de données de la vanne 2 voies (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

La vanne 2 voies existe en deux types : **Vanne d'arrêt** et **Vanne de régulation**. C'est le type de reflet associé qui détermine le comportement de la vanne :

- Reflet Vanne 2 voies donnera une **Vanne d'arrêt**
- Reflect Digital donnera une **Vanne d'arrêt**
- Reflet Analogique donnera une **Vanne d'arrêt**

## Propriétés spécifiques

{% include redy_reflect_technical_common.md %}

### Types de reflets compatibles

- Reflet Vanne 2 voies
- Reflet digital
- Reflet analogique
