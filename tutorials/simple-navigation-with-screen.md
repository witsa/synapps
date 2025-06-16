---
title: Navigation avec un acteur écran
parent: Tutoriels
---

## Objectif du Tutoriel :

Ce tutoriel vise à fournir des instructions détaillées pour naviguer de manière efficace à travers un acteur *Écran* grâce à des acteurs *Bouton de navigation*.

### Pour Aller Plus Loin :

Dans cette section, découvrez des fonctionnalités avancées pour enrichir l'expérience utilisateur.

Visualisation de la Scène Courante sur le Bouton de Navigation :

Explorez la possibilité de changer dynamiquement le bouton de navigation en fonction de la scène affichée.

En suivant ces étapes, vous serez en mesure de naviguer aisément à travers l'acteur écran tout en personnalisant l'affichage pour une expérience utilisateur optimale.

## Voici les trois scènes produites au terme de ce tutoriel :

### Scène 1:
>{% raw %}
>``` text
>SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene1","name":"Scène 1"},"leadActor":{"type":"layout/stack","key":"stack1","properties":{"fontSize":"4vmin"},"children":[{"type":"layout/stack","key":"stack2","children":[{"type":"input/nav-button","key":"nav-button1","properties":{"content":"Bouton de navigation vers Scène 2","displaySceneKey":"scene2","screenActorKey":"screen1","horizontalAlignment":"middle"},"bindings":{"properties.mode":"actor#screen1@properties.sceneKey"},"events":{"properties/mode/binding/onReadTransform":["return context.value !== this.properties.displaySceneKey ? \"default\" : \"primary\";"]}},{"type":"input/nav-button","key":"nav-button2","properties":{"content":"Bouton de navigation vers Scène 3","displaySceneKey":"scene3","screenActorKey":"screen1","horizontalAlignment":"middle"},"bindings":{"properties.mode":"actor#screen1@properties.sceneKey"},"events":{"properties/mode/binding/onReadTransform":["return context.value !== this.properties.displaySceneKey ? \"default\" : \"primary\";"]}}],"properties":{"orientation":"horizontal"}},{"type":"display/screen","key":"screen1","properties":{"verticalAlignment":"expand","sceneKey":"scene2"}}]}}
>```
>{% endraw %}

### Scène 2:
>{% raw %}
>``` text
>SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene2","name":"Scène 2"},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"display/text","key":"text1","properties":{"verticalAlignment":"middle","horizontalAlignment":"middle","content":"Scène 2","fontSize":"6vmin","color":"rgba(255, 255, 255, 1)"}}],"properties":{"backgroundColor":"rgba(13, 0, 255, 1)"}}}
>```
>{% endraw %}

### Scène 3:
>{% raw %}
>``` text
>SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene3","name":"Scène 3"},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"display/text","key":"text1","properties":{"verticalAlignment":"middle","horizontalAlignment":"middle","content":"Scène 3","fontSize":"6vmin","color":"rgba(255, 255, 255, 1)"}}],"properties":{"backgroundColor":"rgba(255, 0, 0, 1)"}}}
>```
>{% endraw %}

# Etape 1 : Création des acteurs et scènes

Pour commencer, il faudra créer deux acteur *Bouton de navigation* ainsi qu'un acteur *Écran* au sein d'une Scène 1.

><details>
><summary>GIF</summary>
><image src="/assets/tutorials/navigation-with-screen-actor/nav-scene-with-screen-setup.gif" alt="Animated gif"/>
></details>

Ensuite, il faudra disposer de 2 autres scènes différentes , dans cet exemple, les deux autres scènes disposeront de couleurs de fond différentes, la Scène 2 sera de couleur rouge et la Scène 3 de couleur bleu.

# Etape 2 : Paramétrage des acteurs

Chaque acteur *Bouton de navigation* doit maintenant pointer l'acteur *Écran* sur lequel la navigation doit être effectuée ainsi que la scène vers laquelle l'acteur écran doit naviguer.

><details>
><summary>GIF</summary>
><image src="/assets/tutorials/navigation-with-screen-actor/nav-scene-with-screen-setup-btn.gif" alt="Animated gif"/>
></details>


## Pour aller plus loin

Grâce aux liaisons Synapps et à un script très simple, il est possible de visualiser la scène active et de modifier le bouton pour qu'il change de couleur en fonction de la scène courante.

Pour se faire, il faut lier le *Mode* du *Bouton de navigation* avec la clé de la scène de l'acteur *Écran* et rajouter le script suivant :

```
return context.value !== this.properties.displaySceneKey ? "default" : "primary";
```

# Étape 3 : Éxécutions

Voici l'exemple d'une navigation d'un acteur *Écran* entre deux scènes grâce à des acteurs *Bouton de navigation*.

><details>
><summary>GIF</summary>
><image src="/assets/tutorials/navigation-with-screen-actor/nav-scene-with-screen-execution.gif" alt="Animated gif"/>
></details>
