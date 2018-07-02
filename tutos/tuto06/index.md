# Tutorial 6: les événements et fonctions javascripts - **<span style='color:red'>Expert</span>**


[Home](../../sitemap.md) > [Tutoriaux](../index.md) > [Tutorial](index.md)

SynApps est conçu pour construire des applications avec le minimum de connaissances en développement et un rendu adapté est possible sans saisir une seule ligne de javascript. Cependant, comme nous allons le voir, il est parfois nécessaire d'écrire du code pour des usages plus avancés

Dans les précédents tutoriaux, nous avons déja utilisé quelques instructions javascripts pour définir des **fonctions de transformations** en lecture sur des liaisons et ainsi adapter un type de valeur source à un type attendu par l'acteur. Exemple: une valeur booléenne ```true``` ou ```false``` vers une chaine de caractère

Nous reviendrons dans ce tutorial sur les fonctions de transformation en lecture et en écriture de liaison, mais au préalable nous allons mettre en oeuvre les **Evénements**. Dans l'inspecteur d'acteur, nous avons largemment manipulé les **Propriétés** mais, vous l'avez peut-être aperçu, un autre onglet permet de définir des evénements

![inspector_events](assets/inspector_events.png)

Ces événements sont générés dans 2 circonstances liées soit:

1. au **cycle de vie** de l'acteur. Exemple: _Initialisation_, _Rendu_, _Destruction_
2. une **intéraction** de l'utilisateur: _Click_, _Entrée souris_

Tout comme les propriétés, les événements peuvent être classés dans 2 catégories:

1. **Commun** à tous les acteurs

    Exemple: _Entrée souris_ est généré quand une l'utilisateur entre en survol souris sur un acteur

2. **Spécifiques** à un acteur

    Exemple: _Sélection d'une ressource_ est généré quand une ressource est sélectionnée par l'utilisateur dans un acteur _Etat_

Par défaut la définition de ces événements est vide, cad qu'aucune action n'est effectuée. Mais il est possible de définir une **action spécifique** avec un éditeur de javascript qui donne accès à l'ensembles des **objets de SynApps**: acteurs, scène, etc, pour les **lire** mais aussi pour les **modifier** !

Nous verrons qu'il est également possible de **débugger** au pas à pas ces fonctions pour résoudre un comportement inattendu par exemple

La maitrise de la définition des événements est un élément important de toute SynApps afin d'effectuer des actions avancées non, ou pas encore, configurables dans l'éditeur SynApps MAKER !

## Prerequis

* Le paramétrage [SynApps_Tutorials.BK4](../config/SynApps_Tutorials.BK4) installé sur le REDY. Il contient les profils utilisateurs, _Administrateur_ et _Installateur_ utilisés dans ce tutorial

* Créer une nouvelle SynApp **tuto06** avec le _MAKER_. Modifier le _label_ de la première scène en ```sceneEvents``` et le _nom_ avec ```scène événements``` puis déployer

## Construction de l'ossature de la **scène événements**

Nous allons construire une scène qui contiendra plusieurs acteurs qui vont générer des événements. Ces derniers seront loggés dans une console de sortie

_Remarque:_ la définition des labels des acteurs est d'autant plus importante avec les événements car ils sont largemment utilisés dans les scripts pour notamment identifier des acteurs

1. **Définir** l'acteur principal avec un acteur _Empilement_

    * renommer le _Label_ avec ```stackRoot```
    * modifier la propriété _Spécifiques > Orientation_ en ```Horizontal```

2. **Ajouter** un acteur enfant de type **_Empilement_** qui contiendra les acteurs qui vont générer des événements

    * renommer le _Label_ avec ```stackEvents```
    * réinitialiser la propriété _Gabarit > Largeur_ avec la taille ```[vide]```
    * définir la propriété _Position > Align. vertical_ en ```Etendre```
    * définir la propriété _Position > Align. horizontal_ en ```Etendre```
    * définir la propriété _Aspect > Police > Taille_ avec la taille ```50px```

