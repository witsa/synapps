[Accueil](../../) / [Tutoriaux](../index.md) / [Tutorial 02](index.md)

# Tutorial 2: les liaisons **6/6** *[10 nov 17]*

## Liaisons **librairies**

Dans les parties [précédentes](part5.md) du tutoriel, les acteurs ont été:

* disposés dans une scène
* liés en **interne** à d'autres acteurs
* liés à des **sources de données** en *lecture* et *écriture*

Pour cette dernière partie, nous adressons le concept des **librairies** qui permettent de centraliser des données simplement et ainsi favoriser leurs ré-utilisabilité dans les propriétés d'acteurs

### Les librairies

Les librairies sont classifiées en trois **catégories**:

* **Couleurs**: librairie de *couleurs*
* **Images**: librairie d'*images*
* **Contenu**: librairie d'autre types de contenu: *texte*, *javascript*, *json*, etc

![Paramètres de la ressource](/assets/part6_1.png)

Tout élément d'une librairie est stocké dans le REDY dans un **nod dédié** qui peut donc être simplement modifié côté UTL manuellement, avec du e@sy-script, etc
![Paramètres de la ressource](/assets/part6_2.png)

Cela implique également qu'une méthode simple pour venir éditer un élément de configuration de SynApps depuis le REDY est de sortir ce contenu de l'acteur dans une *librairie*: _texte_, _couleur_, _valeur numérique_, _etc_

[En savoir plus sur les objets crées dans le REDY](../../redy/explore.md)

*Exemple:* dans la copie d'écran ci-dessus, il suffit de modifier la valeur du label *color1* pour changer la couleur des acteurs qui sont liés à cet élément de librairie

*Remarque:* les librairies ne sont chargées qu'à l'initialisation de la SynApp

#### Cas particulier de la librairie Image

Point important concernant les **images**. Le mécanisme de chargement des images dans SynApps est plus **optimisé** lorsqu'elles sont définies dans des **librairies** car elles profitent des fonctionnalités de **cache de navigateurs**

_A retenir:_ définir **systématiquement** les images dans des librairies sauf pour les trés petites images (en taille) qui ne présentent pas d'intérêt de ré-utilisabilité

### Création des liaisons **librairies**

La couleur de premier plan de l'acteur *gaugeAnalogic* est actuellement définie manuellement. Nous allons la publier dans la *librairie couleur* et créer la liaison avec la propriété *Couleur de premier plan* de l'acteur

1. L'acteur *gaugeAnalogic* étant sélectionné, éditer la liaison de la propriété *Spécifiques.Couleur de fond* et sélectionner **Librairie**

    ![Edition source de données](/assets/part6_3.png)
    La modale d'édition des liaisons vers les librairie s'ouvre

2. Description de l'éditeur de liaison des libraries

    ![Description liaison  interne](/assets/part6_4.png)
    L'éditeur de liaison de *source de données* est composé de trois parties principales:

    * **Sélecteur de librairie éxistante**: sélectionner un type et lier la propriété de l'acteur à une librairie éxistante

    * **Création de nouvelle librairie**: créer un nouvel élément de librairie avec la valeur actuelle de la propriété de l'acteur et lier la propriété de l'acteur

    * **Récapitulatif de la liaison**: vérifier la description et cliquer sur **[Lier]** en bas à droite

    Consulter [description du MAKER](../../designer.md) pour en savoir plus concernant l'éditeur de liaison *source de donnée*

3. Dans *Types*, sélectionner *Couleurs*, sélectionner **color1** dans *Nouvel élément*. Changer le *label* pour **colorGauge** puis **[lier]** en bas à droite

    ![Résumé liaison librairie](/assets/part6_5.png)

4. La propriété *Couleur premier plan* de *gaugeAnalogic* est désormais liée à la librairie *colorGauge*, vous remarquez:
    * qu'elle **n'est plus modifiable manuellement car liée**
    * le bouton d'édition de la liaison est de couleur **vert** pour indiquer une liaison *librairie*
    * un **tooltip résumant la liaison** apparaît en déplaçant le curseur de la souris sur le bouton d'édition de la liaison
    ![Tooltip liaison librairie](/assets/part6_6.png)

### Verification des liaisons **librairies**

1. Vérifier la liaison en modifiant la couleur de la librairie *colorGauge* avec une autre couleur

    ![Sélection de la librairie](/assets/part6_7.png)
    ![Modification de la librairie](/assets/part6_8.png)

2. Revenir sur la scène *scene1* et observer que la couleur est bien appliquée sur les acteurs

3. Modifier également la couleur dans la **configuration du REDY** avec la valeur **red** en utilisant l'explorateur de nod sur

    ```TEXT
    :easy.SynApps.Tuto02.Libraries.Color
    ```
    ![Explorateur de nod](/assets/part6_9.png)

4. Modifier le numéro de _build_ de la SynApp pour forcer son rechargement

    ```:easy.SynApps.Tuto02.Build```

    ![Build](/assets/build.png)
    _Remarque:_ La configuration SynApp est cachée dans le navigateur pour optimiser son temps de chargement. Le numéro de _build_ de la SynApp cachée est comparé à celui stocké sur le REDY. Lorsqu'ils different, la SynApp est rechargée puis cachée dans le navigateur.

    A chaque fois que vous modifiez une SynApp depuis le MAKER, le numéro de build change automatiquement. Par contre, si vous **modifiez une des ressources de SynApp directement depuis le REDY**, avec l'explorateur de Nod par exemple, il faut **manuellement modifier le numéro de _build_** pour forcer le rafraîchissement de la SynApp dans les MAKER et RUNTIME

5. Revenir sur la scène *scene1* de SynApps, rafraîchir (F5) et observer que la couleur est bien appliquée sur les acteurs

    ![Explorateur de nod](/assets/part6_10.png)

## Conclusion

Le tutorial 2 est **terminé** ! la SynApp créée est simple mais a permis d'appréhender un des concepts importants de SynApps, les **liaisons**

Sans attendre les prochains tutoriaux, vous pouvez:

* parcourir le MAKER,
* essayer d'autres acteurs

Vous pouvez remonter les **bugs** & **remarques** concernant ce tutorial, SynApps RUNTIME & MAKER sur [GitHub](https://github.com/witsa/synapps/issues)

[Tutoriel suivant sur les acteurs _disposition_](../tuto03/index.md)
