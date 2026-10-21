---
title: "Composite avec son propre fournisseur relatif"
parent: Tutoriels
---

Nous verrons au cours de ce tutoriel comment fournir un acteur fournisseur de ressource à un acteur fournisseur relatif de variable contenu dans un composite à l'aide du [contexte de donnée](../concepts/context.md).<br>
Il est à noter que l'utilisation du contexte de donnée n'est qu'une des méthodes possibles pour parvenir à renseigner dynamiquement le parent d'un acteur fournisseur relatif de variable.

Les acteurs fournisseurs de variables relatives peuvent de cette façon être regroupés afin de rassembler les différentes requêtes.<br>
Cette pratique permet également de renseigner à l'acteur fournisseur relatif de variable une clé parent dynamiquement.

Dans ce tutoriel, nous afficherons une scène qui comporte un composite et un acteur fournisseur de ressource.<br>
Le composite utilise via son contexte de donnée l'acteur fournisseur de ressource de la scène afin d'alimenter ses propres fournisseurs de variables relatives.

# Étape 1 : Le composite

Ci-dessous le composite fonctionnel utilisé pour ce tutoriel, plus de détails sur la création de celui-ci se trouvent dans la section *Détails du composite* ci-dessous.

>{% raw %}
>``` text
>SYNAPPS-STUDIO-COMPOSITE|{"config":{"key":"composite-relative","name":"Composite fournisseur relatif"},"leadActor":{"type":"layout/stack","key":"stack-root-composite","children":[{"type":"redy/data-source/wos-relative-variable","key":"wos-relative-variable-title","properties":{"dataReadMode":"always","relativePath":"Title","fieldName":"value"}},{"type":"display/text","key":"my-first-text","properties":{"horizontalAlignment":"middle","content":"MON TEXTE"},"bindings":{"properties.content":"actor#wos-relative-variable-title@data"}},{"type":"redy/data-source/wos-relative-variable","key":"wos-relative-variable-class","properties":{"dataReadMode":"always","relativePath":"PTClass","fieldName":"value"}},{"type":"display/text","key":"my-second-text","properties":{"horizontalAlignment":"middle","content":"MON TEXTE"},"bindings":{"properties.content":"actor#wos-relative-variable-class@data"}}]}}
>```
>{% endraw %}
<br>

## Details du composite

Le composite utilisé contient deux acteurs fournisseurs de variable relative et deux acteurs textes.<br>

![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite1.png)<br>

### <b> Details des acteurs fournisseurs de variable relative </b>

Les deux acteurs fournisseurs de variables relatives ne possèdent pas de clé parent, nous allons utiliser le contexte de donnée afin de leur fournir un parent.
Ceux-ci possèdent cependant un chemin relatif et un champ.
<br>
{: .info }
>Le contexte de donnée peut être utilisé en ruissellement, nous pouvons ainsi fournir à l'instance du composite un acteur fournisseur de ressource et celui-ci ruissellera cet acteur vers tous ses enfants.<br><br>
>Dans notre cas, les acteurs fournisseurs de variables relatives détecteront automatiquement la présence d'un acteur fournisseur de ressource dans leurs contextes de donnée et l'utiliseront comme parent.


>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite6.png)<br>
>Fournisseur relatif de variable chargé de récupérer le titre de la ressource

>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite5.png)<br>
>Fournisseur relatif de variable chargé de récupérer la classe de la ressource

### <b>Details de l'acteur texte</b>

>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite10.png)<br>
>Exemple de l'une des liaisons d'un acteur texte

La seule particularité des acteurs textes de ce composite réside dans la liaison de leurs contenus vers la donnée de l'un des acteurs fournisseurs de variables relatives, ce qui permet de récupérer la variable souhaitée dynamiquement.

# Étape 2 : La scène

La scène présente un acteur fournisseur de ressource ainsi qu'une instance du composite que nous avons créé précédemment.<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite8.png)<br>

Le fournisseur de ressource de la scène va chercher une des ressources présente sur le REDY.<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite3.png)<br>

Via son contexte de donnée, le composite va renseigner l'acteur fournisseur de ressource à ses acteurs relatifs comme vu dans les détails de l'étape 1.

>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/link-context.gif)<br>
>Liaison du contexte de donnée.

A l'issue de cette étape, notre scène devrait afficher le titre et la classe de la ressource récupérée par notre fournisseur de ressource.<br>
>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite11.png)<br>
> Exemple d'une scène affichant le titre et la classe d'une ressource.

# Conclusion

A l'issue de ce tutoriel, nous devrions avoir :

- Une scène composée d'un acteur fournisseur de ressource et d'un composite :<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite4.png)<br>

- Un composite composé de deux acteurs fournisseurs de variables relatives et de deux acteurs textes :<br>
![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite1.png)<br>

Au cours de ce tutoriel, nous avons appris à fournir à un composite un certain contexte de donnée et à valoriser ce contexte de donnée pour l'utilisation d'acteurs fournisseurs de variables relatives.<br>

{: .info }
> Il est tout à fait possible, d'agir sur la variable récupérée par le fournisseur relatif de variable (écriture, transformation, etc ...) .

# Scène et composite du tutoriel

Vous pouvez copier/coller le composite réalisé dans ce tutoriel.

>{% raw %}
>``` text
>SYNAPPS-STUDIO-COMPOSITE|{"config":{"key":"composite-relative","name":"Composite fournisseur relatif"},"leadActor":{"type":"layout/stack","key":"stack-root-composite","children":[{"type":"redy/data-source/wos-relative-variable","key":"wos-relative-variable-title","properties":{"dataReadMode":"always","relativePath":"Title","fieldName":"value"}},{"type":"display/text","key":"my-first-text","properties":{"horizontalAlignment":"middle","content":"MON TEXTE"},"bindings":{"properties.content":"actor#wos-relative-variable-title@data"}},{"type":"redy/data-source/wos-relative-variable","key":"wos-relative-variable-class","properties":{"dataReadMode":"always","relativePath":"PTClass","fieldName":"value"}},{"type":"display/text","key":"my-second-text","properties":{"horizontalAlignment":"middle","content":"MON TEXTE"},"bindings":{"properties.content":"actor#wos-relative-variable-class@data"}}]}}
>```
>{% endraw %}

Vous pouvez copier/coller la scène réalisée dans ce tutoriel.

>{% raw %}
>``` text
>SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene1","name":"Scène 1"},"leadActor":{"type":"layout/stack","key":"stack_root","properties":{"verticalAlignment":"expand"},"children":[{"type":"redy/data-source/resource","key":"resource"},{"type":"composite/composite-relative","key":"composite-relative","bindings":{"dataContext":"actor#resource"}}]}}
>```
>{% endraw %}
