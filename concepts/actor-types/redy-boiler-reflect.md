---
title: "REDY | Reflet Chaudière"
parent: "Types d'acteur"
grand_parent: Concepts
---

{% include table_of_content.html %}

# Reflet Chaudière

L'acteur **Reflet Chaudière** permet une visualisation détaillée d'une ressource chaudière REDY avec reflet.

## Fonctionnement

Cet acteur se connecte directement à la source de données de la chaudière (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.
Si une ressource brûleur accompagnée d'un reflet est présent avec la chaudière, l'acteur intègre également son état dans l'affichage.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

Voici les différents états de la chaudière :

| État                   | Description                                         | État LED    | Couleur LED |
| ---------------------- | --------------------------------------------------- | ----------- | ----------- |
| **Arrêtée**            | La chaudière est éteinte et ne fonctionne pas.      | Éteinte     | ▫️          |
| **En marche**          | La chaudière est allumée et fonctionne normalement. | Allumée     | 🟩          |
| **Démarrage en cours** | La chaudière est en train de s'allumer.             | Clignotante | 🟩          |
| **Arrêt en cours**     | La chaudière est en train de s'éteindre.            | Clignotante | 🟩          |
| **En défaut**          | La chaudière rencontre un problème.                 | Clignotante | 🟥          |

La chaudière peut être associée à un brûleur, les [états du brûleur](./redy-burner-reflect.md) sont également pris en charge.

> ⚠️ **ATTENTION**<br>
> Afin que Synapps puisse détecter le brûleur dans le paramétrage, la ressource brûleur doit porter le label `RessBurner` dans le paramétrage et posséder un reflet.

{% include redy_reflect_technical_common.md %}
