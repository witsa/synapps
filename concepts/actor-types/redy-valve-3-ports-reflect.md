---
title: "REDY | Reflet Vanne 3 voies"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Reflet Vanne 3 voies

L'acteur **Reflet Vanne 3 voies** permet une visualisation détaillée d'une ressource vanne 3 voies avec reflet.

## Fonctionnement

Cet acteur se connecte directement à la source de données de la vanne 3 voies (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

La vanne 3 voies représente présente une poignée indiquant la position actuelle de la vanne, variant de **0%** à **100%** en fonction de la valeur du reflet.
Si la ressource est en défaut, la poignée de la vanne est remplacée par une LED rouge clignotante.

{% include redy_reflect_technical_common.md %}