3. **Ajouter** un acteur enfant de type **_texte_** qui sera le premier acteur à générer des événements

    * renommer le _Label_ avec ```textActorA```
    * modifier la propriété _Spécifiques > Contenu_ avec le texte ```Acteur A```
    * modifier la propriété _Aspect > Couleur de fond_ avec la couleur ```#009fe3```
    * modifier la propriété _Aspect > Couleur_ avec la couleur ```#ffffff```
    * modifier les 2 propriétés _Position > Align. vertical_, _Position > Align. horizontal_ en ```Centré```
    * modifier les 4 propriétés _Gabarit > Marge int. gauche_, _Marge int. droit_, _Marge int. haut_, _Marge int. bas_ avec la taille ```50px```

4. **Sélectionner** l'acteur ```stackRoot``` et **ajouter** un acteur enfant de type _Zone de texte_ (dans la catégorie **Intéractions** de l'_explorateur d'acteurs_) qui jouera le rôle de console de sortie des événements

    * renommer le _Label_ avec ```textareaOutput```
    * réinitialiser la propriété _Spécifiques > Valeur_ avec le texte ```[Vide]```
    * définir la propriété _Spécifiques > Texte d'aide_ avec le texte ```Console des événements```
    * définir la propriété _Aspect > Couleur de fond_ avec la couleur ```#d6d6d6```
    * définir la propriété _Aspect > Police > Style_ avec la sélection ```Italic```
    * définir la propriété _Aspect > Police > Taille_ avec la taille ```30px```
    * définir la propriété _Gabarit > Largeur_ avec la taille ```50%```
    * modifier les 4 propriétés _Gabarit > Marge int. gauche_, _Marge int. droit_, _Marge int. haut_, _Marge int. bas_ avec la taille ```50px```

5. **Vérifier** la _liste des acteurs_ ainsi que la _zone de prévisualisation_

    ![actors_list](assets/actors_list.png)
    ![preview](assets/preview.png)

## Implémentation et log d'un événement dans la console

Nous allons définir un premier événement _click_ sur l'acteur A et le logger dans la console

1. **Sélectionner** l'acteur ```textActorA```

    * cliquer dans l'onglet _Evénements_ de l'_inspecteur d'acteur_
    * cliquer sur _commun_ pour ouvrir la liste des événemnts
    ![preview](assets/inspector_events2.png)
    * éditer l'événement _Ev. "Click souris"_
    ![preview](assets/inspector_event_click.png)
    * copier la fonction javascript suivante dans la _zone d'édition_. Elle sera expliquée ci-après
    ```javascript
    var evtName = "Click souris";
    var textareaOutput = context.synoStage.findByLabel('textareaOutput');
    var currentOutput = textareaOutput.get('value');
    var newOutput = context.target.get('content') + ' > '+ evtName + "\n" + currentOutput;
    textareaOutput.set("value", newOutput);
    ```
    ![event_click](assets/event_click.png)

    * sauvegarder la fonction et fermer l'éditeur d'événement
    ![editor_close](assets/editor_close.png)

2. **Déployer**, **éxécuter** et **cliquer** sur _Acteur A_, la console log l'événement

    ![execute](assets/execute.png)

