---
title: "REDY | Reflet Brûleur"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Reflet Brûleur

L'acteur **Reflet Brûleur** permet une visualisation détaillée d'une ressource brûleur avec reflet.

{: .info }
>
> C'est la version avec reflet de l'acteur [Brûleur](./redy-technical-burner.md).

## Fonctionnement

Cet acteur se connecte directement à la source de données d'un brûleur (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

## Propriétés spécifiques

{% include redy_reflect_technical_common.md %}

### Types de reflets compatibles

- Reflet Brûleur
- Reflet digital
