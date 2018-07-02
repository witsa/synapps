# Tutorial 8: les tailles et gabarits - **<span style='color:green'>Débutant</span>**

[Home](../../sitemap.md) > [Tutoriaux](../index.md)

Un des éléments fondateur de SynApps est la capacité à construire des applications adaptatives: on parle également de **responsive design** ou site web adaptatif

[Wikipédia](https://fr.wikipedia.org/wiki/Site_web_adaptatif){:target="_blank"}

Il est important de bien comprendre comment définir les tailles des acteurs pour construire des SynApps qui s'adaptent au mieux aux différentes dimensions d'écrans

_Remarque:_ cela ne veut pas dire qu'une application réalisée pour un mode desktop sera parfaitement adaptée à un smartphone. Dans ce cas, il est préferrable de réaliser 2 applications différentes pour le mode desktop/tablette et smartphone
Par contre, en respectant les indications de ce tutoriel, votre application s'adaptera parfaitement aux différentes tailles d'écrans de ces deux types de restitution

## Prérequis

* Créer une nouvelle SynApp **tuto08**

## Construction de la scène de test

Nous allons construire une scène simple afin de mettre en évidence le comportement des différents types de taille sur le rendu d'un acteur

1. **Modifier** le _label_ de la première scène en ```sceneSizes``` et le _nom_ avec ```Test des tailles``` puis déployer

2. **Définir** l'acteur principal avec un acteur _Empilement_ qui contiendra la barre de commande, le journal à proprement parlé ainsi qu'une modale de configuration

    * renommer le _Label_ avec ```stackRoot```
    * modifier la propriété _Aspect > Police > Taille_ en ```3em```
    * définir la propriété _Aspect > Police > Alignement texte_ en ```Centre```

3. **Ajouter** un acteur enfant de type _Empilement_ qui permettra de saisir la taille de la hauteur

    * renommer le _Label_ avec ```stackInputHeight```
    * modifier la propriété _Spécifiques > Orientation_ en ```Horizontale```
    * réinitialiser la propriété _Gabarit > Hauteur_ avec la valeur par défaut ```[vide]```

4. **Ajouter** un acteur enfant de type _Texte_ qui contiendra le libellé hauteur

    * renommer le _Label_ avec ```textHeight```
    * modifier la propriété _Spécifiques > Contenu_ en ```Hauteur```

5. **Sélectionner** l'acteur ```stackInputHeight``` et **ajouter** un acteur enfant de type _Boite de texte_ qui permettra de saisir la taille

    * renommer le _Label_ avec ```textboxHeight```
    * modifier la propriété _Spécifiques > Valeur_ en ```200px```
    * modifier la propriété _Spécifiques > Texte d'aide_ en ```Hauteur du texte```
    * modifier la propriété _Spécifiques > Taille_ en ```15```
    * modifier la propriété _Aspect > Police > Taille_ en ```1em```

6. **Sélectionner** puis **dupliquer** l'acteur ```stackInputHeight```

    * renommer le _Label_ avec ```stackInputWidth```

7. **Sélectionner** l'acteur enfant de type _Texte_ sous (=enfant de) l'acteur ```stackInputHeight```

    * renommer le _Label_ avec ```textWidth```
    * modifier la propriété _Spécifiques > Contenu_ en ```Largeur```

8. **Sélectionner** l'acteur enfant de type _Boite de texte_ sous l'acteur ```stackInputHeight```

    * renommer le _Label_ avec ```textboxWidth```
    * modifier la propriété _Spécifiques > Valeur_ en ```100%```
    * modifier la propriété _Spécifiques > Texte d'aide_ en ```Largeur du texte```

9. **Sélectionner** l'acteur ```stackRoot``` et **ajouter** un acteur enfant de type _Texte_ auquel seront appliquées les tailles définies par l'utilisateur

    * renommer le _Label_ avec ```textSize```
    * modifier la propriété _Spécifiques > Contenu_ avec le code HTML

    ```HTML
    <span class="badge" style="font-size:1em;">{{width}}</span> x <span class="badge" style="font-size:1em;">{{height}}</span>
    ```
    * compléter le contenu en créant les propriétés additionnelle _width_ et _height_ de type _texte_
    * lier la propriété _Spécifiques > width_ créée à la propriété _Largeur_ du même acteur
    * lier la propriété _Spécifiques > height_ créée à la propriété _Hauteur_ du même acteur
    * modifier la propriété _Position > Align. vertical_ en ```Centré```
    * modifier la propriété _Position > Align. horizontal_ en ```Centré```
    * lier la propriété _Gabarit > Hauteur_ à la propriété _Valeur_ de l'acteur ```textboxHeight```
    * lier la propriété _Gabarit > Largeur_ à la propriété _Valeur_ de l'acteur ```textboxWidth```
    * modifier la propriété _Aspect > Couleur_ en ```#ffffff```
    * modifier la propriété _Aspect > Couleur de fond_ en ```#4b0082```
    * définir la propriété _Aspect > Bordure > Style bordure_ en ```Pointillé```
    * définir la propriété _Aspect > Bordure > Epaisseur bordure_ en ```10px```
    * définir la propriété _Aspect > Bordure > Couleur bordure_ en ```#ff0000```

10. **Vérifier** la zone de prévisualisation

    ![props_invalid](assets/preview.png)

11. **Déployer** et **éxécuter**

La SynApp est terminée ! nous allons tester l'effet des différentes tailles sur l'acteur _texte_ du centre

## Test du comportement des tailles

Nous allons simuler le rendu sur un petit écran pour mieux comprendre l'influence des tailles sur le rendu de l'acteur central

1. En mode éxécution, **appuyer** sur F12 pour ouvrir les DevTools (outils développeurs) de Chrome

2. **Cliquer** sur l'icone permettant de choisir un type de _device_ de rendu

    ![props_invalid](assets/devtools.png)

3. **Sélectionner** le _device_ que vous souhaitez dans la fenêtre principale du navigateur. Par exemple _iPhone 6/7/8_

    ![props_invalid](assets/execute.png)

    _Remarque:_ si vous le souhaitez, cliquer sur les 3 points verticaux en haut à droite puis sélectionnez **Show device frame** pour faire apparaitre le téléphone

## Taille en pixel

La taille en pixel est la plus simple à appréhender et permet définir une taille fixe. Nous recommandons d'éviter ce type de taille excepté dans quelques cas:

* Scène de type synoptique avec fond de plan dans une disposition _toile_, pour rappel [tutorial 3 sur l'acteur de disposition **toile**](../tuto03/part2.md). Tous les acteurs de la scène doivent être défnis en valeur absolu en pixels. L'adaptabilité du synoptique pourra alors être apporté par l'acteur boite à vue, pour rappel [tutorial 3 sur l'acteur de disposition **boite à vue**](../tuto03/part3.md)

* Acteur enfant dont la taille doit absolument rester fixe. Par exemple: un logo qui doit avoir un aspect fixe

* SynApp réalisé pour un écran d'accueil à la résolution précise

De manière générale, l'acteur principal d'une scène ne doit jamais être défini avec une taille fixe

1. **Créér** une nouvelle 