3. **Revenir** sur le MAKER et ouvrir l'événement _Ev. "Click souris"_ défini précédemment

    * une **zone d'aide** est affichée droite de la fenêtre et donne les **mots-clefs** permettant de récuperer et modifier les objets de la SynApp, acteurs, scènes, etc dans le contexte courant

        ![help](assets/help.png)

    * ligne 2

        ```javascript
        var textareaOutput = context.synoStage.findByLabel('textareaOutput');
        ```
        L'instruction _contexte.synotage_ retourne la scène courante ```sceneEvents``` de l'acteur à l'origine de l'événement

        La fonction _findByLabel(...)_ retourne l'acteur avec le label ```textareaOutput``` dans la scène

        la variable _textareaOutput_ contient donc l'acteur du même nom

    * ligne 3

        ```javascript
        var output = textareaOutput.get('value');
        ```
        La fonction _get(...)_ retourne la valeur de la propriété ```value``` de l'acteur ```textareaOutput```

        _Remarque:_ la propriété ```value``` correspond à la propriété _Spécifiques > Valeur_ dans l'_inspecteur d'acteur_. En effet, toutes les propriétés ont un nom **intelligible** pour l'utilisateur du MAKER et un nom **interne** (en anglais) utilisé dans les scripts. Pour connaître le nom interne d'une propriété, il suffit de survoler le bouton de liaison de la propriété comme ci-dessous

        ![property_name](assets/property_name.png)

    * ligne 4

        ```javascript
        var newOutput = context.target.get('content') + ' > '+ evtName + "\n" + currentOutput;
        ```

        L'instruction _context.target_ retourne l'acteur à l'origine de l'événement ```textActorA```

        La fonction _get('content')_ retourne la valeur de la propriété ```Contenu``` de l'acteur ```textActorA```, soit ```Actor A```

        ![property_name2](assets/property_name2.png)

        _"\n"_ effectue un retour à la ligne

    * ligne 5

        ```javascript
        textareaOutput.set("value", newOutput);
        ```

        La fonction _set(...)_ modifie la valeur de la propriété ```value``` de l'acteur ```textareaOutput``` qui prend la valeur de _newOutput_, soit ```Actor A > Click souris\n...```

## Généralisation du log sur autres événements et acteurs

Nous souhaitons mettre en place le même mécanisme que précédemment mais généralisé à tous les acteurs. Nous pourrions dupliquer le code ci-dessus en modifiant le nom de l'événement dans la ligne 1

```javascript
var evtName = "XXXX"; // Remplacer XXXX par le nom de l'événement
```

Mais cela n'est pas vraiment maintenable: la moindre modification devrait être reproduite sur toutes les implémentations des événements

L'objectif est donc de déclarer une fonction _log(...)_ dans l'acteur ```textareaOutput``` et appeler cette fonction depuis tous les événements de l'acteur ```textActorA```. Cette fonction prendra 2 paramêtres:

* _actor_: l'acteur à l'origine de l'événement
* _evtName_: le nom de l'événement

_A savoir:_ les **fonctions doivent être déclarées** dans l'événement _initialisation_ qui est le **premier** événement à s'éxécuter dans le cycle de vie de l'acteur

1. **Sélectionner** l'acteur ```textareaOutput``` pour déclarer la fonction _log(...)_

    * Editer l'événement _Commun > Ev. "initialisation"_

        ![event_init](assets/event_init.png)

    * copier la fonction javascript suivante dans la _zone d'édition_
    ```javascript
    context.target.log = function (actor, evtName) {
        var textareaOutput = context.target;
        var currentOutput = textareaOutput.get('value');
        var newOutput = actor.get('label') + ' > '+ evtName + "\n" + currentOutput;
        textareaOutput.set("value", newOutput);
    }
    ```

    * ligne 1

        ```javascript
        context.target.log = function (actor, evtName) {
            ...
        }
        ```

        L'instruction _context.target.log = function ..._ permet de définir une fonction _log(...)_ qui est définie sur l'acteur courant, _context.target_, ```textareaOutput```

        La fonction a été adaptée par rapport à la définition précédente et prend en paramêtre _actor_ et _evtName_ respectivement l'acteur à l'origine de l'événement et le nom de l'événement

2. **Sélectionner** l'acteur ```textActorA``` pour modifier l'événement _Clic souris_ et appeler la fonction _log()_

    * Editer l'événement _Commun > Ev. "Click souris"_ et remplacer avec le javascript suivant

        ```javascript
        var textareaOutput = context.synoStage.findByLabel('textareaOutput');
        textareaOutput.log(context.target, "Click souris");
        ```

    * ligne 2

        ```javascript
        textareaOutput.log(context.target, "Click souris");
        ```
        La fonction _log(...)_ ,que nous avons implémenté précédemment, est appelée avec l'acteur à l'origine de l'événement _context.target_ et le nom de l'événement

3. **Déployer**, **éxécuter** et **cliquer** sur _Acteur A_, pour vérifier que la console log toujours l'événement

