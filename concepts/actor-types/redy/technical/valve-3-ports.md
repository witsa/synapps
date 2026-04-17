---
title: "Reflet Vanne 3 voies"
parent: "Technique REDY"
grand_parent: "REDY"
---

{% include table_of_content.html %}

# Reflet Vanne 3 voies

Studio **1.6.0**
{: .label .label-green }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-green }

L'acteur **Reflet Vanne 3 voies** permet une visualisation détaillée d'une ressource vanne 3 voies avec reflet.

{: .info }
>
> C'est la version avec reflet de l'acteur [Vanne 3 voies](../../technical/valve-3-ports.md).

## Fonctionnement

Cet acteur se connecte directement à la source de données de la vanne 3 voies (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

## Propriétés spécifiques

{% include redy_reflect_technical_common.md %}

### Types de reflets compatibles

- Reflet Vanne 3 voies
- Reflet analogique
- Reflet digital
