[Accueil](../../readme.md) / [Tutoriaux](../index.md)

# Tutorial 5: les acteurs **composites** - **<span style='color:orange'>Avancé</span>**

Dans ce tutorial, nous allons mettre un oeuvre l'acteur **composite** qui permet de construire de **nouveaux acteurs** à partir d'acteurs éxistants. Ces derniers peuvent être soit des acteurs:

* **Natifs**: disponibles dans toute SynApp
* **Composites**: construits avec le MAKER, ils correspondent à un usage avancé et nécessitent une bonne compréhension du fonctionnement de SynApps

Quelque soit la nature de l'acteur, son **usage est identique**, la distinction permet donc uniquement de les différencier dans leurs mécanismes de fabrication

Le composite est un élément **fondamental** de toute SynApp, car il favorise:

* **Réutisabilité**: au sein d'une même SynApp et vers d'autres SynApp et utilisateurs via des mécanismes d'import/export

* **Maintenabilité**: la modification d'un acteur composite est propagée automatiquement à l'ensemble des scènes qui l'utilise

* **Modularité**: construction de scènes complexes par compositions d'acteurs simples et imbriqués

Ils peuvent être classés dans deux grandes catégories:

* **Standard**: ils ont une fonction de représentation indépendante d'une source de donnée. Par exemple: une jauge

* **Métiers**: ils ont besoin d'une source de données pour fonctionner ou ils utilisent en interne une ressource du REDY. Par exemple: l'acteur journal

![Empilement](assets/nature.png)
_Classement des acteurs par nature et catégorie_

## Description

L'objectif du tutorial est la construction d'acteurs composites permettant de visualiser une ressource de type climatiseur

## Prerequis

* Le paramétrage [SynApps_Tutorials.BRY](../config/SynApps_Tutorials.BRY) installé sur le REDY. Il contient trois ressources préconfigurées nécessaires dans le dossier ```Tutorial5```:
    1. Deux ressource **Régulation ventilo-convecteur 2T** ```VTCAtlanticEst``` et ```VTCAtlanticWest```
    2. Une ressource  **Compteur/Décompteur** ```Simulateur de changement temp. ambiante```

* Créer une nouvelle SynApp **tuto05** avec le _MAKER_. Modifier le _label_ de la première scène en ```sceneClims``` et le _nom_ avec ```scène climatiseurs``` puis déployer.

## Construction de la **scène climatiseurs**

1. Dans la scène courante ```sceneClims``` définissez l'acteur principal avec un acteur **toile**

2. **Ajouter** un acteur enfant de type **image** et définir le fond de plan avec l'image ci-dessous
    * Click droit sur l'image ci-dessous et _Enregistrer sous_ dans un dossier local
    ![Empilement](assets/backgroundPlan.png)

    * Ouvrir le dossier local contenant l'image
    * Glisser/déplacer l'image dans la zone **hachurée** de la propriété  _Spécifiques > Image_ 
    * Modifier la propriété _Gabarit > Hauteur_ à la valeur par défaut
    * Modifier également la propriété _Gabarit > Largeur_ à la valeur par défaut

## Construction de l'ossature du **composite**

1. **Sélectionner** l'onglet composites et **créer** un nouvel acteur composite

    ![Empilement](assets/composites.png)

    * modifier le _label_ du composite en ```compositeClim``` et le _nom_ avec ```Climatiseur```
    * modifier la _description_ du composite en ```Acteur de visualisation et de contrôle d'un climatiseur```
    ![Empilement](assets/compositeClim_inspector.png)
    * Récupérer l'image ci-dessous

        ![Empilement](assets/clim.jpg)

    * Glisser/déplacer l'image dans la zone **hachurée** de la propriété  _Logo_

        ![Empilement](assets/logo.png)

        _Remarques:_ le logo permet d'identifier visuellement le composite dans l'_explorateur d'acteurs_. Il est également possible de faire une copie d'écran du composite avec l'icone **appareil photo** ci-dessus: à tester mais le résultat sera toujours meilleur avec une image adaptée

    * définir la propriété _Aspect > Police > Taille_ à ```50px```

    _Important:_ les propriétés définies **directement** sur le composite sont des **valeurs par défaut** qui seront **initialisées** lors de l'ajout du composite dans la scène.
    Elles sont alors modifiables ce qui permet la personnalisation du composite.
    Ici, nous définissons la police par défaut à ```50px``` directement sur le composite. Cette taille sera modifiable lors de l'ajout du composite dans la scène.
    Cet aspect est extrémement important: un composite peut être considéré comme une **boite noir** avec des **propriétés publiques personnalisables**. Editer le composite revient à ouvrir la boite et définir son comportement. Nous reviendrons sur cet aspect ultérieurement dans le tutorial

