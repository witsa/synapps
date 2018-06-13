# Tutorial 4: la navigation

[Home](../../sitemap.md) > [Tutoriaux](../index.md) > [Tutorial](index.md)

Dans ce tutorial, nous allons détailler une fonction fondamentale de toute application: la **navigation** entre scènes.

Nous allons mettre en oeuvre 2 nouveaux acteurs

* **Bouton de navigation**: pour déclencher la navigation entre les scènes
* **Ecrans**: pour afficher une scène dans une zone de l'écran

## Description

L'objectif du tutorial est la construction d'une SynApp navigable avec **3 scènes**. Chaque scène naviguée pourra être accédée avec un **raccourci** ou favoris dans le navigateur. La dernière scène contiendra également une navigation scondaire.
La scène principale sera composée d'un **menu**, de la **scène centrale** et d'un **pied de page**

![Empilement](assets/description.png)

## Prerequis

Créer une nouvelle SynApp **tuto04** avec le _MAKER_. Modifier le _label_ de la première scène en **sceneMaster** et le _nom_ avec <code>scène principale**</code> puis déployer.

![Empilement](assets/sceneMaster.png)

## Construction de la **scène principale**

1. Dans la scène courante _sceneMaster_ **définissez** l'acteur principal avec un acteur _empilement_

    * Renommer le _Label_ avec <code>stackRoot</code>
    ![Empilement](assets/stackRoot.png)
    * Définir la propriété _Aspect > Police > Taille_ avec <code>50px</code>

    _Remarque:_ il est important de systématiquement **renommer** le _Label_ des objets créés: acteur, scène, etc, avec des noms explicites.

    Par exemple <code>stack1</code> par <code>stackRoot</code>, <code>scene1</code> par <code>sceneMaster</code>

    Cela rend la la SynApp plus **maintenable** notamment dans ce tutorial car des acteurs vont référencés les clés d'autres acteurs

2. **Ajouter** un acteur enfant de type _empilement_ qui contiendra le menu de navigation

    * renommer le _Label_ avec <code>stackMenu</code>
    * définir la propriété _Spécifique > Orientation_ à <code>Horizontale</code>
    * définir la propriété _Aspect > Police > Alignement texte_ à <code>Centre</code>
    * définir la propriété _Gabarit > Hauteure_ à <code>10%</code>

3. **Sélectionner** l'acteur _empilement_ <code>stackRoot</code> et **Ajouter** un acteur enfant de type _écran_ (dans la catégorie _Affichage_ de l'explorateur d'acteurs) qui contiendra la scène courante

    * renommer le _Label_ avec <code>screenMiddle</code>
    * réinitialiser la propriété _Gabarit > Hauteur_ à la valeur par défaut <code>[Vide]</code>
    * définir la propriété _Position > Align. vertical_ à <code>Etendre</code>

    _Remarque:_ ne pas préter attention au **message d'avertissement** sur la propriété _Spécifiques > Scène_. Elle sera définie ultérieurement
    ![Empilement](assets/warning.png)

4. **Sélectionner** l'acteur _empilement_ <code>stackRoot</code> et **Ajouter** un acteur enfant de type _empilement_ qui contiendra le pied de page

    * renommer le _Label_ avec <code>stackFooter</code>
    * définir la propriété _Aspect > Couleur de fond_ à un gris clair <code>#e0e0e0</code>
    * réinitialiser la propriété _Gabarit > Hauteur_ à la valeur par défaut <code>[Vide]</code>

5. **Ajouter** un acteur enfant de type _text_ qui contiendra le texte de pied de page

    * renommer le _Label_ avec <code>textFooter</code>
    * définir la propriété _Aspect > Couleur_ à un gris foncé <code>#555555</code>
    * définir la propriété _Spécifiques > Contenu_ avec le texte <code>Pied de page</code>
    * définir la propriété _Position > Align. vertical_ à <code>Centré</code>
    * définir la propriété _Position > Align. horizontal_ à <code>Centré</code>

    ![Empilement](assets/footer.png)

    L'arbre des acteurs doit être

    ![Empilement](assets/sceneMasterActors.png)

## Construction des 3 **scènes secondaires**

1. **Ajouter** une **nouvelle scène**

    * renommer le _Label_ en <code>sceneA</code>
    * définir la propriété _Nom_ avec le texte <code>Scène A</code>
    * définir la propriété _Dossier_ avec le texte <code>Scènes</code>

    ![Empilement](assets/sceneA.png)

    _Remarque:_ le dossier permet de **ranger** la scène dans la liste

    ![Empilement](assets/scenes.png)

