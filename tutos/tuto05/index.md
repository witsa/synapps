# Tutorial 5: les acteurs **composites**

[Home](../../sitemap.md) > [Tutoriaux](../index.md) > [Tutorial](index.md)

Dans ce tutorial, nous allons mettre un oeuvre l'acteur **composite** qui a ceci de particulier: la construction de **nouveaux acteurs** à partir d'acteurs éxistants. Ces derniers peuvent être soit des acteurs:

* **natifs**: disponibles dans toute SynApp
* **composites**: construits avec le MAKER, ils sont un usage avancé et nécessite une bonne compréhension du fonctionnement de SynApps

Quelque soit la nature de l'acteur, **son usage est identique**,la distinction permet donc uniquement de les différencier techniquement

Le composite est un élément **fondamental** de toute SynApp, car il favorise:

* **réutisabilité**: au sein d'une même SynApp et vers d'autres SynApp et utilisateurs via des mécanismes d'import/export

* **maintenabilité**: la modification d'un acteur composite est propagée automatiquement à l'ensemble des scènes qui l'utilise

* **modularité**: construction de scènes complexes par compositions d'acteurs simples et imbriqués

Ils peuvent être classés dans deux grandes catégories:

* **standard**: ils ont une fonction de représentation indépendante d'une source de donnée. Par exemple: une jauge

* **métiers**: ils ont besoin d'une source de données pour fonctionner ou ils utilisent en interne une ressource du REDY. Par exemple: l'acteur journal

![Empilement](assets/nature.png)
_Classement des acteurs par nature et catégorie_

## Description

L'objectif du tutorial est la construction d'un acteur composite standard permettant de visualiser/gérer une climatiseur

## Prerequis

Créer une nouvelle SynApp **tuto05** avec le _MAKER_. Modifier le _label_ de la première scène en <code>sceneClims</code> et le _nom_ avec <code>scène climatiseurs</code> puis déployer.

## Construction de la **scène climatiseurs**

1. Dans la scène courante <code>sceneClims</code> définissez l'acteur principal avec un acteur **toile**

2. **Ajouter** un acteur enfant de type **image** et définir le fond de plan avec l'image ci-dessous. 
    * Click droit sur l'image ci-dessous et _Enregistrer sous_ dans un dossier local
    ![Empilement](assets/backgroundPlan.png)

    * Ouvrir le dossier local contenant l'image
    * Glisser/déplacer l'image dans la zone **hachurée** de la propriété  _Spécifiques > Image_ 
    * Modifier la propriété _Gabarit > Hauteur_ à la valeur par défaut
    * Modifier également la propriété _Gabarit > Largeur_ à la valeur par défaut

## Construction de l'ossature du **composite**

1. **Sélectionner** l'onglet composites et **créer** un nouvel acteur composite

    ![Empilement](assets/composites.png)

    * modifier le _label_ du composite en <code>compositeClim</code> et le _nom_ avec <code>Climatiseur</code>
    * modifier la _description_ du composite en <code>Acteur de visualisation et de contrôle d'un climatiseur</code>
    ![Empilement](assets/compositeClim_inspector.png)
    * Récupérer l'image ci-dessous

        ![Empilement](assets/clim.jpg)

    * Glisser/déplacer l'image dans la zone **hachurée** de la propriété  _Logo_
            ![Empilement](assets/logo.png)
        _Remarques:_ le logo permet d'identifier visuellement le composite dans l'_explorateur d'acteurs_. Il est également possible de faire une copie d'écran du composite avec l'icone **appareil photo** ci-dessus: à tester mais le résultat sera toujours mieux avec une image adaptée

    * définir la propriété _Aspect > Police > Taille_ à <code>50px</code>

    _Important:_ les propriétés définies **directement** sur le composite sont des **valeurs par défaut** qui seront **initialisées** lors de l'ajout du composite dans la scène.
    Elles sont alors modifiables ce qui permet la personnalisation du composite.
    Ici, nous définissons la police par défaut à <code>50px</code> directement sur le composite. Cette taille sera modifiable lors de l'ajout du composite dans le scène.
    Cet aspect est extrémement important: un composite peut être considéré comme une **boite noir** avec des **propriétés publiques personnalisables**. Editer le composite revient à ouvrir la boite et définir son comportement. Nous reviendrons sur cet aspect ultérieurement dans le tutorial

2. **Définissez** l'acteur principal avec un acteur _empilement_

    * Renommer le _Label_ avec <code>stackClim</code>
    * définir la propriété _Aspect > Couleur_ à un bleu clair <code>#45aadb</code>

