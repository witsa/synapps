---
title: Navigation avec un acteur écran
parent: Tutoriels
---

Voici les trois scènes produites au terme de ce tutoriel :

>{% raw %}
>``` text
>SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene1","name":"Scène 1"},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"input/nav-button","key":"nav-button1","properties":{"content":"Bouton de navigation","textAlign":"center","fontSize":"6em","displaySceneKey":"scene3","screenActorKey":"screen1"}},{"type":"display/screen","key":"screen1","properties":{"verticalAlignment":"expand","sceneKey":"scene2"}}]}}
>```
>{% endraw %}

>{% raw %}
>``` text
>SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene2","name":"Scène 2"},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"display/text","key":"text1","properties":{"verticalAlignment":"middle","horizontalAlignment":"middle","content":"Scène 2","fontSize":"6vmin","color":"rgba(255, 255, 255, 1)"}}],"properties":{"backgroundColor":"rgba(13, 0, 255, 1)"}}}
>```
>{% endraw %}

>{% raw %}
>``` text
>SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene3","name":"Scène 3"},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"display/text","key":"text1","properties":{"verticalAlignment":"middle","horizontalAlignment":"middle","content":"Scène 3","fontSize":"6vmin","color":"rgba(255, 255, 255, 1)"}}],"properties":{"backgroundColor":"rgba(255, 0, 0, 1)"}}}
>```
>{% endraw %}

# Etape 1 : Création des acteurs et scènes

Pour commencer, il faudra créer un acteur *Bouton de navigation* ainsi qu'un acteur *Écran* au sein d'une Scène 1.

>![SynApps]( {{ site.baseurl }}/assets/tutorials/navigation-with-screen-actor/nav-scene-with-screen-setup.gif)

Ensuite, il faudra disposer de 2 autres scènes différentes , dans cet exemple, les deux autres scènes disposeront de couleurs de fond différentes, la Scène 2 sera de couleur rouge et la Scène 3 de couleur bleu.

# Etape 2 : Paramétrage des acteurs

Dans un premier temps, la Scène 2 sera affichée par l'acteur *Écran*.

>![SynApps]( {{ site.baseurl }}/assets/tutorials/navigation-with-screen-actor/nav-scene-with-screen-display-scene.gif)

L'acteur *Bouton de navigation* doit maintenant pointer l'acteur *Écran* sur lequel la navigation doit être effectuée ainsi que la scène vers laquelle l'acteur doit naviguer.

>![SynApps]( {{ site.baseurl }}/assets/tutorials/navigation-with-screen-actor/nav-scene-with-screen-setup-btn.gif)

# Étape 3 : Éxécution

Voici l'exemple d'une navigation d'un acteur *Écran* entre deux scènes grâce à un acteur *Bouton de navigation*.

>![SynApps]( {{ site.baseurl }}/assets/tutorials/navigation-with-screen-actor/nav-scene-with-screen-execution.gif)