4. **Sélectionner** l'acteur ```textActorA``` pour implémenter les autres événements

    * copier le javascript suivant

        ```javascript
        var textareaOutput = context.synoStage.findByLabel('textareaOutput');
        textareaOutput.log(context.target, "XXX");
        ```

    * éditer l'événement _Commun > Ev. "Rendu"_ et coller le javascript copier ci-dessus en remplaçant la chaine de caractère ```XXX``` par ```Rendu```

    * reproduire l'opération ci-dessus pour les événements _Ev. "Entrée souris"_, _Ev. "Sortie souris"_, _Ev. "Clic enfoncé"_, _Ev. "Clic relaché"_

5. **Cloner** l'acteur ```textActorA```

    * renommer le _Label_ avec ```textActorB```
    * modifier la propriété _Spécifiques > Contenu_ avec le texte ```Actor B```
    * modifier la propriété _Aspect > Couleur de fond_ avec la couleur ```#9400d3```

6. **Cloner** l'acteur ```textActorB```

    * renommer le _Label_ avec ```textActorC```
    * modifier la propriété _Spécifiques > Contenu_ avec le texte ```Actor C```
    * modifier la propriété _Aspect > Couleur de fond_ avec la couleur ```#ff8000```

7. **Déployer**, **éxécuter** et **intéragir** avec les acteurs _Acteur A, B et C_, pour vérifier que la console log tous les événements implémentés: _Rendu_, _Entrée souris_, _Sortie souris_,  _Clic enfoncé_, _Clic relaché_ et _Clic souris_

    ![event_init](assets/execute2.png)

    _Remarques:_

    * l'événement _Rendu_ apparait en premier car il est éxécuté au moment du rendu des 3 acteurs sur la scène

    * l'événement _Clic enfoncé_ est généré au moment même ou l'utilisateur clique sur la souris, idem pour _Clic relaché_ au moment du relachement. Ces 2 événements sont toujours suivi de l'événement _Clic souris__. La pluspart du temps, seul ce dernier doit être implémenté

## Ajout d'un bouton de nettoyage de la console

La console de log est vite remplie des événements générés. Nous allons ajouter un bouton de nettoyage qui videra le contenu de la console

1. **Revenir** sur le MAKER et **sélectionner** l'acteur ```stackRoot```

2. **Ajouter** un acteur _Bouton poussoir_

    * renommer le _Label_ avec ```buttonPushClear```
    * modifier la propriété _Spécifiques > Contenu_ avec le HTML
    ```html
    <span class="glyphicon glyphicon-erase" aria-hidden="true"></span>
    ```
    _Remarque:_ ce code restitue une image de type gomme provenant de la librairie bootstrap

    * modifier la propriété _Spécifiques > Couleur model_ avec la sélection ```Danger```
    * modifier la propriété _Aspect > Police > Taille_ avec la taille ```50px```
    * modifier la propriété _Position > Align. vertical_ avec la position ```Haut```
    * éditer l'événement _Commun > Ev. "Clic souris"_ avec le javascript
    ```javascript
    var textareaOutput = context.synoStage.findByLabel('textareaOutput');
    textareaOutput.set('value', '');
    ```

    * ligne 2: _textareaOutput.set('value', '')_ remplace le contenu de la console de log par une chaine vide

3. **Déployer**, **éxécuter** et **vérifier** que le bouton de nettoyage est opérationnel

    ![execute3](assets/execute3.png)

## Debugging sous Chrome

Il est parfois trés utile de pouvoir débugger une fonction javascript pour résoudre un dysfonctionnement ou une erreur.
SynApp une application qui s'éxécute dans le navigateur et nous pouvons donc utiliser ses fonctionnalités avancés pour débugger le code éxécuté dans SynApp !
La plupart des navigateurs modernes possèdent des fonctions de débugging. Nous utiliserons ici **Chrome** pour les besoins de ce tutorial