3. **Ajouter** un acteur enfant de type _html_ qui contiendra la température mesurée courante

    * renommer le _Label_ avec <code>htmlTempCurrent</code>
    * définir la propriété _Spécifiques > Contenu_ avec le texte
    ```html
    <span style="white-space: nowrap;"><i class="icon-temperature-thermometer"></i> {{tempCurrent}}°C</span>
    ```
    _Remarques:_
    * l'acteur _html_ est identique à l'acteur _text_ mais est adapté au contenu HTML
    * _icon-temperature-thermometer_ permet d'utiliser une libraire d'icones embarquée dans SynApps

    * créer la propriété proposée <code>tempCurrent</code> de type **texte**
    ![Empilement](assets/tempCurrent.png)
    * modifier les informations de la propriété additionnelle <code>tempCurrent</code> dans l'onglet _Additionnelles > Gestion des propriétés additionnelles_
    ![Empilement](assets/addProps.png)
    * modifier _Nom de la propriété_ avec <code>Température courante</code> et _Description_ avec <code>Température mesurée par le climatiseur</code>
    ![Empilement](assets/editProps.png)
    * définir la propriété _Spécifiques > Température courante_ avec la valeur <code>21</code>
    ![Empilement](assets/previewTempCurrent.png)
    * définir la propriété _Aspect > Police > Alignement texte_ à <code>Centre</code>

4. **Sélectionner** l'acteur <code>stackClim</code> et **ajouter** un acteur enfant de type _boite à vue_ qui adaptera le visuel du climatiseur à la taille de l'écran

    * renommer le _Label_ avec <code>viewBoxClim</code>
    * définir la propriété _Position > Align. vertical_ à <code>Etendre</code>
    * définir la propriété _Position > Align. horizontal_ à <code>Etendre</code>
    * réinitialiser la propriété _Gabarit > Hauteur_ à <code>[vide]</code>

5. **Ajouter** un acteur enfant de type _toile_ qui contiendra les différents acteurs du visuel

    * renommer le _Label_ avec <code>canvasClim</code>
    * définir la propriété _Gabarit > Hauteur_ à <code>150px</code>
    * définir la propriété _Gabarit > Largeur_ à <code>175px</code>

    _Remarque:_ l'acteur enfant d'une _toile_ doit toujours avoir une dimension fixe. Ici nous définissons la toile avec les dimensions de l'image ci-après.

6. **Ajouter** un acteur enfant de type _image_ qui contiendra l'image du climatiseur

    * renommer le _Label_ avec <code>imageClim</code>
    * Récupérer l'image ci-dessous

        ![Empilement](assets/clim.jpg)

    * Glisser/déplacer l'image dans la zone **hachurée** de la propriété  _Spécifiques > Image_
    * Réinitialiser la propriété _Gabarit > Hauteur_ à la valeur par défaut
    * Réinitialiser également la propriété _Gabarit > Largeur_ à la valeur par défaut

7. **Sélectionner** l'acteur _toile_ <code>canvasClim</code> et **ajouter** un acteur enfant de type _commutateur image_ qui affichera le mode hiver/été

    * renommer le _Label_ avec <code>switchImageMode</code>
    * récupérer les 2 images ![Hot](assets/hot.png) ![Cold](assets/cold.png)
    * réinitialiser la propriété _Gabarit > Hauteur_ à la valeur par défaut <code>[vide]</code>
    * réinitialiser également la propriété _Gabarit > Largeur_ à la valeur par défaut <code>[vide]</code>
    * modifier la propriété _Spécifiques > Texte On_ avec le texte <code>Chaud</code>
    * modifier la propriété _Spécifiques > Texte Off_ avec le texte <code>Froid</code>
    * désactiver la propriété _Spécifiques > Actif_
    * glisser la première image dans la zone hachurée de la propriété _Spécifiques > Image On_
    * glisser la deuxième image dans la zone hachurée de la propriété _Spécifiques > Image off_
    ![Hot](assets/switchImageMode.png)
    * modifier la propriété _Position > Position gauche_ avec la taille <code>5px</code>
    * modifier la propriété _Position > Position bas_ avec la taille <code>5px</code>

8. **Sélectionner** l'acteur _toile_ <code>canvasClim</code> et **ajouter** un second acteur enfant de type _commutateur image_ qui affichera le mode de fonctionnement on/off

    * renommer le _Label_ avec <code>switchImageOnOff</code>
    * récupérer les 2 images ![Hot](assets/on.gif) ![Cold](assets/off.png)
    * réinitialiser la propriété _Gabarit > Hauteur_ à la valeur par défaut <code>[vide]</code>
    * réinitialiser également la propriété _Gabarit > Largeur_ à la valeur par défaut <code>[vide]</code>
    * modifier la propriété _Spécifiques > Texte On_ avec le texte <code>On</code>
    * modifier la propriété _Spécifiques > Texte Off_ avec le texte <code>Off</code>
    * désactiver la propriété _Spécifiques > Actif_
    * glisser la première image dans la zone hachurée de la propriété _Spécifiques > Image On_
    * glisser la deuxième image dans la zone hachurée de la propriété _Spécifiques > Image off_
    ![Hot](assets/switchImageOnOff.png)
    * modifier la propriété _Position > Position droite_ avec la taille <code>5px</code>
    * modifier la propriété _Position > Position haut_ avec la taille <code>5px</code>

