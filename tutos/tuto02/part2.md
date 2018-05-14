[Home](../../sitemap.md) > [Tutoriaux](../index.md) > [Tutorial](index.md)

# Tutorial 2: les liaisons **2/6** *[6 nov 17]*

## Construction et configuration des acteurs

La SynApp sera constituée d'une seule scène avec un acteur disposition de type *empilement*

*Remarque:* le premier acteur de toute scène est appelé l'**acteur principal** et est obligatoirement de type *disposition* car il conditionne la disposition des acteurs qu'il contient: les **acteurs enfants**

1. Dans la scéne courante *scene1*, définir l'acteur principal avec un *empilement* :cliquer sur [+] pour ajouter un acteur *Dispositions* > *Empilement*

2. Par défaut, le *label* de l'acteur est *stack1*. Cliquer sur le bouton d'édition du *label* dans l'*inspecteur* d'acteur

![Editer le Label](assets/editLabel.png)

 et le renommer avec un nom plus explicite: *stackRoot*

![Changer le label](assets/changeLabel.png)

*Remarque:* il est vivement conseillé de modifier systématiquement les *labels* afin de leurs donner un nom **explicite** et **définitif**. Les *labels* sont en effet utilisés dans différents sections de SynApps: *scripts*, *liaisons* et en cas de renommage, la SynApp pourrait ne plus fonctionner correctement

3. L'acteur *stackRoot* étant sélectionné, ajouter un premier acteur enfant de type *Affichage* > *Texte* et renommer le label avec *textTop*

3. Resélectionner l'acteur *stackRoot* et ajouter un deuxième acteur enfant de type *Charts* > *Jauge* et renommer le label avec *gaugeAnalogic*

4. Resélectionner l'acteur *stackRoot* et ajouter un troisième acteur enfant de type *Affichage* > *Texte* et renommer le label avec *textBottom*

5. Nous allons modifier maintenant l'alignement et la taille du texte des acteurs *textTop* et *textBottom*. Mais plutot que de modifier chacun des 2 acteurs, nous allons définir ces propriétés au niveau de l'acteur principal car ces propriétés sont hérités par les enfants.

*Remarque:* de façon général, il est préférrable de définir les propriétés communes le **plus haut possible dans la hiérarchie** des acteurs, ceci afin d'éviter de redéfinir plusieurs fois des valeurs identiques sur chacun des acteurs.

L'acteur *stackRoot* étant sélectionné, modifier les propriétés suivantes dans l'*inspecteur d'objets*:
  * *Aspect* > *Alignement texte*: **Centre**, le texte sera centré
  * *Aspect* > *Taille*: **100px**, la taille de la police sera de 100 pixels

Vous observez que les tailles et alignements des textes des acteurs *textTop* et *textBottom* changent !

6. Modifier également la bordure de l'acteur *stackRoot* avec les propriétés suivantes:
  * *Aspect* > *Style bordure*: **Solide**
  * *Aspect* > *Epaisseur bordure*: **10px**
  * *Aspect* > *Rayon bordure*: **50px**
  * *Aspect* > *Couleur bordure*: **#0000ff**

![Edition bordure](assets/editBordure.png)

7. Sélectionner l'acteur *textTop* et modifier les propriétés suivantes:
  * *Aspect* > *Couleur de fond*: **#0000ff**, idem *Couleur bordure* de *stackRoot*
  * *Aspect* > *Couleur*: **#ffffff**, blanc
  * *Spécifique* > *Contenu*:

Le texte affiché en haut sera composé du *nom* et de l'*unité* de la ressource avec ce format:
```
Nom [unité]
```
Il existe un moyen simple pour décrire cette composition de format en utilisant des **propriétés additionnelles**:

Cliquer sur le bouton d'édition de la propriété *Spécifique* > *Contenu*
![Edition bordure](assets/editContent.png)

Un fenêtre modale d'édition du contenu s'ouvre
![Edition bordure](assets/editContentModal.png)

Saisir:
![Code snapshot](assets/codeSnapshot1.png)

Les doubles crochets ouvrant et fermant permettent de définir une *propriété additionnelle*. Dans notre cas, deux *propriétés additionnelles* sont créées:
* **nom**: qui contiendra le nom de la ressource *variableAnalogiqueTuto*
* **unit**: qui contiendra l'unité de cette même ressource

Sauvegarder puis fermer la fenêtre, l'inspecteur d'acteur propose la création de ces deux propriétés
![Edition bordure](assets/editContentNewProps.png)

Créer les deux *propriétés additionnelles* en cliquant sur le [+] et en choisissant **text** comme type de propriété

![Edition bordure](assets/editContentNewProps2.png)

Vérifier le résultat sur le *contenu* dans la zone de prévisualisation en modifiant la valeur des deux *propriétés additionnelles* **nom** et **unit**
![Edition bordure](assets/editContentNewProps3.png)
![Edition bordure](assets/editContentPreview.png)

7. Sélectionner l'acteur *textBottom* et modifier la propriété *Spécifique* > *Contenu*. Procéder de la même façon que pour l'acteur *textTop* mais ici le contenu sera composé de la valeur et du max avec ce format:
![Code snapshot](assets/codeSnapshot2.png)

Cette fois ci, choisir **nombre** comme type pour les deux *propriétés additionnelles* **value** et **max** créées. Initialiser les propriétés avec les valeurs respectivent 75 et 100

La zone de prévisualisation finale doit ressembler à cela !
![Prévisualisation](assets/preview.png)

**Déployer la SynApp** pour ne pas perdre vos modifications

Suite du [tutorial](part3.md)