1. **Exécuter** la SynApp et appuyer sur **F12** pour ouvrir la console _Developer Tools_

    _Remarque:_ dans la mesure du possible, il est préferrable d'utiliser 2 écrans: le premier pour la SynApp, le second pour la console _Developer Tools_. Configurer le _Dock side_ pour choisir le mode d'affichage

    ![tools_dock](assets/tools_dock.png)

2. **Sélectionner** l'onglet _Sources > Network_ de la console
    ![tools_sources](assets/tools_sources.png)

3. Pour info, le dossier _appria.wit.fr_ contient le RUNTIME du SynApps qui ne peut pas être exploité

4. **Ouvrir** le second dossier _synapps-scripts_. Celui-ci nous intéresse car il contient tous les événements implémenté dans la SynApp ! Ils sont classés par nom relativement explicites: _onClick_, _onInit_, _onMouseDown_, _onMouseEnter_, _onMouseLeave_, _onMouseUp_, _onRender_

    ![tools_events](assets/tools_events.png)

5. **Ouvrir**  le dossier des événements _onInit_ qui contien la fonction javascript implémenté par l'événement _Ev. "Initialisation"_ de l'acteur ```textareaOutput```

    ![tools_js](assets/tools_js.png)

    _Remarque:_ une SynApp peut avoir beaucoup de scripts définis dans plusieurs acteurs et scènes. Un formalisme est donc défini afin d'**identifier rapidement le script recherché**:

    Dans ```actor-textarea-textareaOutput-sceneEvents.js```

    * ```actor``` signifie que le script est associé à un objet de type acteur
    * ```textarea``` correspond au type _zone de texte_ de l'acteur (en anglais)
    * ```textareaOutput``` correspond au label de l'objet
    * ```sceneEvents``` correspond à la scène de l'objet

6. **Ouvrir** le dossier des événements _onClick_ qui contien les 4 fonctions javascript implémenté par l'événement _Ev. "Clic souris"_ dans la scène

    ![tools_js](assets/tools_onclick.png)

    Le **formalisme de nommage** des évènements permet d'**identifier aisemment** les 4 fonctions et les acteurs auquelles elles se rapportent

7. **Sélectionner** la fonction javascript ```actor-buttonPush-buttonPushClear-sceneEvents.js```. Son contenu s'affiche dans la zone centrale

    ![tools_fxclick](assets/tools_fxclick.png)

8. **Ajouter** un point d'arret sur la ligne 4 en cliquant sur celle-ci

    ![tools_beakpoint](assets/tools_beakpoint.png)

9. **Cliquer** sur le bouton de nettoyage de la SynApp pour éxécuter l'événement _Ev "Clic souris"_. Le code javascript est alors éxécuté jusqu'au point d'arrêt et le navigateur indique _Paused in debugger_

    ![tools_debug](assets/tools_debug.png)
    ![tools_paused](assets/tools_paused.png)

10. **Ouvrir** la console si pas encore ouverte

    ![tools_debug](assets/tools_console.png)

11. **copier** le javascript suivant dans la console + entrée

    ```javascript
    textareaOutput.get('value')
    ```
    Le contenu de la propriété _Valeur_ est alors affichée dans la console !

    ![tools_debug](assets/tools_console2.png)

    * La totalité des propriétés de l'acteur peuvent être évaluées de la même manière. Pour connaitre la couleur de fond, copier dans la console:

        ```javascript
        textareaOutput.get('backgroundColor')
        ```

    * Vous pouvez également modifier les valeurs des propriétés. Pour modifier la couleur de fond de l'acteur en jaune, copier dans la console

        ```javascript
        textareaOutput.set('backgroundColor', 'yellow')
        ```
        puis appuyer sur **F8** pour sortir du point d'arrêt, la couleur de fond a changé !

        ![tools_debug](assets/bg_yellow.png)

        _Remarque:_ la couleur d'origine configurée dans la SynApp revient après rechargement

12. **Cliquer** sur le bouton de nettoyage pour rentrer de nouveau en debug et **copier** le javascript suivant dans la console + entrée

    ```javascript
    textareaOutput.inspect()
    ```

    La fonction _inspect()_ permet de visualiser la totalité des valeurs des propriétés d'un objet de SynApps. Ici l'acteur ```textareaOutput```

    ![tools_debug](assets/tools_inspect.png)