2. **Définissez** l'acteur principal avec un acteur _Empilement_

    * Renommer le _Label_ avec ```stackClim```
    * définir la propriété _Aspect > Couleur_ à un bleu clair ```#45aadb```

3. **Ajouter** un acteur enfant de type _html_ qui contiendra la température mesurée courante

    * renommer le _Label_ avec ```htmlTempCurrent```
    * définir la propriété _Spécifiques > Contenu_ avec le texte
    ```html
    <span style="white-space: nowrap;"><i class="icon-temperature-thermometer"></i>{% raw %}{{tempCurrent}}{% endraw %}°C</span>
    ```
    _Remarques:_
    * l'acteur _html_ est identique à l'acteur _text_ mais est adapté au contenu HTML
    * _icon-temperature-thermometer_ permet d'utiliser une libraire d'icones embarquée dans SynApps

    * créer la propriété proposée ```tempCurrent``` de type **texte**
    ![Empilement](assets/tempCurrent.png)
    * modifier les informations de la propriété additionnelle ```tempCurrent``` dans l'onglet _Additionnelles > Gestion des propriétés additionnelles_
    ![Empilement](assets/addProps.png)
    * modifier _Nom de la propriété_ avec ```Température courante``` et _Description_ avec ```Température mesurée par le climatiseur```
    ![Empilement](assets/editProps.png)
    * définir la propriété _Spécifiques > Température courante_ avec la valeur ```21```
    ![Empilement](assets/previewTempCurrent.png)
    * définir la propriété _Aspect > Police > Alignement texte_ à ```Centre```

4. **Sélectionner** l'acteur ```stackClim``` et **ajouter** un acteur enfant de type _boite à vue_ qui adaptera le visuel du climatiseur à la taille de l'écran

    * renommer le _Label_ avec ```viewBoxClim```
    * définir la propriété _Position > Align. vertical_ à ```Etendre```
    * définir la propriété _Position > Align. horizontal_ à ```Etendre```
    * réinitialiser la propriété _Gabarit > Hauteur_ à ```[vide]```

5. **Ajouter** un acteur enfant de type _toile_ qui contiendra les différents acteurs du visuel

    * renommer le _Label_ avec ```canvasClim```
    * définir la propriété _Gabarit > Hauteur_ à ```150px```
    * définir la propriété _Gabarit > Largeur_ à ```175px```

    _Remarque:_ l'acteur enfant d'une _toile_ doit toujours avoir une dimension fixe. Ici nous définissons la toile avec les dimensions de l'image ci-après.

6. **Ajouter** un acteur enfant de type _image_ qui contiendra l'image du climatiseur

    * renommer le _Label_ avec ```imageClim```
    * Récupérer l'image ci-dessous

        ![Empilement](assets/clim.jpg)

    * Glisser/déplacer l'image dans la zone **hachurée** de la propriété  _Spécifiques > Image_
    * Réinitialiser la propriété _Gabarit > Hauteur_ à la valeur par défaut
    * Réinitialiser également la propriété _Gabarit > Largeur_ à la valeur par défaut

7. **Sélectionner** l'acteur _toile_ ```canvasClim``` et **ajouter** un acteur enfant de type _commutateur image_ qui affichera le mode hiver/été

    * renommer le _Label_ avec ```switchImageMode```
    * récupérer les 2 images ![Cold](assets/cold.png) ![Hot](assets/hot.png)
    * réinitialiser la propriété _Gabarit > Hauteur_ à la valeur par défaut ```[vide]```
    * réinitialiser également la propriété _Gabarit > Largeur_ à la valeur par défaut ```[vide]```
    * modifier la propriété _Spécifiques > Texte On_ avec le texte ```Chaud```
    * modifier la propriété _Spécifiques > Texte Off_ avec le texte ```Froid```
    * désactiver la propriété _Spécifiques > Actif_
    * glisser la première image dans la zone hachurée de la propriété _Spécifiques > Image On_
    * glisser la deuxième image dans la zone hachurée de la propriété _Spécifiques > Image off_
    ![Hot](assets/switchImageMode.png)
    * modifier la propriété _Position > Position gauche_ avec la taille ```5px```
    * modifier la propriété _Position > Position bas_ avec la taille ```5px```

8. **Sélectionner** l'acteur _toile_ ```canvasClim``` et **ajouter** un second acteur enfant de type _commutateur image_ qui affichera le mode de fonctionnement on/off

    * renommer le _Label_ avec ```switchImageOnOff```
    * récupérer les 2 images ![Hot](assets/on.gif) ![Cold](assets/off.png)
    * réinitialiser la propriété _Gabarit > Hauteur_ à la valeur par défaut ```[vide]```
    * réinitialiser également la propriété _Gabarit > Largeur_ à la valeur par défaut ```[vide]```
    * modifier la propriété _Spécifiques > Texte On_ avec le texte ```On```
    * modifier la propriété _Spécifiques > Texte Off_ avec le texte ```Off```
    * désactiver la propriété _Spécifiques > Actif_
    * glisser la première image dans la zone hachurée de la propriété _Spécifiques > Image On_
    * glisser la deuxième image dans la zone hachurée de la propriété _Spécifiques > Image off_
    ![Hot](assets/switchImageOnOff.png)
    * modifier la propriété _Position > Position droite_ avec la taille ```5px```
    * modifier la propriété _Position > Position haut_ avec la taille ```5px```

