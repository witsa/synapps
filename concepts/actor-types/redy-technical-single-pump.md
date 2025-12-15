---
title: "REDY | Reflet Pompe simple"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Reflet Pompe simple

L'acteur **Reflet Pompe simple** permet une visualisation détaillée d'une ressource pompe simple avec reflet.

{: .info }
>
> C'est la version avec reflet de l'acteur [Pompe simple](./technical-single-pump.md).

## Fonctionnement

Cet acteur se connecte directement à la source de données de la pompe simple (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

## Propriétés spécifiques

{% include redy_reflect_technical_common.md %}

### Types de reflets compatibles

- Reflet pompe simple
- Reflet digital