13. **Inspecter** tous les types d'objets pour connaitre leurs propriétés

    * **host**: informations systèmes du REDY

        ```javascript
        context.host.inspect()
        ```

        ![tools_debug](assets/tools_host.png)

    * **synoStage**: scène courante

        ```javascript
        context.synoStage.inspect()
        ```

        ![tools_debug](assets/tools_synoStage.png)

    * **synapp**: synApp courante

        ```javascript
        context.synapp.inspect()
        ```

        ![tools_debug](assets/tools_synApp.png)

    * **session**: session utilisateur courant

        ```javascript
        context.session.inspect()
        ```

        ![tools_debug](assets/tools_session.png)

         _Remarque:_ l'objet _session_ contient une fonction _logOff()_ qui déconnecte l'utilisateur courant. Nous allons utiliser cette fonctionnalité dans la partie suivante pour construire un composite affichant l'utilisateur courant et un bouton de déconnection

Vous avez vu comment **débugger** les événements SynApps avec le navigateur Chrome, **afficher** et **modifier** les propriétés des objets SynApps

## Mise en pratique avec composite session utilisateur

Nous allons construire un composite affichant le nom de l'utilisateur connecté et un bouton de déconnection.

1. **Sélectionner** l'onglet _Composites_ et **créer** un nouveau composite

    * modifier le _label_ du composite en ```sessionLogger``` et le _nom_ avec ```Session utilisateur```
    * modifier la _description_ du composite en ```Affiche l'utilisateur connecté et permet la déconnexion```
    * modifier la _catégorie_ du composite avec la sélection ```Métier```
    * Récupérer l'image ci-dessous

        ![Empilement](assets/logo_logOff.png)
    * Glisser/déplacer l'image dans la zone **hachurée** de la propriété  _Logo_
    * modifier la propriété _Aspect > Police > Taille_ en ```40px```
    * modifier la propriété _Position > Align. vertical_ en ```Auto```

        ![Empilement](assets/composite_inspector.png)

2. **Définir** l'acteur principal avec un acteur _Empilement_

    * renommer le _label_ en ```stackRoot```
    * modifier la propriété _Spécifiques > Orientation_ en ```Horizontal```
    * modifier la propriété _Position > Align. vertical_ en ```Auto```

3. **Ajouter** un acteur enfant de type _html_

    * renommer le _Label_ avec ```htmlSession```
    * modifier la propriété _Spécifiques > Contenu_ en 
    ```html
    <i class="icon-user"></i> {% raw %}{{user}}{% endraw %}
    ```
    * **compléter** le contenu en créant la propriété additionnelle _user_. Vous pouvez également donner des informations additionnelles sur la propriété, comme le nom et la description, dans _Additionnelles > Gestion des propriétés additionnelles_
    * **lier** la propriété en interne à l'objet _Session > Utilisateur > Nom complet_

        ![Empilement](assets/bind_session.png)
    * modifier la propriété _Position > Align. vertical_ en ```Centré```
    * modifier la propriété _Gabarit > Marge > Marge int. droit_ en ```20px```

4. **Sélectionner** l'acteur ```stackRoot``` et **ajouter** un acteur enfant de type _Bouton poussoir_

    * renommer le _Label_ avec ```buttonLogOff```
    * modifier la propriété _Spécifiques > Contenu_ en 
    ```html
    <i class="icon-off"></i>
    ```
    * modifier la propriété _Position > Align. horizontal_ en ```Droite```
    * définir l'événement _Commun > Ev. "Clic souris"_
    ```javascript
    context.session.logOff();
    ```
    Comme nous l'avons vu précédemment, la fonction _logOff_ sur l'objet SynApp _session_ permet de **forcer la déconnection** de l'utilisateur

5. **Vérifier** le composite _Session utilisateur_ dans la _zone de prévisualisation_
    ![Empilement](assets/preview2.png)

6. **Sélectionner** la scène ```Scène événements```

