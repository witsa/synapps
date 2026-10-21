---
api_type: display/data-table
kind: property
name: columns
---
Cette propriété permet de définir les colonnes du tableau de données.
Le JSON est structuré sous la forme d'un tableau d'objets, chaque objet représentant une colonne du tableau de données.

Studio permet de configurer les colonnes via l'inspecteur.

Lorsque vous modifiez une colonne, la prévisualisation du tableau de données n'est pas mise à jour automatiquement. Il faut cliquer sur le bouton "Appliquer les modifications" pour mettre à jour le tableau de données avec les nouvelles définitions de colonnes.

### Champs de colonne

| Champ              | Propriété     | Description                                                                                           |
| ------------------ | ------------- | ----------------------------------------------------------------------------------------------------- |
| Clé                | `key`         | Clé unique de la colonne ; utilisée pour lier la cellule à la donnée si `fieldPath` n'est pas défini. |
| Nom                | `name`        | Nom affiché dans l'en-tête ; laisser vide pour ne pas afficher de nom.                                |
| Chemin du champ    | `fieldPath`   | Chemin d'accès dans l'objet de la ligne pour récupérer la valeur ; si vide, `key` est utilisé.        |
| Visible            | `isVisible`   | Booléen indiquant si la colonne est visible.                                                          |
| Type               | `type`        | Type de la colonne. Valeurs : `string`, `number`, `boolean`, `boolean-image`, `date-time`, `custom`.  |
| Style              | `style`       | Style d'acteur cellule à utiliser pour cette colonne (seuls les styles compatibles sont proposés).    |
| Style d'en-tête    | `headerStyle` | Style d'acteur cellule pour l'en-tête ; si vide, le style d'en-tête par défaut est utilisé.           |
| Largeur de colonne | `columnWidth` | Largeur de la colonne (`auto`, `max-content`, valeur fixe, etc.).                                     |

### Types de colonnes

| Type              | Description                                                                                     |
| ----------------- | ----------------------------------------------------------------------------------------------- |
| Texte `string`    | Affiche la valeur comme du texte.                                                               |
| Nombre `number`   | Affiche la valeur comme un nombre.                                                              |
| Booléen `boolean` | Affiche la valeur comme vrai/faux avec un texte.                                                |
| Booléen image     | Affiche la valeur comme vrai/faux avec une image et un texte.                                   |
| Date/heure        | Affiche la valeur comme une date ou une heure au format par défaut comme `23/12/2025 21:30:00`. |
| Personnalisé      | Utilise un composite comme contenu de la cellule.                                               |

Chaque type de colonne utilise un style de cellule. Des styles par défaut sont fournis pour chaque type :

| Type              | Style par défaut                             |
| ----------------- | -------------------------------------------- |
| Texte `string`    | _Texte_ `table-cell-string`                  |
| Nombre `number`   | _Nombre_ `table-cell-number`                 |
| Booléen `boolean` | _Booléen_ `table-cell-boolean`               |
| Booléen image     | _Booléen image_ `table-cell-boolean-image`   |
| Date/heure        | _Date/heure_ `table-cell-datetime`           |
| Personnalisé      | _Personnalisé_ `table-cell-custom`           |

{: .info }
> Il est possible de créer d'autres styles d'acteur Cellule de donnée pour les personnaliser. Il seront basés sur les styles par défaut pour les utiliser dans les colonnes de type correspondant.<br/>
> Voir la page [Cellule de tableau de données](./data-table-cell) pour plus de détails.
