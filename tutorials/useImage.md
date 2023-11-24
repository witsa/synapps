---
title: "Les images dans synapps"
parent: Tutoriels
---

### <center> <b> LES IMAGES DANS SYNAPPS </b> </center>

### Objectif du Tutoriel :

Nous allons voir dans ce tutoriel comment vous pouvez utiliser les **images** dans Synapps.
Dans un premier temps, nous verrons comment ajouter une *image de fond* et un acteur *image*<br>

>Nous partons du principe que vous avez déjà une scene dans votre synapps et un acteur empilement.


# Etape 1 : Ajouter d'une image dans la librairie

Pour commencer, nous allons ajouter nos **images** dans la librairie. Cela permettra qu'elles soient accessibles facilement et permet d'optimiser l'affichage de celles-ci.<br>
Pour ajoutez une **image** dans la librairie suivez ce [tuto]({{ site.baseurl }}/concepts/pictures.html)<br>

>📌 **REMARQUE**<br>
 N'oubliez pas de sauvegarder votre librairie après chaque modification ou ajout d'image.<br>
 Ceci évitera toute perte d'image et garantira la disponibilité de celle-ci lors de liaisons.

# Etape 2 : Utilisation des images avec les acteurs

### <b> Image de fond </b>

>Ici nous partons du principe que vous avez déjà un acteur dans votre scene.<br>

Tout d'abord, il faut établir la liaison entre **l'acteur** et **l'image** que vous souhaitez utiliser.
Pour réaliser cela rendez-vous dans la section *Aspect* de votre acteur.
Ensuite, selectionnez l'icône d'engrenage correspondant à la caractéristique *Image de fond* et cliquez sur *Lier à ......* .<br>
Enfin, une popup apparaitra à votre droite, vous y verrez plusieurs champs à renseigner, pour le type de source sélectionnez *Image*. Puis, en cliquant sur le champs *Image*, vous aurez accès à la liste des **images** qui se trouvent dans votre librairie. Il vous suffit ensuite de sélectionnez l'**image** de votre choix.

>![SynApps]( {{site.baseurl }}/assets/tutorials/images/creat_liaison_background.gif)<br>
>Exemple de creation d'une liaison entre le fond d'un acteur text et une image dans la librairie

Comme vous pouvez voir sur le gif, vous pouvez aussi mettre une couleur de fond qui sera derriere votre image de fond.

Vous pouvez maintenant ajuster l'**image** comme bon vous semble à l'aide des caractéristiques suivant qui se trouve en dessous de *Image de fond* et dans la section secondaire *Fond*:
  - position du fond
  - taille du fond
  - répétition du fond
  - attachement du fond

>![SynApps]( {{site.baseurl }}/assets/tutorials/images/creat_liaison_background_2.gif)<br>
>Exemple d'ajustement d'une image dans la librairie
<br>

Pour finir, pour voir le resultat de votre synapps vous pouver exécuter votre synapp, pour l'exécuter suivez ce [tuto]({{ site.baseurl }}/quick-start/synapp-run.html).<br>

### <b> Acteur Image </b>

Pour commencer, la création de l'acteur **Image** se déroule dans l'*Inspecteur*. Tout d'abord vous devez faire un clic droit sur l'acteur empilement/stack et sélectionner *Ajouter un acteur* puis l'acteur **Image**.
Ensuite, il faut ajouter votre **image**, allez dans la caractéristique **Image** dans la section *Spécifiques*. Vous avez deux options: `soit` établir une liaison entre votre acteur et l'une des **images** de votre librairie, `soit` cliquez sur *Déposer ici* et sélectionner directement votre **image**.

>![SynApps]( {{ site.baseurl }}/assets/tutorials/images/creat-actor-image.gif)<br>
>Exemple de création d'un acteur image

Enfin, vous pouvez ajuster votre **image** comme il vous plait à l'aide de l'inspecteur à votre droite.

> 💡 **ASTUCE**<br>
  Vous pouvez aussi rajouter une bordure comme sur le gif, il peut faire office de cadre.<br>
  Pour comprendre comment fonctionne chaque caractéristique vous pouvez regarder cette [page]({{ site.baseurl }}/concepts/actor/).
<br>

>![SynApps]( {{ site.baseurl }}/assets/tutorials/images/Inspecteur_de_l'acteur_image.gif)<br>
>Exemple des caractéristiques que vous pouvez utliser

>📌 **REMARQUE**<br>
 N'oubliez pas de sauvegarder votre scene avant l'exécution.
<br>

Pour finir, pour voir le resultat vous pouver executer votre *synapp*, pour l'executer suivez ce [tuto]({{ site.baseurl }}/quick-start/synapp-run.html).<br>

# Conclusion

Dans ce tutoriel vous avez vu comment créer un acteur image dans votre scène mais aussi comment ajouter une image de fond à l'un de vos acteurs.
Selon les caractéristiques que vous avez choisi vous pouvez obtenir ce type de scene.

![SynApps]( {{site.baseurl }}/assets/tutorials/images/result-tuto-image.png)<br>

# Scène du tutoriel

Vous pouvez copier/coller la scène réalisée dans ce tutoriel.<br>

{% raw %}
```
SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene1","name":"Use_Image"},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"display/text","key":"text1","properties":{"verticalAlignment":"middle","horizontalAlignment":"middle","content":"Tutoriel Image","fontSize":"6vmin","color":"rgba(255, 255, 255, 1)"}},{"type":"display/image","key":"image1","properties":{"width":"50%","borderColor":"rgba(155, 109, 109, 1)","borderWidth":"10px","borderStyle":"solid","opacity":71,"horizontalAlignment":"middle"},"bindings":{"properties.content":"picture@night"}}],"properties":{"backgroundColor":"rgba(131, 100, 100, 1)","backgroundPosition":"center center","backgroundSize":"contain","backgroundRepeat":"no-repeat"},"bindings":{"properties.backgroundImage":"picture@day"}}}
```
{% endraw %}

Si vous voulez la partie sur l'image de fond<br>

{% raw %}
```
SYNAPPS-STUDIO-ACTOR|{"type":"layout/stack","key":"stack1","children":[{"type":"display/text","key":"text1","properties":{"verticalAlignment":"middle","horizontalAlignment":"middle","content":"Tutoriel Image","fontSize":"6vmin","color":"rgba(255, 255, 255, 1)"}}],"properties":{"backgroundColor":"rgba(131, 100, 100, 1)","backgroundPosition":"center center","backgroundSize":"contain","backgroundRepeat":"no-repeat"},"bindings":{"properties.backgroundImage":{"sourceType":"picture","path":"day"}}}
```
{% endraw %}

Si vous voulez la partie sur l'acteur image<br>

{% raw %}
```
SYNAPPS-STUDIO-ACTOR|{"type":"display/image","key":"image1","properties":{"width":"50%","borderColor":"rgba(155, 109, 109, 1)","borderWidth":"10px","borderStyle":"solid","opacity":71,"horizontalAlignment":"middle"},"bindings":{"properties.content":{"sourceType":"picture","path":"night"}}}
```
{% endraw %}
