---
api_type: technical/valve-2-ports
kind: property
name: type
---
Définit le type de vanne :

- Vanne d'arrêt (`shutoff`)
- Vanne de régulation (`control`)

En fonction du type sélectionné, les autres propriétés disponibles changent.

- Pour la Vanne d'arrêt, utilisez la propriété Statut pour contrôler l'état (ouverte, fermée, en mouvement, ...).
- Pour la Vanne de régulation, utilisez la propriété Valeur pour définir le pourcentage d'ouverture.
