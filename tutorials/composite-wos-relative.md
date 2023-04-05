---
title: "Composite avec fournisseur relatif"
parent: Tutoriels
---

>## Scène avec fournisseur de donnée et composite avec fournisseur de variable relative

Dans cet exemple, une scène comporte un acteur [fournisseur de ressource](../concepts/actor-types/redy-wos-variable-source.md) et un composite.<br>
Le composite contient un acteur [fournisseur de ressource relative](../concepts/actor-types/redy-wos-relative-variable-source.md) et un acteur texte qui affiche le nom de la ressource à l'aide d'une liaison sur l'acteur *fournisseur de ressource relative*.

La ressource est récupérée dans la scène par un acteur *fournisseur de ressource* et le sous-chemin de la ressource est récupéré par un acteur *fournisseur de variable relative* situé dans le composite.

>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite4.PNG)<br>
>Scène avec fournisseur ressource

>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite1.PNG)<br>
>Composite avec fournisseur variable relatif


Afin que l'acteur *fournisseur de ressource* soit renseigné à l'acteur *fournisseur de variable relative* du composite, il faut passer l'acteur fournisseur dans le contexte de l'instance du composite à l'aide d'une liaison.

>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite2.PNG)<br>
>Instance du composite dans la scène avec liaison du contexte

L'acteur fournisseur de ressource (situé dans la scène) doit pointer vers une ressource de l'ULI comme suit :

>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite3.PNG)<br>
>Instance du composite dans la scène avec liaison du contexte

L'acteur fournisseur de variable relative (situé dans le composite) doit avoir sa *clé parent* vide, un *chemin relatif* précis ainsi qu'eventuellement un *champ* comme suit :

>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite6.PNG)<br>
>Instance du composite dans la scène avec liaison du contexte

Enfin, l'acteur texte, situé dans le composite doit être lié avec la valeur souhaité de l'acteur *fournisseur de variable relative* comme suit :

>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite5.PNG)<br>
>Liaison de l'acteur texte sur le fournisseur de variable relative

>![SynApps]( {{ site.baseurl }}/assets/tutorials/composite-relative/tuto-composite7.PNG)<br>
>Détails de la liaison de l'acteur texte sur le fournisseur de variable relative

>La scène à coller dans Synapps-Studio :
>{% raw %}
>``` text
>SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene1","name":"Scène 1"},"leadActor":{"type":"layout/stack","key":"stack_root","properties":{"verticalAlignment":"expand"},"children":[{"type":"redy/data-source/resource","key":"resource","properties":{"path":":easy.RESS.OwnerPLUG.PLUG01.DI1"}},{"type":"composite/composite-relative","key":"composite-relative","bindings":{"dataContext":"actor#resource"}}]}}
>```
>{% endraw %}

>Le composite à coller dans Synapps-Studio :
>{% raw %}
>``` text
>SYNAPPS-STUDIO-COMPOSITE|{"config":{"key":"composite-relative","name":"Composite fournisseur relatif"},"leadActor":{"type":"layout/stack","key":"stack-root-composite","children":[{"type":"redy/data-source/wos-relative-variable","key":"wos-relative-variable","properties":{"dataReadMode":"always","relativePath":"Title","fieldName":"value"}},{"type":"display/text","key":"my-text","properties":{"verticalAlignment":"middle","horizontalAlignment":"middle"},"bindings":{"properties.content":{"relativeTo":"wos-relative-variable","relativePath":":easy.RESS.OwnerPLUG.PLUG01.DI1.Title","fieldName":"value","dataReadMode":"always","source":"redy/wos-relative-variable"}}}]}}
>```
>{% endraw %}