7. **Sélectionner** l'acteur ```stackEvents```

8. **Ajouter** l'acteur composite créé _Session utilisateur_

    * modifier la propriété _Position > Align. horizontal_ en ```Centré```
    * réinitialiser la propriété _Gabarit > Hauteur_ à ```[Vide]```
    * définir l'événement _Commun > Ev. "Clic souris"_
    ```javascript
    var textareaOutput = context.synoStage.findByLabel('textareaOutput');
    textareaOutput.log(context.target, "Déconnection");
    ```

    _Remarque:_ ce script, identique que pour les acteurs _A_, _B_ et _C_, **log** dans la console l'événement de **déconnection**

9. **Déplacer** l'acteur _Session utilisateur_ en première position sous ```stackEvents```

    ![actors_order](assets/actors_order.png)

10. **Déployer** et **éxécuter** la SynApp

    * cliquer sur le bouton de déconnection, l'utilisateur est **déconnecté** et l'événement **Déconnection** est loggé dans la console

    ![execute4](assets/execute4.png)

    Le composite _Session utilisateur_ est opérationnel mais nous allons le faire évoluer par afficher un "toolTip" contenant le **mail** et le **niveau** de l'utilisateur connecté: _administrateur_, _installateur_, _exploitant_ connecté

11. **Revenir** dans le MAKER et sélectionner le composite _Session utilisateur_

12. **Sélectionner** l'acteur ```stackRoot``` et **ajouter** un acteur _modal_

    * renommer le _Label_ avec ```modalTooltip```
    * déselectionner la propriété _Spécifiques > Griser_
    * déselectionner la propriété _Spécifiques > Fermer sur clique en dehors_
    * sélectionner la propriété _Spécifiques > Position horizontale_ sur ```Gauche```
    * sélectionner la propriété _Spécifiques > Position verticale_ sur ```Haut```
    * définir la propriété _Spécifiques > Acteur attaché_ sur ```htmlSession```
    * sélectionner la propriété _Spécifiques > Attachement horizontale_ sur ```Gauche```
    * sélectionner la propriété _Spécifiques > Attachement verticale_ sur ```Bas```
    * lier la propriété _Aspect > Police > Taille_ à la propriété _taille_ du composite

        ![bind_size](assets/bind_size.png)
    * définir les 4 propriétés _Gabarit > Marge > Marge int. gauche_, _Marge int. droit_, _Marge int. haut_, _Marge int. bas_ avec ```50px```

    * tester le placement correcte de la modale en sélectionnant la propriété _Spécifiques > Test modale_

        ![bind_size](assets/preview3.png)

13. **Ajouter** un acteur enfant _Texte_

    * renommer le _Label_ avec ```textTooltip```
    * définir la propriété _Spécifiques > Contenu_

    ```html
    <span class="glyphicon glyphicon-lock"></span>{% raw %}{{level}}{% endraw %}<br/>{% raw %}{{mail}}{% endraw %}
    ```
    * compléter le contenu en créant les propriétés additionnelles proposées _level_ et _mail_. Vous pouvez également donner des informations additionnelles sur ces propriétés, comme les noms et descriptions, dans _Additionnelles > Gestion des propriétés additionnelles_

        ![properties](assets/properties.png)

    * lier la propriété _user_ en interne à l'objet _Session > Niveau_
    * éditer le script de lecture de la liaison
            ![properties](assets/script_transform.png)
    * définir le script de transormation en lecture suivant
         ```javascript
        var level = context.value;
        switch(level) {
            case 4:
                return "Administrateur";
            case 3:
                return "Installateur";
            case 2:
                return "Exploitant";
            case 1:
                return "Visiteur";
            default:
                return "?";
        }
        ```
        _Remarque:_ la fonction transform le niveau 1, 2, 3 ou 4 de l'utilisateur en texte explicite

    * lier la propriété _mail_ en interne à l'objet _Session > User > Mail_

    * définir le script de transormation en lecture suivant
         ```javascript
        return context.value === null ? '@ -': context.value;
        ```
        La  fonction retourne '@ -' si le mail n'est pas défini

        _Remarque:_ les fonctions de transformations ont dans leurs **contextes** une propriété supplémentaire _value_ par rapport aux événements. Dans le cas d'un **script de transformation** en:
        * **lecture**: _context.value_ correspond à la valeur de la propriété de l'objet source. ici le _mail_
        * **écriture**: _context.value_ correspond à la valeur de la propriété de l'acteur. Ici, elle n'est pas définie car on ne fait que lire la source

        ![composite_inspector2](assets/composite_inspector2.png)