9. **Sélectionner** l'acteur _toile_ ```canvasClim``` et **ajouter** un acteur enfant de type _image_ qui indiquera si le climatiseur est en train de fonctionner

    * renommer le _Label_ avec ```imageProgress```
    * récupérer l'image ![Hot](assets/progress.gif)
    * glisser l'image dans la zone hachurée de la propriété _Spécifiques > Image_
    * réinitialiser la propriété _Gabarit > Hauteur_ à la valeur par défaut ```[vide]```
    * réinitialiser également la propriété _Gabarit > Largeur_ à la valeur par défaut ```[vide]```
    * modifier la propriété _Position > Position gauche_ avec la taille ```70px```
    * modifier la propriété _Position > Position bas_ avec la taille ```10px```

10. **Sélectionner** l'acteur _Empilement_ ```stackClim``` et **ajouter** un acteur enfant de type _html_ qui contiendra la température de consigne

    * renommer le _Label_ avec ```htmlTempCmd```
    * définir la propriété _Spécifiques > Contenu_ avec le texte
    ```html
    <span style="white-space: nowrap;"><i class="icon-target"></i>{% raw %}{{tempCmd}}{% endraw %}°C</span>
    ```
    _Remarques:_
    * l'acteur _html_ est identique à l'acteur _text_ mais est adapté au contenu HTML
    * _icon-temperature-thermometer_ permet d'utiliser une libraire d'icones embarquée dans SynApps

    * créer la propriété proposée ```tempCmd``` de type **texte**
    * modifier les informations de la propriété additionnelle ```tempCmd``` dans l'onglet _Additionnelles > Gestion des propriétés additionnelles_
    * modifier _Nom de la propriété_ avec ```Température consigne``` et _Description_ avec ```Température de consigne```
    * définir la propriété _Spécifiques > Température consigne avec la valeur ```22 °C```
    ![Empilement](assets/previewTempCurrent.png)
    * définir la propriété _Aspect > Police > Alignement texte_ à ```Centre```

11. **Vérifier** la configuration
    * la zone de prévisualisation
    ![Empilement](assets/preview.png)

    * structure des acteurs du composites
    ![Empilement](assets/actors.png)

## Ajout du **composite** dans la **scène**

Seul l'ossature du visuel est finalisée, les propriétés personnalisées et le comportement du composite reste à configurer. Au préalable, nous allons ajouter plusieurs **instances** du composite dans la scène

1. **Sélectionner** la scène _climatiseurs_
    ![Empilement](assets/select_scene.png)

2. **Sélectionner** l'acteur _toile_ ```canvas1``` et **ajouter** un acteur enfant de type _Climatiseur_ (dans la catégrorie _Autres_ de l'explorateur d'acteurs)

    * renommer le _Label_ avec ```compositeClimEast```
    * modifier la propriété _Gabarit > Hauteur_ avec la taille ```300px```
    * modifier la propriété _Gabarit > Largeur_ avec la taille ```300px```
    * modifier la propriété _Position > Position gauche_ avec la taille ```200px```
    * modifier la propriété _Position > Position haut_ avec la taille ```240px```
    * vérifier que la propriété _Aspect > Police > Taille_ a bien la valeur de ```50px``` que nous avons configuré au niveau du composite
    * modifier cette propriété avec la valeur ```30px``` et constater que la taille du texte de l'acteur diminue
    * réinitialiser la propriété et constater que la taille est de nouveau ```50px```
    ![Empilement](assets/defaultSize.png)
    * modifier la propriété _Aspect > Couleur de fond_ avec la couleur jaune clair ```#ffe583```

3. **Dupliquer** l'acteur _Climatiseur_ ```compositeClimEast```

    * renommer le _Label_ avec ```compositeClimWest```
    * modifier la propriété _Position > Position gauche_ avec la taille ```600px```
    * modifier la propriété _Aspect > Couleur de fond_ avec la couleur gris clair ```#e0e0e0```
    ![Empilement](assets/preview2.png)
    * constater que nous avons personnalisé les 2 instances d'un même composite

## Définition des **propriétés spécifiques** du composite

Nous allons définir les propriétés personnalisées du composite pour pouvoir configurer notamment le mode de fonctionnement été/hiver, marche/arrêt, les températures ambiante et de consigne

