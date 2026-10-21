---
api_type: display/data-table-cell
kind: property
name: textOverflow
---
Par défaut, le texte est tronqué si la largeur de la cellule est insuffisante pour l'afficher en entier. Il est possible de configurer le comportement en cas de dépassement de texte.

- **Tronquer** `truncate`: le texte est coupé et des points de suspension sont ajoutés à la fin.
- **Retour à la ligne** `wrap`: le texte est affiché sur plusieurs lignes si nécessaire.
- **Retour à la ligne (Cassure)** `break`: le texte est affiché sur plusieurs lignes si nécessaire, en cassant les mots si besoin.
- **Sans retour à la ligne** `nowrap`: le texte est affiché en une seule ligne, même s'il dépasse la largeur de la cellule.
