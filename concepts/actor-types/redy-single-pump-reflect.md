---
title: "REDY | Reflet Pompe simple"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Reflet Pompe simple

L'acteur **Reflet Pompe simple** permet une visualisation détaillée d'une ressource pompe simple avec reflet.

## Fonctionnement

Cet acteur se connecte directement à la source de données de la pompe simple (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

Voici les différents états de la pompe simple :

| État          | Description                                     | État LED | Couleur LED |
| ------------- | ----------------------------------------------- | -------- | ----------- |
| **Arrêtée**   | La pompe est éteinte et ne fonctionne pas.      | Éteinte  | ▫️          |
| **En marche** | La pompe est allumée et fonctionne normalement. | Allumée  | 🟩          |
| **En défaut** | La pompe rencontre un problème.                 | Allumée  | 🟥          |

{% include redy_reflect_technical_common.md %}
