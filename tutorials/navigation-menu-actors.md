---
title: Utiliser les acteurs de menu de navigation
parent: Tutoriels
nav_order: 1
---

{% include table_of_content.html %}

La navigation est un élément clé de toute synapp. Elle permet de naviguer entre les différentes scènes et de visualiser leur contenu. Ce tutoriel vous guidera à travers la création d'une navigation fonctionnelle en utilisant les acteurs de menu de navigation.

## Vue d'ensemble

Synapps Studio propose trois acteurs principaux pour gérer la navigation :

- **Menu de navigation** : Conteneur principal qui gère l'état de la navigation
- **Groupe de navigation** : Groupe d'éléments de navigation (avec possibilité de repli)
- **Bouton de menu** : Bouton individuel pour naviguer vers une scène

Ces trois acteurs travaillent ensemble pour créer une expérience de navigation cohérente.

## Étape 1 — Ajouter les acteurs de navigation

### 1.1 Créer un Menu de navigation

Commencez par ajouter un acteur **Menu de navigation** à votre scène. Cet acteur sera le conteneur principal qui gère l'état de la navigation globale.

> Le **Menu de navigation** contiendra tous les groupes de navigation et boutons de menu.

1. Ouvrir la scène de votre synapp
2. Ajouter un acteur `layout/nav-menu`
3. Placer cet acteur à l'endroit désiré (généralement à gauche de votre interface)

### 1.2 Ajouter des Groupes de navigation

Une fois le Menu créé, vous pouvez ajouter des **Groupes de navigation** en tant qu'acteurs enfants.

Un groupe de navigation fonctionne comme un conteneur qui peut se replier ou se déplier (mode accordéon).

1. Ajouter un acteur `layout/nav-group` **à l'intérieur** du Menu de navigation
2. Remplir la propriété **Titre du groupe** avec le nom de votre groupe (ex. "Accueil", "Administration", "Rapports")
3. Vous pouvez ajouter plusieurs groupes si nécessaire

### 1.3 Ajouter des Boutons de menu

Enfin, ajoutez des **Boutons de menu** à l'intérieur de chaque groupe de navigation ou dans l'acteur menu de navigation directement.

1. Ajouter un acteur**Bouton de menu**
2. Remplir la propriété **Contenu** avec le nom du bouton (ex. "Dashboard", "Utilisateurs")
3. Configurer la propriété **Scène** pour indiquer la scène à afficher lors du clic. Cette scène sera renseignée à l'acteur **menu de navigation**.

> Si vous souhaitez ajouter un bouton de menu directement dans le Menu sans passer par un groupe, c'est possible. Cependant, les groupes permettent une meilleure organisation, surtout pour les menus volumineux.

**Résultat attendu :** Vous devriez avoir une structure similaire à celle-ci :

```
├── Menu de navigation (gère selectedScene)
│   └── Bouton "Acceuil"
├────── Groupe "Utilisateur"
│   ├────── Bouton "Dashboard"
│   ├────── Bouton "Profil"
│   └────── Bouton "Paramètres"
└────── Groupe "Données"
    ├────── Bouton "Chauffage"
    └────── Bouton "CTA"
```

## Étape 2 — Définir les styles actif et inactif

Chaque bouton de menu peut avoir deux styles visuels : **actif** et **inactif**. Le style actif est appliqué lorsque le bouton correspond à la scène actuellement affichée ou au survol.

### 2.1 Configurer les styles du Menu

Le **Menu de navigation** possède deux propriétés de style qui s'appliquent à tous les boutons enfants :

1. Sélectionner le **Menu de navigation**
2. Dans le panneau des propriétés, trouver :
   - **Style du bouton actif** : Le style appliqué quand le bouton affiche la scène actuellement sélectionnée ou est survolé
   - **Style du bouton inactif** : Le style appliqué quand le bouton n'affiche pas la scène actuellement sélectionnée

Ces styles peuvent être personnalisés en ajoutant des styles pour l'acteur **Bouton de menu**

{: .tip }

> Choisissez des styles contrastés pour bien distinguer le bouton actif. Par exemple :
>
> - Style actif : Fond coloré + texte blanc/clair
> - Style inactif : Fond transparent + texte foncé

### 2.2 Personnaliser le Groupe

Vous pouvez également personnaliser les couleurs de l'entête du **Groupe de navigation**.
L'acteur **Menu de navigation** porte les propriétés couleur de fond et couleur du texte qui sont appliquées à toutes les entêtes de groupe.

## Étape 3 — Comprendre la propriété selectedScene

La propriété `selectedScene` est au cœur du mécanisme de navigation. Elle détermine **quel bouton doit afficher le style actif**.

