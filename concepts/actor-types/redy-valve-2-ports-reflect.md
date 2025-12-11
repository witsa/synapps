---
title: "REDY | Reflet Vanne 2 voies"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Reflet Vanne 2 voies

L'acteur **Reflet Vanne 2 voies** permet une visualisation détaillée d'une ressource vanne 2 voies avec reflet.

## Fonctionnement

Cet acteur se connecte directement à la source de données de la vanne 2 voies (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

La vanne 2 voies existe en deux types : **Vanne d'arrêt** et **Vanne de régulation**.

### Type Vanne de régulation `control`

La vanne d'arrêt varie de **0% (fermée)** à **100% (ouverte)** en fonction de la valeur du reflet.
Si la ressource est en défaut, la poignée de la vanne est remplacée par une LED rouge clignotante.

### Type Vanne d'arrêt `shutoff`

| État               | Description                                                                                        |
| ------------------ | -------------------------------------------------------------------------------------------------- |
| **Fermée**         | La vanne est fermée et bloque le passage du fluide.                                                |
| **Ouverte**        | La vanne est entièrement ouverte et laisse passer le fluide.                                       |
| **Ouverture**      | La vanne est en train de s'ouvrir.                                                                 |
| **Fermeture**      | La vanne est en train de se fermer.                                                                |
| **Initialisation** | La vanne est en phase d'initialisation.                                                            |
| **En défaut**      | La vanne rencontre un problème la poignée de la vanne est remplacée par une LED rouge clignotante. |

{% include redy_reflect_technical_common.md %}
