---
title: "REDY | Reflet Pompe double"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Reflet Pompe double

L'acteur **Reflet Pompe double** permet une visualisation détaillée d'une ressource pompe double avec reflet.

## Fonctionnement

Cet acteur se connecte directement à la source de données de la pompe double (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

Voici les différents états de la pompe double :

| État                  | Description                                           | État LED | Couleur LED |
| --------------------- | ----------------------------------------------------- | -------- | ----------- |
| **Arrêtée**           | Les deux pompes sont éteintes et ne fonctionnent pas. | Éteinte  | ▫️          |
| **Pompe 1 en marche** | La pompe 1 est allumée et fonctionne normalement.     | Allumée  | 🟩          |
| **Pompe 2 en marche** | La pompe 2 est allumée et fonctionne normalement.     | Allumée  | 🟩          |
| **Pompe 1 en défaut** | La pompe 1 rencontre un problème.                     | Allumée  | 🟥          |
| **Pompe 2 en défaut** | La pompe 2 rencontre un problème.                     | Allumée  | 🟥          |

{% include redy_reflect_technical_common.md %}
