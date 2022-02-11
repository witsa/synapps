---
title: Depassement du contenu
section: ecran
propName: exceed
propPath: properties.exceed
scriptApiClass: Actor.Display.exceed
order: 2
---
La propriété 'Dépassement du contenu' permet de gérer l'affichage du contenu de l'acteur écran verticalement et horizontalement.

Si l'acteur écran dispose d'une taille figée OU contrainte par un autre élément (acteur parent par exemple), alors, les propriétés 'dépassement horizontal' et 'dépassement vertical' s'appliquent.

Il existe quatres options pour chaqu'une de ces deux propriétés :
- **Caché**

Le contenu de l'acteur écran qui ne dispose pas de suffisament de place pour s'afficher ne sera pas visible et ses éléments ne seront pas accessible.

- **Visible**

Le contenu de l'acteur écran qui ne dispose pas de suffisament de place est affiché en dehors de l'emplacement prévu pour l'acteur.

Attention, si un autre acteur chevauche ce dépassement, la partie qui dépasse sera caché par cet acteur.
Il est nécessaire de jouer avec les z-index dans ce cas si l'on souhaite afficher la partie qui dépasse.

Il est à noter que les deux propriétés 'dépassement horizontal' et 'dépassement vertical' doivent avoir la valeur `Visible` afin d'obtenir le comportement souhaité.

- **Défilement**

Permet d'ajouter une scrollbar à la scène afin de pourvoir acceder à ses éléments qui dépassent.

- **Automatique**

S'adapte en fonction de la taille de l'acteur écran.

**ATENTION**

Les propriétés `Visible` et `Caché` ne sont pas compatibles entres elles.

Exemple:

![SynApps]( {{ site.baseurl }}/assets/concepts/actor/display_screen/showHide.PNG)

Ne fonctionne pas !