2. **Ajouter** un acteur enfant de type _empilement_

    * définir la propriété _Aspect > Couleur_ en _blanc_ à <code>#ffffff</code>
    * définir la propriété _Aspect > Couleur de fond_ en _orange_ à <code>#ff8000</code>
    * lier cette même propriété dans un nouvel élément de librairie

    ![Empilement](assets/bindLibrary.png)

    et définir le nom de cet élément en <code>colorSceneA</code>
    ![Empilement](assets/bindLibrary2.png)

    * définir la propriété _Aspect > Police > Poids_ à <code>800</code>
    * définir la propriété _Aspect > Police > Alignement texte_ à <code>Centre</code>
    * définir la propriété _Aspect > Police > Taille_ à <code>100px</code>

3. **Ajouter** un acteur enfant de type _text_

    * définir la propriété _Spécifiques > Contenu_ avec le texte <code>Scène A</code>
    * définir la propriété _Position > Align. vertical_ à <code>Centré</code>
    ![Empilement](assets/previewA.png)

4. **Cloner** la scène <code>sceneA</code>

    ![Empilement](assets/clone.png)

    * renommer le _Label_ en <code>sceneB</code>
    * définir la propriété _Nom_ avec le texte <code>Scène B</code>

5. **Sélectionner** l'acteur _empilement_ <code>stack1</code>

    * supprimer la liaison de la propriété _Aspect > Couleur de fond_
    ![Empilement](assets/bindRemove.png)

    * définir la propriété _Aspect > Couleur de fond_ en _violet_ à <code>#9400d3</code>
    * lier cette même propriété dans un nouvel élément de librairie avec le nom <code>colorSceneB</code>

6. **Sélectionner** l'acteur _text_ <code>text2</code>

    * définir la propriété _Spécifiques > Contenu_ avec le texte <code>Scène B</code>

7. **Définir** la scène **C comme pour la scène B** (_étapes 4 à 6_) en utilisant la couleur bleu <code>#0000ff</code>

    ![Empilement](assets/scenes2.png)

## Intégration des 3 **scènes secondaires** dans la **scène principale**

1. **Sélectionner** la scène principale <code>sceneMaster</code>

2. **Sélectionner** l'acteur _ecran_ <code>screenMiddle</code>

    * définir la propriété _Spécifiques > Scène_ en sélectionnant la scène <code>sceneA</code>. La scène A est alors affichée dans l'écran principal
    ![Empilement](assets/preview.png)

4. **Sélectionner** l'acteur _empilement_ <code>stackMenu</code> et **Ajouter** un acteur enfant de type _navigation_ (dans la catégorie _Interactions_ de l'explorateur d'acteurs) qui va naviguer sur la scene A dans l'acteur écran de la scène

    * renommer le _Label_ avec <code>buttonNavSceneA</code>
    * lier la propriété _Aspect > Couleur de fond_ à l'élément de librairie couleur <code>colorSceneA</code>
    ![Empilement](assets/bindLibrary3.png)
    * définir la propriété _Position > Align. vertical_ en <code>Etendre</code>
    * définir la propriété _Position > Align. horizontal_ en <code>Etendre</code>
    * définir la propriété _Spécifiques > Contenu_ avec le texte <code>Scene A</code>
    * sélectionner la propriété _Spécifiques > Scène_ avec <code>Scene A</code>
    * sélectionner la propriété _Spécifiques > Acteur de visualisation_ avec <code>screenMiddle</code>
    ![Empilement](assets/buttonNavSceneA.png)

    _Remarque:_ c'est dans ces 2 dernières sélections que la navigation opère: une action sur le bouton <code>buttonNavSceneA</code> commandera l'affichage de la scene <code>sceneA</code> dans l'acteur <code>screenMiddle</code> de la scène principale

4. **Cloner** l'acteur _navigation_ <code>buttonNavSceneA</code>

    * renommer le _Label_ avec <code>buttonNavSceneB</code>
    * supprimer la liaison de la propriété _Aspect > Couleur de fond_
    * lier cette même propriété à l'élément de librairie couleur <code>colorSceneB</code>
    * définir la propriété _Spécifiques > Contenu_ avec le texte <code>Scene B</code>
    * sélectionner la propriété _Spécifiques > Scène_ avec <code>Scene B</code>