1. **Sélectionner** le composite _Climatiseur_

2. **cliquer** sur **Gestion des propriétés** spécifiques dans l'onglet _Spécifiques_ de l'inspecteur du composite
    ![Empilement](assets/specificsProps.png)

3. **ajouter** une propriété de type _Booléen_ qui permettra de définir si le climatiseur est en marche ou arrêt

    * définir le _Label_ avec le texte _onoff_
    * définir le _Nom de la propriété_ avec le texte _Marche/Arrêt_
    * définir la _Description_ avec le texte _Climatiseur en Marche/Arrêt_

4. **ajouter** une propriété de type _Nombre_ qui permettra de définir la température de consigne

    * définir le _Label_ avec le texte _tempCmd_
    * définir le _Nom de la propriété_ avec le texte _Température consigne_
    * définir la _Description_ avec le texte _Température commandée_

5. **ajouter** une propriété de type _Nombre_ qui permettra de définir la température ambiante

    * définir le _Label_ avec le texte _tempCurrent_
    * définir le _Nom de la propriété_ avec le texte _Température ambiante_
    * définir la _Description_ avec le texte _Température mesurée par le climatiseur_

6. **ajouter** une propriété de type _Liste de choix_ qui permettra de définir le mode de fonctionnement été ou hiver

    * définir le _Label_ avec le texte _modeClim_
    * définir le _Nom de la propriété_ avec le texte _Mode_
    * définir la _Description_ avec le texte _Mode de fonctionnement_
    * Dans la liste de choix définir les 2 éléments été et hiver avec les labels respectifs ```SUMMER``` et ```WINTER```
    ![Empilement](assets/listMode.png)

7. **Vérifier** la définition des 4 propriétés spécifiques et **fermer** le _Gestionnaire de propriétés spécifiques_ en cliquant sur _Terminé_
    ![Empilement](assets/compositeProps.png)

8. **Définir** les valeurs par défaut des 4 propriétés spécifiques créées

    * définir la propriété _Spécifiques > Marche/Arrêt_ en ```sélectionné```
    * définir la propriété _Spécifiques > Température consigne_ avec la valeur ```20```
    * définir la propriété _Spécifiques > Température ambiante_ avec la valeur ```23```
    * définir la propriété _Spécifiques > Mode ambiante_ avec la sélection ```Eté```

## Liaisons des **propriétés spécifiques** du composite aux acteurs internes

Quatre propriétés spécifiques du composite ont été créées et doivent maintenant être **liées aux acteurs internes** du composite et ainsi définir le comportement du composite en fonction des valeurs définies dans ces propriétés

1. **Selectionner** l'acteur ```switchImageOnOff```

    * lier la propriété _Spécifiques > Valeur_ en _interne_ à la propriété _Spécifiques > Marche/Arrêt_ du composite
    ![Empilement](assets/bindInternal.png)
    ![Empilement](assets/bindInternal2.png)

2. **Selectionner** l'acteur ```htmlTempCurrent```

    * lier la propriété _Spécifiques > Température courante_ en _interne_ à la propriété _Spécifiques > Température courante_ du composite (même opération que la propriété précédente)

3. **Selectionner** l'acteur ```htmlTempCmd```

    * lier la propriété _Spécifiques > Température consigne_ en _interne_ à la propriété _Spécifiques > Température consigne_ du composite

4. **Selectionner** l'acteur ```switchImageMode```

    * lier la propriété _Spécifiques > Valeur_ en _interne_ à la propriété _Spécifiques > Mode_ du composite

    **_Important:_** jusqu'a présent les **données liéés** étaient de **même nature**
    * _Marche/Arrêt_ du composite et _valeur_ de _switchImageOnOff_ de type **booléen**
    * _Température courante_ du composite et _Température courante_ de _htmlTempCurrent_ de type **nombre**
    * dans le cas de _switchImageMode_ la propriété _Valeur_ est de type **booléen** et la propriété _Mode_ du composite est de type **texte**: ```SUMMER``` ou ```WINTER```. Il faut donc procéder à une **conversion** ou **transformation** de la valeur **texte** en **booléen**

    * Définir une fonction de transformation en lecture pour transformer le _Mode_ **texte** en _Valeur_ **booléen**
    ![Empilement](assets/transform.png)
    * Définir la fonction
    ```javascript
    return context.value==="SUMMER"
    ```
    ![Empilement](assets/aceJs.png)

    Les scripts seront détaillés dans le [Tutorial 6: événements et javascript](../tuto06/index.md) mais simplement savoir que dans une fonction de transformation _context.value_ contient la **valeur de la source de la liaison**: ici, la valeur de la proriété _Mode_ du composite.

    ```_return context.value==="SUMMER"``` retourne la valeur booléénne ```true``` si le mode est ```SUMMER```, sinon ```false``` (pour ```WINTER```)