9. **Sélectionner** l'acteur _toile_ <code>canvasClim</code> et **ajouter** un acteur enfant de type _image_ qui indiquera si le climatiseur est en train de fonctionner

    * renommer le _Label_ avec <code>imageProgress</code>
    * récupérer l'image ![Hot](assets/progress.gif)
    * glisser l'image dans la zone hachurée de la propriété _Spécifiques > Image_
    * réinitialiser la propriété _Gabarit > Hauteur_ à la valeur par défaut <code>[vide]</code>
    * réinitialiser également la propriété _Gabarit > Largeur_ à la valeur par défaut <code>[vide]</code>
    * modifier la propriété _Position > Position gauche_ avec la taille <code>70px</code>
    * modifier la propriété _Position > Position bas_ avec la taille <code>10px</code>

10. **Sélectionner** l'acteur _empilement_ <code>stackClim</code> et **ajouter** un acteur enfant de type _html_ qui contiendra la température de consigne

    * renommer le _Label_ avec <code>htmlTempCmd</code>
    * définir la propriété _Spécifiques > Contenu_ avec le texte
    ```html
    <span style="white-space: nowrap;"><i class="icon-target"></i> {{tempCmd}}</span>
    ```
    _Remarques:_
    * l'acteur _html_ est identique à l'acteur _text_ mais est adapté au contenu HTML
    * _icon-temperature-thermometer_ permet d'utiliser une libraire d'icones embarquée dans SynApps

    * créer la propriété proposée <code>tempCmd</code> de type **texte**
    * modifier les informations de la propriété additionnelle <code>tempCmd</code> dans l'onglet _Additionnelles > Gestion des propriétés additionnelles_
    * modifier _Nom de la propriété_ avec <code>Température consigne</code> et _Description_ avec <code>Température de consigne</code>
    * définir la propriété _Spécifiques > Température consigne avec la valeur <code>22 °C</code>
    ![Empilement](assets/previewTempCurrent.png)
    * définir la propriété _Aspect > Police > Alignement texte_ à <code>Centre</code>

11. **Vérifier** la configuration
    * la zone de prévisualisation
    ![Empilement](assets/preview.png)

    * structure des acteurs du composites
    ![Empilement](assets/actors.png)

## Ajout du **composite** dans la **scène**

Seul l'ossature du visuel est finalisée, les propriétés personnalisées et le comportement du composite reste à configurer. Au préalable, nous allons ajouter plusieurs **instances** du composite dans la scène

1. **Sélectionner** la scène _climatiseurs_
    ![Empilement](assets/select_scene.png)

2. **Sélectionner** l'acteur _toile_ <code>canvas1</code> et **ajouter** un acteur enfant de type _Climatiseur_ (dans la catégrorie _Autres_ de l'explorateur d'acteurs)

    * renommer le _Label_ avec <code>compositeClimEast</code>
    * modifier la propriété _Gabarit > Hauteur_ avec la taille <code>300px</code>
    * modifier la propriété _Gabarit > Largeur_ avec la taille <code>300px</code>
    * modifier la propriété _Position > Position gauche_ avec la taille <code>200px</code>
    * modifier la propriété _Position > Position haut_ avec la taille <code>240px</code>
    * vérifier que la propriété _Aspect > Police > Taille_ a bien la valeur de <code>50px</code> que nous avons configuré au niveau du composite
    * modifier cette propriété avec la valeur <code>30px</code> et constater que la taille du texte de l'acteur diminue
    * réinitialiser la propriété et constater que la taille est de nouveau <code>50px</code>
    ![Empilement](assets/defaultSize.png)
    * modifier la propriété _Aspect > Couleur de fond_ avec la couleur jaune clair <code>#ffe583</code>

3. **Dupliquer** l'acteur _Climatiseur_ <code>compositeClimEast</code>

    * renommer le _Label_ avec <code>compositeClimWest</code>
    * modifier la propriété _Position > Position gauche_ avec la taille <code>600px</code>
    * modifier la propriété _Aspect > Couleur de fond_ avec la couleur gris clair <code>#e0e0e0</code>
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

