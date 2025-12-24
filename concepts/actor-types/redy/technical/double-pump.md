---
title: "Reflet Pompe double"
parent: "Technique"
grand_parent: "REDY"
---

{% include table_of_content.html %}

# Reflet Pompe double

Studio **1.6.0-beta**
{: .label .label-yellow }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-yellow }

L'acteur **Reflet Pompe double** permet une visualisation détaillée d'une ressource pompe double avec reflet.

{: .info }
>
> C'est la version avec reflet de l'acteur [Pompe double](../../technical/double-pump.md).

## Fonctionnement

Cet acteur se connecte directement à la source de données de la pompe double (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

## Propriétés spécifiques

{% include redy_reflect_technical_common.md %}

### Types de reflets compatibles

- Reflet pompe double