5. **Cloner** un nouvel acteur <code>buttonNavSceneC</code> **comme pour le bouton de navigation B** (_étape 4_) en oubliant pas de lier la couleur de fond à la librairie <code>colorSceneC</code>

6. **Déployer** et **exécuter** la SynApp et cliquer sur les 3 boutons pour commander la navigation

    ![Empilement](assets/execute.png)

    La navigation principale est désormais opérationnelle !

7. Toujours En mode exécution, **Cliquer** sur la scene B. **Copier l'url courante dans un nouvel onglet du navigateur**: la SynApp s'ouvre sur la **scene A** et pas sur la B ! Cela signifie qu'il n'est pas possible, pour l'instant, de définir un raccourci vers une scène particulière de la SynApp. 

    Dans une application, il est trés important de pouvoir définir des **accès rapide via des raccourcis** vers des scènes spécifiques

## Définition des **paramêtres de la scène** principale

1. **Sélectioner** la scène principale <code>sceneMaster</code> pour définir qu'elle est pilotée par des paramêtres. Ici par le numéro de scène scendaire

    * cliquer sur _Gestion des propriétés paramêtres_ dans l'inspecteur de scène
    ![Empilement](assets/sceneMaster2.png)

2. **Ajouter** une propriété de type **Texte**
    ![Empilement](assets/sceneProp.png)

    * définir _Label_ par <code>selectedScene</code>
    * définir _Nom de la propriété_ par <code>Scène sélectionnée</code>
    * cliquer sur _Terminer_
    ![Empilement](assets/sceneProp2.png)
    * Une nouvelle propriété _Scène sélectionnée_ apparait dans l'inspecteur de la scène
    ![Empilement](assets/sceneProp3.png)
    * définir _Scène sélectionnée_ par <code>sceneA</code>
    ![Empilement](assets/sceneProp4.png)

3. **Sélectionner** l'acteur _text_ <code>textFooter</code> pour afficher la valeur de la propriété de scène ci-dessus en pied de page

    * modifier la propriété _Spécifiques > Contenu_ avec le texte ![Empilement](assets/workaround.png)
    * créer la propriété proposée <code>currentScene</code>
    ![Empilement](assets/textFooterProp.png)
    * liéer en interne cette propriété
    ![Empilement](assets/textFooterProp2.png)
    * sélectionner l'objet _Scène principale_ et la propriété _Scène sélectionnée_ et **lier**
    ![Empilement](assets/bindInternal.png)

4. **Déployer** et **exécuter** la SynApp. L'**URL** de la SynApp contient désormais la propriété de scéne créée _selectedScene_
    ![Empilement](assets/execute2.png)
    <code>.../scene/sceneMaster?sceneProps=%7B%22selectedScene%22%3A%22sceneA%22%7D</code>

    * remplacer <code>sceneA</code> dans le chemin ci-dessus par <code>sceneB</code>
    <code>.../scene/sceneMaster?sceneProps=%7B%22selectedScene%22%3A%22sceneB%22%7D</code>
    * le pied de page de la scène affiche bien la valeur saisie
    ![Empilement](assets/execute3.png)

    Par contre, la SynApp **ne navigue pas sur la scene B** et reste sur la scene A car, comme nous avons lié le texte du pied de page à la propriété _Scène sélectionnée_ de la scène principale, nous devons également lier la propriété _scène_ de l'acteur écran

5. **Sélectionner** l'acteur _écran_ **screenMiddle** pour lier sa scène

    * Lier la propriété _Spécifique > Scène_ en interne vers l'objet _Scène principale_ et la propriété _Scène sélectionnée_
    ![Empilement](assets/bindInternal2.png)

6. **Déployer** et **exécuter** la SynApp

    * cliquer sur les 3 boutons pour commander la navigation et vérifier que l'**URL** ainsi que le **pied de page** suivent bien la scène sélectionnée
    ![Empilement](assets/execute4.png)

    * modifier directement l'URL avec un **autre clé de scene** et vérifier que la **navigation** et le **pied de page** suivent bien la scène définie
    ![Empilement](assets/execute4.png)

    * naviguer sur la **scène B** et **copier l'URL** dans un nouvel onglet du navigateur. La SynApp **s'ouvre sur la scène B**

    La navigation principale est désormais opérationnelle

## Construction de la **navigation secondaire** de la scène C