5. **Sélectionner** le composite (sans acteurs sélectionnés) et **tester** son fonctionnement

    * Modifier la propriété _Spécifiques > Marche/Arrêt_ et vérifier que l'image correspondante dans la _zone de prévisualisation_ bascule bien du _rouge_ au clignotant _vert/gris_
    * Modifier la propriété _Spécifiques > Température consigne_ et vérifier que la consigne dans la _zone de prévisualisation_ change
    * Modifier la propriété _Spécifiques > Température ambiante_ et vérifier qu'elle change dans la _zone de prévisualisation_
    * Modifier la propriété _Spécifiques > Mode_ et vérifier que l'image correspondante dans la _zone de prévisualisation_ bascule bien de _été_ à _hiver_
    ![Empilement](assets/compositeTest.png)
    ![Empilement](assets/preview3.png)

## Configuration des propriétés spécifiques du composite dans la scène

La définition du composite est finalisée, nous allons maintenant lier les valeurs des propriétés spécifiques de ses instances dans la scène vers une ressource du REDY de type _Régulation ventilo-convecteur 2T_

1. **Sélectionner** la scène _climatiseurs_

2. **Sélectionner** l'acteur ```compositeClimEast```

    * définir la propriété _Spécifiques > Température consigne_ avec la valeur ```21```
    * définir la propriété _Spécifiques > Température ambiante_ avec la valeur ```19```
    * définir la propriété _Spécifiques > Mode ambiante_ avec la sélection ```Eté```
    ![compositeClimEast](assets/compositeClimEast.png)

3. **Sélectionner** l'acteur ```compositeClimWest```

    * définir la propriété _Spécifiques > Marche/Arrêt_ ```non sélectionné```
    * définir la propriété _Spécifiques > Température consigne_ avec la valeur ```25```
    * définir la propriété _Spécifiques > Température ambiante_ avec la valeur ```19```
    * définir la propriété _Spécifiques > Mode_ avec la sélection ```Hiver```

4. **Verifier** que les 2 instances du composite, ```compositeClimEast```, ```compositeClimWest``` représentent les valeurs définies
    ![preview](assets/preview4.png)

Le composite fonctionne et les valeurs définies pour les 2 instances du composite dans la scène peuvent sans difficultés être liées à une ressource de type _Régulation ventilo-convecteur 2T_ via une source de donnée, consulter le [tutorial 2 sur les liaisons](../tuto06/index.md).

Cela pose cependant **plusieurs problèmes**:

* A chaque fois que l'acteur _Climatiseur_ sera ajouté dans une scène, il faudra
    1. definir sa source de donnée principale de type _Régulation ventilo-convecteur 2T_ et
    2. lier les 4 propriétés _Spécifiques_ _Marche/Arrêt_, _Température consigne_, _Température ambiante_ ainsi que _Mode_ ...
* Cela ne favorise ni la réutisabilité, ni la maintenabilité
* L'utilisateur qui utilise le composite dans la scène n'est pas forcemment l'auteur du composite: il ne sait peut-être pas, ni comment, ni quels chemins relatifs de la ressources doivent être liées aux propriétés

C'est le principe de la **boite noir**, l'utilisateur veut juste ajouter un composite sur la scène, définir sa ressource et tout doit fonctionner ! Et c'est possible avec les composites que nous appelons alors **Metiers**

## Composite Metier lié à une ressource du REDY

Nous pourrions modifier le composite standard précédement créé en composite métier, capable d'exploiter directement une ressource de type ```Régulation ventilo-convecteur 2T```. Mais, plutôt que de modifier le composite éxistant, nous allons en créer un nouveau, **métier**, capable d'exploiter directement la ressource ci-dessus. Bien sur, il contiendra et exploitera dans ses acteurs internes, le composite précédemment créé

Notre **objectif** ici est double:

* **Montrer** comment les acteurs composites peuvent s'intégrer de façon **modulaire**
* **Conserver** l'acteur composite initial **standard** pour permettre sa configuration directement dans une scène, voir dans un autre composite métier, lorsque la source de donnée n'est pas une ressource de type ```Régulation ventilo-convecteur 2T```