5. **ajouter** une propriété de type _Nombre_ qui permettra de définir la température de consigne

    * définir le _Label_ avec le texte _tempCurrent_
    * définir le _Nom de la propriété_ avec le texte _Température ambiante_
    * définir la _Description_ avec le texte _Température mesurée par le climatiseur_

6. **ajouter** une propriété de type _Liste de choix_ qui permettra de définir le mode de fonctionnement été ou hiver

    * définir le _Label_ avec le texte _modeClim_
    * définir le _Nom de la propriété_ avec le texte _Mode_
    * définir la _Description_ avec le texte _Mode de fonctionnement_
    * Dans la liste de choix définir les 2 éléments été et hiver avec les labels respectifs <code>SUMMER</code> et <code>WINTER</code>
    ![Empilement](assets/listMode.png)

7. **Vérifier** la définition des 4 propriétés spécifiques et **fermer** le _Gestionnaire de propriétés spécifiques_ en cliquant sur _Terminé_
    ![Empilement](assets/compositeProps.png)

8. **Définir** les valeurs par défaut des 4 propriétés spécifiques créées

    * définir la propriété _Spécifiques > Marche/Arrêt_ en <code>sélectionné</code>
    * définir la propriété _Spécifiques > Température consigne_ avec la valeur <code>20</code>
    * définir la propriété _Spécifiques > Température ambiante_ avec la valeur <code>23</code>
    * définir la propriété _Spécifiques > Mode ambiante_ avec la sélection <code>Eté</code>

## Liaisons des **propriétés spécifiques** du composite aux acteurs

Quatre propriétés spécifiques du composite ont été créées et doivent maintenant être **liées aux acteurs internes** du composite et ainsi définir le comportement du composite en fonction des valeurs définies dans ces propriétés

1. **Selectionner** l'acteur <code>switchImageOnOff</code>

    * lier la propriété _Spécifiques > Valeur_ en _interne_ à la propriété _Spécifiques > Marche/Arrêt_ du composite
    ![Empilement](assets/bindInternal.png)
    ![Empilement](assets/bindInternal2.png)

2. **Selectionner** l'acteur <code>htmlTempCurrent</code>

    * lier la propriété _Spécifiques > Température courante_ en _interne_ à la propriété _Spécifiques > Température courante_ du composite (même opération que la propriété précédente)

3. **Selectionner** l'acteur <code>htmlTempCmd</code>

    * lier la propriété _Spécifiques > Température consigne_ en _interne_ à la propriété _Spécifiques > Température consigne_ du composite

4. **Selectionner** l'acteur <code>switchImageMode</code>

    * lier la propriété _Spécifiques > Valeur_ en _interne_ à la propriété _Spécifiques > Mode_ du composite

    **_Important:_** jusqu'a présent les **données liéés** étaient de **même nature**
    * _Marche/Arrêt_ du composite et _valeur_ de _switchImageOnOff_ de type **booléen**
    * _Température courante_ du composite et _Température courante_ de _htmlTempCurrent_ de type **nombre**
    * dans le cas de _switchImageMode_ la propriété _Valeur_ est de type **booléen** et la propriété _Mode_ du composite est de type **texte**: <code>SUMMER</code> ou <code>WINTER</code>. Il faut donc procéder à une **conversion** ou **transformation** de la valeur **texte** en **booléen**

    * Définir une fonction de transformation en lecture pour transformer le _Mode_ **texte** en _Valeur_ **booléen**
    ![Empilement](assets/transform.png)
    * Définir la fonction
    ```javascript
    return context.value==="SUMMER"
    ```
    ![Empilement](assets/aceJs.png)

    Les scripts seront détaillés dans le [Tutorial 6: événements et javascript](../tuto06/index.md) mais simplement savoir que dans une fonction de transformation _context.value_ contient la **valeur de la source de la liaison**: ici, la valeur de la proriété _Mode_ du composite.

    <code>_return context.value==="SUMMER"</code> retourne la valeur booléénne <code>true</code> si le mode est <code>SUMMER</code>, sinon <code>false</code> (pour <code>WINTER</code>)

5. **Sélectionner** le composite (sans acteurs sélectionnés) et **tester** son fonctionnement

    * Modifier la propriété _Spécifiques > Marche/Arrêt_ et vérifier que l'image correspondante dans la _zone de prévisualisation_ bascule bien du _rouge_ au clignotant _vert/gris_
    * Modifier la propriété _Spécifiques > Température consigne_ et vérifier que la consigne dans la _zone de prévisualisation_ change
    * Modifier la propriété _Spécifiques > Température ambiante_ et vérifier qu'elle change dans la _zone de prévisualisation_
    * Modifier la propriété _Spécifiques > Mode_ et vérifier que l'image correspondante dans la _zone de prévisualisation_ bascule bien de _été_ à _hiver_
      ![Empilement](assets/compositeTest.png)