### 3.1 Où se trouve selectedScene ?

`selectedScene` existe au niveau des propriétés du **Menu de navigation**.

Cette propriété contient la **clé** (identifiant) de la scène actuellement affichée.

### 3.2 Fonctionnement

Lorsqu'un utilisateur clique sur un **Bouton de menu** :

1. Le bouton définit la propriété `selectedScene` du Menu avec la clé de sa scène
2. Le Menu notifie tous ses enfants (boutons et groupes) de ce changement
3. Chaque **Bouton de menu** compare sa propriété **Scène** avec la valeur de `selectedScene`
4. Si elles correspondent : le bouton affiche le **style actif**
5. Si elles ne correspondent pas : le bouton affiche le **style inactif**

## Étape 4 — Lier selectedScene avec un acteur écran

Si votre synapp utilise un **acteur Écran** pour afficher le contenu des scènes, vous devez synchroniser le Menu de navigation avec cet acteur. L'acteur Écran doit afficher la **même scène** que celle sélectionnée dans le Menu.

### 4.1 Ajouter un acteur Écran

1. Dans la scène qui contient le Menu de navigation
2. Ajouter un acteur **Écran** à côté du Menu.
3. Cet Écran affichera le contenu de la scène sélectionnée

### 4.2 Créer une liaison

Pour que l'Écran affiche toujours la scène sélectionnée du Menu, créez une **liaison** :

1. Sélectionner l'acteur **Écran**
2. Dans le panneau des propriétés, trouver la propriété **Scène** (selectedScene)
3. Créer une liaison de cette propriété vers la propriété **Scène sélectionnée** du Menu de navigation

{: .info }

> Si l''acteur écran est contrôlé par d'autres éléments (ex. scripts), vous pouvez créer la liaison dans l'autre sens : du Menu vers l'Écran.

Après avoir créé cette liaison, l'Écran affichera **automatiquement** la scène sélectionnée dans le Menu. Quand vous cliquez sur un bouton du Menu, l'Écran se met à jour en temps réel !

### 4.3 Initialiser la scène sélectionnée

Par défaut, aucune scène n'est sélectionnée au démarrage. Pour afficher une scène par défaut :

1. Sélectionner le **Menu de navigation**
2. Dans le panneau des propriétés, définir la propriété **Scène sélectionnée** avec la scène désirée.
3. Vous pouvez utiliser une liaison pour la définir dynamiquement si nécessaire

{: .info }

> Si la liaison est créée dans l'autre sens (de Menu vers Écran), assurez-vous que la scène sélectionnée est définie sur l'acteur écran.

## Exemple de scène complète

Voici une scène complète avec un Menu de navigation fonctionnel :

> {% raw %}
>
> ```text
> SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene_navigation","name":"Scène de navigation"},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"layout/nav-menu","key":"nav-menu1","properties":{"width":"20vmin","fontSize":"2vmin"},"children":[{"type":"input/menu-button","key":"menu-button1","properties":{"content":"Scène 1","sceneKey":"scene1","icon":"aaabattery"}},{"type":"input/menu-button","key":"menu-button2","properties":{"content":"Scène 2","sceneKey":"scene2","icon":"adobe"}},{"type":"layout/nav-group","key":"nav-group1","children":[{"type":"input/menu-button","key":"menu-button3","properties":{"content":"Scène 3","sceneKey":"scene5","icon":"alarm"}},{"type":"input/menu-button","key":"menu-button4","properties":{"content":"Scène 4","sceneKey":"scene6","icon":"alarmalt"}}],"properties":{"icon":"ajax","content":"Groupe 1"}},{"type":"layout/nav-group","key":"nav-group2","children":[{"type":"input/menu-button","key":"menu-button5","properties":{"content":"Scène 5","sceneKey":"scene7","icon":"aaabattery"}}],"properties":{"content":"Groupe 2","icon":"acsource"}}],"bindings":{"properties.selectedScene":{"canWrite":true,"source":"actor#screen1@properties.sceneKey"}}},{"type":"display/screen","key":"screen1","properties":{"horizontalAlignment":"expand","backgroundColor":"#F7EE7F","sceneKey":""}}],"properties":{"orientation":"horizontal"}}}
> ```
>
> {% endraw %}

---

Voir aussi :

- [Bouton de Menu](../concepts/actor-types/input/menu-button.md)
- [Groupe de navigation](../concepts/actor-types/layout/layout-nav-group.md)
- [Menu de navigation](../concepts/actor-types/layout/layout-nav-menu.md)
- [Acteur Écran](../concepts/actor-types/display/screen.md)
- [Navigation](../concepts/navigation.md)