1. **Sélectionner** l'onglet composites et **créer** un nouvel acteur composite

    ![Empilement](assets/composites.png)

    * modifier le _label_ du composite en ```compositeClim2``` et le _nom_ avec ```Climatiseur métier```
    * modifier la _description_ du composite en ```Acteur de visualisation et de contrôle d'un climatiseur avec ressource Régulation ventilo-convecteur 2T```
    * modifier la _catégorie_ du composite avec la sélection ```Métier```. Cela permet de retrouver le composite dans cette catégorie dans l'_explorateur d'acteurs_
    * Récupérer l'image ci-dessous

        ![Empilement](assets/climBus.jpg)
    * Glisser/déplacer l'image dans la zone **hachurée** de la propriété  _Logo_
    ![Empilement](assets/compositeClim2_inspector.png)

    * définir la propriété _Source de données > Source_
    ![compositeDatasource](assets/compositeDatasource.png)

    **Important:** nous définissons une source de donnée sur le composite afin d'avoir une **ressource de travail** pour configurer les liaisons. Cette ressource pourra et devra  être modifié au moment de l'ajout d'une instance de ce composite dans la scène

    * créer la source de donnée WOS ![createDatasource](assets/createDatasource.png)
    * parcourir le chemin vers la ressource ```VTCAtlanticEst``` dans le dossier ```Tutorial5```
    ```text
    : / easy / RESS / R00005 / R0003
    ```
    * modifier le nom de la source de donnée par ```dsVTCAtlanticEst``` puis cliquer sur **Créer**
        ![defineDatasource](assets/defineDatasource.png)

    * modifier la _Classe de la donnée_ pour indiquer la classe de ressource que sait consommer le composite. Cela facilitera la configuration du composite lors de l'ajout dans une scène en indiquant à l'utilisateur le type de ressource à définir. Sélectionner **Classe de la donnée** pour contraindre le composite à une ressource de type _ventilo-convecteur 2T_

        ![defineDatasource](assets/compositeClass.png)
        ![defineDatasource](assets/compositeClass2.png)

2. **Définir** l'acteur principal avec un acteur _Empilement_

3. **Ajouter** un acteur enfant de type _Climatiseur_

    * renommer le _Label_ avec ```compositeClimDrived```
    * réinitialiser la propriété _Gabarit > Hauteur_ avec la valeur par défaut ```[Vide]```
    * définir la propriété _Position > Align. vertical_ a ```Etendre```
    * définir la propriété _Position > Align. horizontal_ a ```Etendre```
    * lier la propriété _Spécifiques > Marche/Arrêt_ en Source de données
    ![bindDatasource](assets/bindComposite2.png)
    * saisir ```VC_Stop``` dans le _Chemin_ ou utiliser l'_explorateur de chemin relatif_
    * sélectionner la propriété _Valeur_ et la liaison en lecture _Rafraichie_ et **Lier**
    ![bindDatasource2](assets/bindDatasource2.png)
    * lier la propriété _Spécifiques > Température consigne_ en Source de données

    _Remarque:_ la valeur du chemin de la ressource ```VC_Stop``` retourne ```true``` lorsque le climatiseur est arreté et ```false``` lorsqu'il est en marche. Hors la propriété _Spécifiques > Marche/Arrêt_ doit avoir la valeur ```true``` pour indiquer que le climatiseur est en marche: il faut donc **inverser** la valeur provenant de la source de données avec un **fonction de transformation**

    * editer le script de transformation lecture
    ![transform2](assets/transform2.png)
    * écrire la fonction suivante
        ```javascript
        return !context.value
        ```
        Pour rappel _context.value_ retourne la valeur de la source = valeur du noeud ```VC_Stop```

        Le caratere _!_ signifie ```not``` et va donc inverser la valeur de la ressource, ce qui est le comportement souhaité

    * lier la propriété _Spécifiques > Température consigne_ en Source de données avec le chemin ```VC_Sp```, la propriété _valeur_ et la liaison en lecture _Rafraichie_

    _Remarque:_ la consigne est accessible en écriture mais ne sera pas commandé par l'acteur _compositeClim2_. C'est un choix que nous avons fait quant au périmêtre métier du composite. Nous commenderons la consigne depuis la scène, la liaison n'est donc pas autorisée en écriture.

    * lier la propriété _Spécifiques > Température ambiante_ en Source de données avec le chemin ```VC_At```, la propriété _valeur_ et la liaison en lecture _Rafraichie_

    * lier la propriété _Spécifiques > Mode_ en Source de données avec le chemin ```VC_Cold```, la propriété _valeur_ et la liaison en lecture _Rafraichie_

    _Remarque:_ la valeur du chemin de la ressource ```VC_Cold``` retourne ```true``` lorsque le climatiseur est en mode _hiver_ et ```false``` en mode _été_. Hors la propriété _Spécifiques > Mode_ doit avoir la valeur ```WINTER``` ou ```SUMMER```: il faut donc **modifier** la valeur provenant de la source de données avec un **fonction de transformation**

    * editer le script de transformation lecture de _Mode_ avec la fonction suivante
        ```javascript
        return context.value ? "WINTER" : "SUMMER";
        ```
        Pour rappel _context.value_ retourne la valeur de la source = valeur du noeud ```VC_Cold```

        Le caratere _?_ est une instruction conditionnelle qui retournera ```WINTER``` lorsque _context.value_ est ```true``` sion ```SUMMER```