1. **Cloner** la scène <code>sceneC</code>

    * renommer le _Label_ en <code>sceneC_1</code>
    * définir la propriété _Nom_ avec le texte <code>Scène C 1</code>
    * définir la propriété _Dossier_ avec le texte <code>Scènes.Scène C</code>

    ![Empilement](assets/sceneC1.png)

2. **Sélectionner** l'acteur _text_ <code>text2</code>

    * modifier la propriété _Spécifiques > Contenu_ avec le texte <code>Scène C > 1</code>

3. **Sélectionner** l'acteur _empilement_ <code>stack1</code> et **ajouter** un acteur _navigation_

    * renommer le _Label_ en <code>buttonNavBack</code>
    * modifier la propriété _Spécifiques > Contenu_ avec le texte <code>Retour</code>
    * définir la propriété _Spécifiques > Scène_ avec la scène <code>Scène C</code>
    * définir la propriété _Position > Align. horizontal_ avec <code>Gauche</code>
    * déplacer l'acteur en première position de <code>stack1</code>
    ![Empilement](assets/actors.png)
    ![Empilement](assets/previewC1.png)

    _Remarque:_ la propriété _Spécifiques > Acteur de visualisation_ est laissée vide car nous voulons naviguer sur la zone courante.

4. **Cloner** 3 fois la scène <code>sceneC_1</code> en scène <code>sceneC_2</code>, <code>sceneC_3</code> et <code>sceneC_4</code> en renommant les noms de scène et textes (_étapes 1 et 2_)
    ![Empilement](assets/scenesC.png)

5. **Sélectionner** la scène _ <code>sceneC</code>

6. **Sélectionner** l'acteur _empilement_ <code>stack1</code> et **ajouter** un acteur _empilement_

    * modifier la propriété _Spécifiques > Orientation_ en  <code>Horizontal</code>
    * modifier la propriété _Position > Align. vertical_ en  <code>Etendre</code>
    * modifier la propriété _Gabarit > Hauteur_ à la valeur par défaut <code>[vide]</code>

7. **Ajouter** un acteur _navigation_

    * renommer le _Label_ en <code>buttonNavSceneC1</code>
    * modifier la propriété _Spécifiques > Contenu_ avec le texte <code>Scène C1</code>
    * définir la propriété _Position > Align. vertical_ avec <code>Centré</code>
    * définir la propriété _Position > Align. horizontal_ avec <code>Centré</code>
    * définir la propriété _Spécifiques > Scène_ avec la scène <code>Scène C 1</code>
    ![Empilement](assets/previewC.png)

8. **Cloner** l'acteur <code>buttonNavSceneC1</code>

    * renommer le _Label_ en <code>buttonNavSceneC2</code>
    * modifier la propriété _Spécifiques > Contenu_ avec le texte <code>Scène C2</code>
    * définir la propriété _Spécifiques > Scène_ avec la scène <code>Scène C 2</code>

9. **Cloner** l'acteur _empilement_ <code>stack3</code> contenant les 2 acteurs _navigation_ et procéder à la configuration précédente (_étape 8_) pour naviguer vers les scènes _scène C 3_ et _scène C 4_

    ![Empilement](assets/actors2.png)
    ![Empilement](assets/sceneC.png)

10. **Déployer** et **exécuter** la SynApp

    * naviguer sur la scène C puis dans les scènes C1, C2, C3 et C4 en cliquant sur retour pour retourner dans la scène C

## Que retenir

Vous avez mis en oeuvre la navigation de 2 manières:

* En passant par un **acteur ecran** dans lequel s'ouvre la scène sélectionnée
* En **directe** la scène sélectionnée remplace la scène courante

Vous avez défini des **propriétés de scènes** qui permettent de **piloter les scènes** et **définir des raccourcis** vers des scènes spécifiques. Ces propriétés sont **liables** par tous les acteurs constitutifs de cette scène

Enfin, vous avez ranger les scènes dans des **dossiers** pour les retrouver plus facilement !

## Conclusion

Le **tutorial 4** sur les acteurs _navigation_ est **terminé**. La maitrise de la navigation est extrémement importante pour construire des applications ambitieuses !

Vous pouvez remonter les **bugs** & **remarques** concernant ce tutorial, SynApps RUNTIME & MAKER sur [GitHub](https://github.com/witsa/synapps/issues)

[Tutoriel suivant sur les acteurs composites](../tuto05/index.md)