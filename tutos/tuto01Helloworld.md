# Une première SynApp déployée *Helloworld*

## Prerequis

[Installation](/install.md)

## Création de la SynApp

### Sélection de l'UTL

1. Ouvrez le Maker

![RedyProPC](/assets/tuto01device.PNG)

2. Entrez l'adresse de l'UTL (Redy ou Redy Pro PC)

Exemples:
* http://127.0.0.1
* http://localhost:8080
* redy.domain.com
* https://redy.domain.org

Dans le cas ou l'UTL est installée localement sur le port 80: http://127.0.0.1

3. Connection sur l'UTL

Saisir les identifiants de connection du Redy identiques à ceux de l'application d'exploitation

### Création de la SynApp

Saisir les informations de création dans le formulaire de la SynApp:
![Création SynApp](/assets/tuto01new.PNG)

### Ouverture du Maker

L'environnement du Maker ainsi que tous les concepts seront décrits ultérieurement. Pour l'instant nous allons juste ajouter 3 acteurs dans la *scene1*:

1. Cliquer sur  [+] dans l'onglet acteur en bas à gauche de l'éditeur 

![Ajout acteur empilement](/assets/tuto01actorStack.PNG)

2. Dans l'explorateur d'acteur sélectionner le premier *Empilement*

Cet acteur va permettre de disposer des acteurs enfants dans la scène courante qui vont s'empiler verticalement.

![Visu acteur empilement](/assets/tuto01actorStack2.PNG)

3. L'acteur *stack1* étant sélectionné, cliquer de nouveau sur [+] pour ajouter un premier acteur enfant de type *Affichage* > *Texte*

![Ajout acteur texte](/assets/tuto01actorText.PNG)

4. Modifier l'acteur texte *text2* pour augmenter la taille du texte à 100 pixels: l'acteur *text2* étant sélectionné, éditer la propriété *Aspect* > *Taille* avec *100px* dans la zone à droite de l'éditeur appélé l'inspecteur d'objets SynApps.

![Modification taille texte](/assets/tuto01actorTextFontSize.PNG)

5. Dans la zone central de prévisualisation, double cliquer sur *text2* et saisissez "Hello world"

6. Sélectionner l'acteur *stack1*, cliquer de nouveau sur [+] pour ajouter un deuxième acteur enfant de type *Charts* > *Jauge*

7. Modifier l'acteur jauge *gauge3* pour qu'il prenne tout l'espace vertical: l'acteur *gauge3* étant sélectionné, éditer les propriétés *Position* > *Alignement vertical* et *Alignement horizontal* avec *Etendre*

![Modification position jauge](/assets/tuto01actorGaugePosition.PNG)

La zone de prévisualisation finale doit ressembler à cela ! (sinon recommencer :-)
![Prévisualisation](/assets/tuto01preview.PNG)

### Déploiement de la SynApp

Déployer la SynApp sur le Redy en cliquant *Déployer* dans la barre de commande en haut à droite 

![Déployer](/assets/tuto01deploy.PNG)

La SynApp est déployée sur le Redy dans *:easy.SynApps*

[En savoir plus sur les objets crées dans le Redy](/exploreRedy.md)

**Attention**: le paramétrage de l'UTL dévra être sauvegardé sinon, en cas de redémarrage, votre SynApp ne sera pas conservée

### Exécution de la SynApp

Exécuter la SynApp en cliquant *Exécuter* dans la barre de commande, soit:

* *Executer* principal: la SynApp est éxécuté dans le navigateur courant

![Exécuter](/assets/tuto01execute.PNG)

* *Executer* secondaire: la SynApp est éxécuté dans un nouveau navigateur

![RedyExécuter dans nouvelle fenêtre](/assets/tuto01executeOutside.PNG)

Ce mode est a priviliégier pour faire cohabiter le mode *exécution* et *edition* sur 2 écrans différents par exemple. Dans ce cas, à chaque déploiement, le mode *exécution* est rafraichi

## Etapes suivantes

Vous avez construit puis déployé sur un Redy une première SynApp !

Avant de continuer, revenez dans l'edition de la SynApp et parcourez tous les propriétés des 3 acteurs. Regardez notamment les propriétés *spécifiques*, essayez de modifier des propriétés, la couleur de fond par exemple, pour observer leurs effets dans la zone de prévisualisation.

Ensuite, vous pouvez:
1. créer une SynApp connectée à des ressources du Redy: [Tutorial 2: liaisons aux ressources de l'UTL](tuto02BindingSources.md)
2. consulter la [description des concepts de SynApp](/concepts/index.md)
3. consulter la [description du designer de SynApp](/designer.md)
4. consulter la [documentation des acteurs](/actors/index.md)