La définition du composite métier est finalisée ! Les valeurs _Spécifiques_ _Marche/Arrêt_, _Température consigne_, _Température ambiante_ et _Mode_ ainsi que la représentation dans la _zone de prévisualisation_ doivent désormains refleter les données de la ressource _VTCAtlanticEst_

Modifier les valeurs directement dans le paramétrage de la Ressource du REDY puis attendre (max 30 secondes ou forcer le rechargement avec F5) le rafraissement de la source de donnée pour vérifier que le composite reflète bien les modifications

![compositeClim2_inspector2](assets/compositeClim2_inspector2.png)
![preview5](assets/preview5.png)

## Modification de la scène par remplacement du composite métier

Nous avons configuré la scène avec 2 intances de composite _compositeClim_. Hors nous avons désormais un composite métier _compositeClim2_ qui sait exploiter des ressources _Régulation ventilo-convecteur 2T_. Nous allons donc supprimer ces 2 instances, les remplacer par notre composite métier puis associer les 2 ressources

1. **Sélectionner** la scène _climatiseurs_

2. **Sélectionner** l'acteur ```compositeClimEast``` et le supprimer ![preview5](assets/actor_delete.png)

3. **Sélectionner** l'acteur ```compositeClimWest``` et le supprimer également

4. **Sélectionner** l'acteur _toile_ ```canvas1``` et **ajouter** un acteur enfant de type _Climatiseur métier_ (dans la catégrorie _Métiers_ de l'explorateur d'acteurs)

    * renommer le _Label_ avec ```compositeClimEast```
    * modifier la propriété _Gabarit > Hauteur_ avec la taille ```300px```
    * modifier la propriété _Gabarit > Largeur_ avec la taille ```300px```
    * modifier la propriété _Position > Position gauche_ avec la taille ```200px```
    * modifier la propriété _Position > Position haut_ avec la taille ```240px```

5. **Dupliquer** l'acteur _Climatiseur_ ```compositeClimEast```

    * renommer le _Label_ avec ```compositeClimWest```
    * modifier la propriété _Position > Position gauche_ avec la taille ```600px```
    * modifier la propriété _Source de données > Source_
    ![actorDatasource2](assets/actorDatasource2.png)
    * créer une nouvelle source de donnée _WOS_
    ![createDatasource2](assets/createDatasource2.png)
    * parcourir le chemin vers la ressource ```VTCAtlanticWest``` dans le dossier ```Tutorial5```
    ```text
    : / easy / RESS / R00005 / R0004
    ```
    * modifier le nom de la source de donnée par ```dsVTCAtlanticWest``` puis cliquer sur **Créer**
        ![defineDatasource2](assets/defineDatasource2.png)
    * vérifier que l'acteur représente bien les valeurs de la ressource du REDY ```VTCAtlanticWest```

6. **Sélectionner** l'acteur _toile_ ```canvas1``` et **ajouter** un acteur enfant de type _Curseur_

    * renommer le _Label_ avec ```sliderEast```
    * définir la propriété _Gabarit > Largeur_ avec la taille ```400px```
    * définir la propriété _Position > Position gauche_ avec la valeur ```120px```
    * définir la propriété _Position > Position haut_ avec la valeur ```630px```
    * définir la propriété _Source de données > Source_ avec la source de donnée ```dsVTCAtlanticEst```
    * définir la propriété _Spécifiques > Min_ avec la valeur ```15```
    * définir la propriété _Spécifiques > Max_ avec la valeur ```35```
    * définir la propriété _Spécifiques > Bar_ avec la sélection ```Avant curseur```
    * définir la propriété _Spécifiques > Couleur bar_ avec la couleur ```#ff8000```
    * définir la propriété _Spécifiques > Interval_ avec la valeur ```0.5```
    * lier la propriété  _Spécifiques > Valeur_ en source de donnée avec le chemin ```VC_Sp```, la propriété _valeur_ et la liaison en lecture _Rafraichie_ et **écriture**
    ![bindDatasource3](assets/bindDatasource3.png)

7. **Dupliquer** l'acteur ```sliderEast```

    * renommer le _Label_ avec ```sliderWest```
    * définir la propriété _Gabarit > Largeur_ avec la taille ```400px```
    * définir la propriété _Position > Position gauche_ avec la valeur ```600px```
    * définir la propriété _Source de données > Source_ avec la source de donnée ```dsVTCAtlanticWest```

8. **Déployer**, **éxécuter** et **vérifier** que:

    * vous pouvez commander les consignes de température des 2 ressources
    * les températures de consigne sur les 2 instances du composite _Climatiseur métier_ changent en conséquence

## **Partage** du composite

