---
title: "Reflet Chaudière"
parent: "Technique REDY"
grand_parent: "REDY"
---

{% include table_of_content.html %}

# Reflet Chaudière

Studio **1.6.0**
{: .label .label-green }
Runtime **2.8.0**
{: .label .label-green }
REDY **16.4.0**
{: .label .label-green }

L'acteur **Reflet Chaudière** permet une visualisation détaillée d'une ressource chaudière REDY avec reflet.

{: .info }
>
> C'est la version avec reflet de l'acteur [Chaudière](../../technical/boiler.md).

## Fonctionnement

Cet acteur se connecte directement à la source de données de la chaudière (via un `reflet` ). Il interprète les informations reçues pour afficher un état de fonctionnement.
Si une ressource brûleur accompagnée d'un reflet est présent avec la chaudière, l'acteur intègre également son état dans l'affichage.

La propriété **Détails de reflet au click** (`withDetails`) permet d’activer l’affichage d’une modale lors du clic sur un acteur. Cette modale présente un détail de reflet, offrant une visualisation complète des informations du reflet. Si le reflet est commandable, la modale permet également d’interagir avec celui-ci.

La chaudière peut être associée à un brûleur, les [états du brûleur](./burner.md) sont également pris en charge.

{: .pin}
>
> Les états du brûleurs sont affichés uniquement si la chaudière poussède un ressource brûleur avec un reflet *Bruleur* activé.

{: .warning}
>
> Ne changez pas le label `RessBurner` du brûleur dans le paramétrage. Sinon, l'association entre la chaudière et le brûleur ne fonctionnera pas correctement.

## Propriétés spécifiques

{% include redy_reflect_technical_common.md %}

### Types de reflets compatibles

- Reflet Chaudière
  - Optionnel: sous ressource avec un reflet Brûleur
