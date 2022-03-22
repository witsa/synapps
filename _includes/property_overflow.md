Les propriétés *Dépassement vertical* et *Dépassement horizontal* permettent de gérer le comportement de l'acteur vis à vis d'un dépassement éventuel de son contenu.

Si l'acteur dispose d'une taille figée *OU* est contraint par un autre élément (acteur parent par exemple), alors, les propriétés *Dépassement horizontal* et *Dépassement vertical* peuvent s'appliquer.

Il existe quatre options pour chacune de ces propriétés :
- **Caché**

Le contenu qui ne dispose pas de suffisamment de place pour s'afficher ne sera pas visible et ses éléments ne seront pas accessibles.

- **Visible**

Le contenu qui ne dispose pas de suffisamment de place est affiché en dehors de l'emplacement prévu pour l'acteur.

Attention, si un autre acteur chevauche ce dépassement, la partie qui dépasse sera cachée par cet acteur.

> Il faut noter que les deux propriétés doivent être `Visible` afin d'obtenir le comportement souhaité.

- **Défilement**

Permet d'ajouter une *scrollbar* à l'acteur qui donne le moyen d'acceder au contenu qui dépassent.

- **Automatique**

Affiche une *scrollbar* uniquement s'il existe un dépassement.

> ⚠️ **ATTENTION**<br>
> Les options `Visible` et `Caché` ne sont pas compatibles entres elles.