Nous avons réalisé 2 acteurs composites qui repondent au besoin de la SynApp. Hors, il est fort probable que nous souhaitions **réutiliser** le composite dans d'autre SynApps et le **partager** avec d'autres utilisateurs

Ultérieurement, SynApps MAKER disposera d'un mécanisme  permettant d'**importer** et **exporter** tout ou partie des objets d'une SynApp et d'un composite notamment
En attendant, il est tout de même possible d'exporter, et d'importer un composite en tant que fichier de paramétrage partiel .WK4 depuis la Configuration du REDY

Nous allons créer une nouvelle SynApp et importer le composite ```compositeClim``` créé dans la SynApp ```tuto05```

1. Lister les SynApps et créer une nouvelle SynApps que vous appelerez ```Test Import```
    ![bindDatasource3](assets/listSynApps.png)]

2. **Naviguer** dans l'interface de **Configuration** du REDY et l'onglet **Explorateur**

3. **Sélectionner** le chemin du compoite
    ```text
    :easy.SynApps.tuto05.Composites.compositeClim
    ```
    ![bindDatasource3](assets/redyExplorator.png)

4. **Cliquer** sur le bouton **Exporter**

5. **Sélectionner** le chemin du dossiers des compoite dans la nouvelle SynApp ```Test Import```
    ```text
    :easy.SynApps.Test_Import.Composites
    ```

6. **Cliquer** sur le bouton _Choisir un fichier_, **sélectionner** le fichier _.WK4_ exporté précédemment, et **ajouter**
    ![redyImport](assets/redyImport.png)

7. **Vérifier** que le composite est bien importé
    ![redyImport2](assets/redyImport2.png)

8. **Retourner** dans SynApps MAKER et nettoyer le cache pour forcer le rechargement du paramétrage de la SynApp depuis le REDY

    _Remarque:_ souvenez vous, SynApps **cache les configurations** des SynApps pour des questions d'**optimisation** du temps de chargement. Il se base notamment sur un **numéro de build** pour savoir si la SynApp a été mise à jour et dans ce cas **forcer le rechargement** de la SynApp depuis le REDY

    Ici, nous avons importé un paramétrage depuis le REDY, le numéro de build de la SynApp ```Test Import``` est donc resté inchangé, c'est pourquoi, nous nettoyons le cache des SynApps dans le navigateur

9. **Rafraichir** la SynApp avec F5

10. **Sélectionner** l'onglet composites et vérifier la présence du composite ```Climatiseur``` dans la SynApp ```Test Import```

Vous pouvez alors créer une scène et utiliser le composite !

## Que retenir

Vous avez mis en oeuvre un des concepts fondamentaux de SynApps: les **acteurs composites**

Ils permettent de construire de nouveaux acteurs à partir d'acteurs **natifs** ou d'autres **composites** et ainsi avoir une construction plus modulaire qui favorise **maintenabilité** et **réutisabilité** !

Ils permettent également d'avoir des profils utilisateurs de **SynApps MAKER** de niveaux différents:

* **avancés**: capable de **construire** des acteurs composites plus ou moins évolués
* **standards**: capable de d'**utiliser** ces acteurs composites sans avoir besoin de comprendre comment ils fonctionnent. Principe de la **boite noir** !

Nous avons vu comment **personnaliser les propriétés** par défaut de l'acteur composite, par exemple la couleur de fond.
Nous avons également défini de **nouvelles propriétés**  qui permettent de personnaliser l'instance d'acteur composite, par exemple, _Mode_ et _Températures_

Nous avons vu également comment construire des acteurs **métiers** qui savent exploiter une source de donnée particulière, par exemple une ressource du REDY. En tant qu'utilisateur du composite, il a suffit de définir la source de données de l'acteur composite _Climatiseur métier_ pour que ce dernier soit pleinement **opérationnel** !

Enfin, en attendant un mécanisme d'import/export natif depuis SynApps MAKER, nous avons **importé** un composite via le **paramétrage partiel** du REDY

## Conclusion

Le **tutorial 5** sur les acteurs _composites_ est **terminé**. La maitrise de la création est extrémement importante pour construire des applications ambitieuses, maintenables et réutilisables !

Il est important de bien définir le **périmêtre fonctionnel** de chaque composite et exposer notamment de façon intelligible ses **propriétés personnalisées**. La **description** est également importante pour donner des indications à celui qui va utiliser le composite

L'acteur composite est une fonctionnalité majeure de SynApps et permet de construire un éco-système d'acteurs métiers réutilisables et ainsi priviligier **qualité** et **productivité** !

Vous pouvez remonter les **bugs** & **remarques** concernant ce tutorial, SynApps RUNTIME & MAKER sur [GitHub](https://github.com/witsa/synapps/issues)

[Tutoriel suivant sur les événements et fonctions](../tuto06/index.md)