14. **Sélectionner** l'acteur ```htmlSession``` pour définir les événements qui vont **afficher** et **cacher** la modale

    * définir l'événement _Ev. "Entrée souris"_ avec la fonction javascript

        ```javascript
        var modalTooltip = context.synoStage.findByLabel("modalTooltip");
        modalTooltip.set('isShown', true);
        ```
        _Remarque:_ la propriété _isShown_ est le nom interne de la propriété _Afficher_
        ![prop_isShown](assets/prop_isShown.png)

    * définir l'événement _Ev. "Sortie souris"_ avec la fonction javascript

        ```javascript
        var modalTooltip = context.synoStage.findByLabel("modalTooltip");
        modalTooltip.set('isShown', false);
        ```
        _Remarque:_ les fonctions ci-dessus sur les 2 événements _Entrée souris_ et _Sortie souris_ sont sensiblement identiques, dans un cas on défini la valeur ```true``` et dans l'autre ```false```. Nous aurions également pu définir une fonction commune _displayModal(value)_ déclarée dans l'événement _initialisation_ comme pour la fonction log() de _textareaOutput_ et l'appeler depuis les 2 fonctions

15. **Déployer** et **éxécuter** la SynApp

    * survoler le nom de l'utilisateur connecté, niveau et mail sont affichés dans le tooltip

        ![execute6](assets/execute6.png)

    * cliquer sur le bouton de déconnection et connectez-vous avec un compte installateur, _login:_ ```install``` et _mot de passe:_ ```.```

        ![execute5](assets/execute5.png)

## Que retenir

Vous avez mis en oeuvre les **événements et fonctions javascripts** qui sont un usage avancé de SynApps

Ils permettent de réaliser des actions impossibles à définir avec l'interface d'édition du MAKER. Cela nécessite quelques connaissances de fonctions javascripts, mais vous l'aurez constaté, avec quelques instructions de base, il est rapidement possible de définir des comportements évolués

Le javacript peut être défini dans deux éléments distinctes de SynApps:

* Les **événements** des acteurs
* Les scripts de **transformation** en lecture et écriture des liaisons

_Remarque:_ pour ces dernierr, lorsqu'une liaison est définie en **lecture ET écriture**, vers une source de donnée par exemple, toute fonction de **transformation en lecture** doit avoir son **équivalent en écriture**

Vous avez utilisé les **Developer Tools** du navigateur **Chrome** pour:

* **débugger** les scripts définis dans SynApps MAKER,
* placer des **points d'arrêts** et entrer en mode pas à pas
* **inspecter** et **interragir** avec des objets: session, acteur, scène, etc

Enfin, vous avez réalisé un composite métier réutilisable: gérant les sessions utilisateur. Pour cela, nous avons mis en oeuvre plusieurs types d'événements et scripts au coeur du composite. L'intégration dans la scène est alors extrêmement simple et peut même être réalisé par un utilisateur sans connaissances avancées dans SynApps notamment sur les _événements_: principe de la **boite noir** et de la **modularité** des composites !

## Conclusion

Le **tutorial 6** sur les événements et fonctions javascripts est **terminé**. Ils sont un usage avancé de SynApps mais pour construire des applications évoluées leurs maitrises devient rapidement indispensable !

Vous pouvez remonter les **bugs** & **remarques** concernant ce tutorial, SynApps RUNTIME & MAKER sur [GitHub](https://github.com/witsa/synapps/issues)

[Tutoriel suivant sur les acteurs métiers du REDY](../tuto07/index.md)