---
api_type: display/data-table-cell
kind: property
name: composite
---
Pour personnaliser réellement l'affichage, il faut créer un composite qui va définir comment afficher la donnée et ajouter un style d'acteur cellule de tableau de données basé sur _Personnalisé_ `table-cell-custom` qui utilise ce composite.

### Passage par le contexte de données

Le composite à créer reçoit les mêmes éléments de la cellule que dans l'évènement [`onDidCellRender`](./data-table#contexte-des-évènements) de l'acteur **Tableau de données**. Ils sont disponibles dans le [contexte de données](../../context.md) du composite. Ainsi, elle sont accessibles par script ou via des liaisons vers le contexte de données.

### Passage par les propriétés du composite

Il est également possible de commander des propriétés du composite en passant un objet dans l'évènement [`onCellContentTransform`](./data-table#oncellcontenttransform) de l'acteur **Tableau de données**.

```javascript
// onCellContentTransform

if (!context.isHeader && context.columnKey === "custom1") {
  // la clé de la colonne est "custom1"
  // Personnalisation de la cellule
  return {
      // Passage d'une propriété "color" au composite
      color: context.dataRow.status === "active" ? "green" : "red",
      // Passage d'une propriété "label" au composite
      label: context.dataRow.name,
  };
}
```

Dans cet exemple, on passe deux propriétés `color` et `label` au composite de la cellule. La couleur du composite sera changée en fonction de la valeur du champ `status` de la ligne de données, et la propriété scpécifique qui a comme clé `label` sera définie avec la valeur du champ `name` de la ligne de données.
