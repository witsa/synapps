---
title: "omposite avec son propre fournisseur relatif"
parent: Tutoriels
---

Ce tutoriel présente une scène qui inclue un [fournisseur de ressource](../concepts/actor-types/redy-resource-source.md) et un composite comportant le titre d'une ressource récupérée via un [fournisseur de variable relative](../concepts/actor-types/redy-wos-relative-variable-source.md).

Pour ce tutoriel, la scène comprend un fournisseur de ressource et le composite un fournisseur de variable relative qui se base sur le fournisseur de ressource de la scène.

Cela permet à des composites de bénéficier dynamiquement de fournisseur parents à l'aide du [contexte de donnée](../concepts/context.md).<br>

# Étape 1 : Le composite

Le composite contient un acteur texte qui présente le titre de la ressource ainsi qu'un acteur fournisseur de variable relative qui sert à alimenter le contenu de mon acteur texte.

![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite9.PNG)<br>
<br>
L'acteur fournisseur de variable relative ne possède pas de clé parent (nous verrons pourquoi à l'étape 4), il possède cependant un chemin relatif et un champ.<br>
Dans notre cas, nous souhaitons simplement afficher le titre de la ressource.<br>
Le chemin relatif est donc *Title* et le champ *Valeur*.<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite2.PNG)

# Étape 2 : La liaison à l'acteur texte

Pour récupérer le titre de la ressource, il faut effectuer une liaison sur le contenu de l'acteur texte vers le fournisseur de variable relative.<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/link-text.gif)<br>

# Étape 3 : La scène

La scène présente un acteur fournisseur de ressource ainsi qu'une instance du composite que nous avons créé précédemment.<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite8.PNG)<br>

Le fournisseur de ressource de la scène va chercher une ressource présente sur le REDY peut importe la ressource.<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite3.PNG)<br>

Cette scène présente donc un acteur fournisseur de ressource ainsi qu'un composite.

# Étape 4 : La liaison du contexte

Comme expliqué en <b>Étape 1</b>, la clé parent du fournisseur de variable relative a été laissée vide et cela pour permettre de renseigner dynamiquement un acteur parent.<br>
Pour se faire, nous allons utiliser le contexte de donnée du composite.<br>
En effet, lorsque qu'un fournisseur de variable relative ne possède pas de clé parent, celui-ci va automatiquement chercher un acteur fournisseur de ressource / variable.

Dans notre exemple, il suffit donc de lier le contexte de donnée du composite à l'acteur fournisseur dans la scène.<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/link-context.gif)<br>

A l'issue de cette étape, vous nous avons :

- la liste des acteurs de la scène :<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite4.PNG)<br>
> Notons la liaison sur l'acteur 'composite-relative' qui traduit la liaison vers l'acteur 'resource' sur le contexte de donnée.

- la liste des acteurs du composite :<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite1.PNG)<br>
> Notons la liaison sur l'acteur 'my-text' qui représente la liaison pour aller chercher le titre de la ressource.

# Conclusion

Nous avons appris à fournir un acteur fournisseur de ressource à un composite via son contexte de donnée.<br>
Cela permet donc d'alléger les scènes et de factoriser l'utilisation des fournisseurs relatifs au sein des composites.

> 📌 **REMARQUE**<br>
Il est tout à fait possible, d'agir sur la variable récupérée tout comme si le fournisseur de variable relative était dans la scène ( écriture, tranformation, etc...).

# Scène et composite du tutoriel

Vous pouvez copier/coller le composite réalisé dans ce tutoriel.

>{% raw %}
>``` text
>SYNAPPS-STUDIO-COMPOSITE|{"config":{"key":"composite-relative","name":"Composite fournisseur relatif"},"leadActor":{"type":"layout/stack","key":"stack-root-composite","children":[{"type":"redy/data-source/wos-relative-variable","key":"wos-relative-variable","properties":{"dataReadMode":"always","relativePath":"Title","fieldName":"value"}},{"type":"display/text","key":"my-text","properties":{"horizontalAlignment":"middle","content":"MON TEXTE"},"bindings":{"properties.content":"actor#wos-relative-variable@data"}}]}}
>```
>{% endraw %}

Vous pouvez copier/coller la scène réalisée dans ce tutoriel.

>{% raw %}
>``` text
>SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene1","name":"Scène 1"},"leadActor":{"type":"layout/stack","key":"stack_root","properties":{"verticalAlignment":"expand"},"children":[{"type":"redy/data-source/resource","key":"resource","properties":{"path":":easy.RESS.OwnerPLUG.PLUG01.DI1"}},{"type":"composite/composite-relative","key":"composite-relative","bindings":{"dataContext":"actor#resource"}}]}}
>```
>{% endraw %}