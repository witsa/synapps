---
title: Création d'un composite
parent: Tutoriels
---

Il est souvent nécessaire au sein des Synapps de répéter ou de paramétrer tout un ensemble d'acteurs, pour se faire on utilise le [composite]({{ site.baseurl }}{% link concepts/composite.md %}).

### Ressources : {#ressource}

>Composite simple permettant d'afficher un bouton qui ouvre une modale :
>```
>SYNAPPS-STUDIO-COMPOSITE|{"config":{"key":"composite1","name":"Composite 1"},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"input/button","key":"button1","properties":{"content":"Cliquer pour ouvrir la modale","mode":"primary","horizontalAlignment":"middle"}},{"type":"layout/modal","key":"modal-on-click1","properties":{"height":"450px","width":"450px","clickOutsideToClose":false},"additionalDefs":{"showTrigger":{"type":"actor","label":"Affichage","helperTxt":"Acteur qui déclenche l'affichage."},"hideTrigger":{"type":"actor","label":"Fermeture","helperTxt":"Acteur qui déclenche la fermeture."}},"additionals":{"showTrigger":"button1","hideTrigger":"button2"},"children":[{"type":"layout/stack","key":"stack2","children":[{"type":"display/text","key":"text1","properties":{"content":"Hello world !","horizontalAlignment":"middle","verticalAlignment":"middle"}},{"type":"input/button","key":"button2","properties":{"content":"Cliquer pour fermer la modale","horizontalAlignment":"middle","verticalAlignment":"middle","mode":"danger"}}],"properties":{"verticalAlignment":"expand"}}],"events":{"onPostInit":["const showTrigger = context.getActor(this.additionals.showTrigger);","","","if (showTrigger) {","  const originalOnClickFx = showTrigger.events.onClick ? showTrigger.events.onClick.fx : null;","  if (originalOnClickFx) {","    showTrigger.removeEvent('onClick');","  }","","  showTrigger.createEvent('onClick', (ctx) => {","    this.properties.isShown = true;","    if (originalOnClickFx) {","      originalOnClickFx(ctx);","    }","  });","}","","const hideTrigger = context.getActor(this.additionals.hideTrigger);","","if (hideTrigger) {","  const originalOnClickFx = hideTrigger.events.onClick ? hideTrigger.events.onClick.fx : null;","  if (originalOnClickFx) {","    hideTrigger.removeEvent('onClick');","  }","","  hideTrigger.createEvent('onClick', (ctx) => {","    this.properties.isShown = false;","    if (originalOnClickFx) {","      originalOnClickFx(ctx);","    }","  });","}"]}}],"properties":{"fontSize":"4vmin"}}}
>```

>Composite paramétré à l'aide d'une *propriété spécifique* permettant d'afficher un bouton qui ouvre une modale avec un texte personnalisable :
>```
>SYNAPPS-STUDIO-COMPOSITE|{"config":{"key":"composite1","name":"Composite 1","additionalDefs":{"myTexte":{"type":"text","label":"Mon texte","value":"Hello world !"}}},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"input/button","key":"button1","properties":{"content":"Cliquer pour ouvrir la modale","mode":"primary","horizontalAlignment":"middle"}},{"type":"layout/modal","key":"modal-on-click1","properties":{"height":"450px","width":"450px","clickOutsideToClose":false},"additionalDefs":{"showTrigger":{"type":"actor","label":"Affichage","helperTxt":"Acteur qui déclenche l'affichage."},"hideTrigger":{"type":"actor","label":"Fermeture","helperTxt":"Acteur qui déclenche la fermeture."}},"additionals":{"showTrigger":"button1","hideTrigger":"button2"},"children":[{"type":"layout/stack","key":"stack2","children":[{"type":"display/text","key":"text1","properties":{"content":"Hello world !","horizontalAlignment":"middle","verticalAlignment":"middle","fontSize":"3vmin"},"bindings":{"properties.content":"stage@properties.myTexte"}},{"type":"input/button","key":"button2","properties":{"content":"Cliquer pour fermer la modale","horizontalAlignment":"middle","verticalAlignment":"middle","mode":"danger","fontSize":"2vmin"}}],"properties":{"verticalAlignment":"expand"}}],"events":{"onPostInit":["const showTrigger = context.getActor(this.additionals.showTrigger);","","","if (showTrigger) {","  const originalOnClickFx = showTrigger.events.onClick ? showTrigger.events.onClick.fx : null;","  if (originalOnClickFx) {","    showTrigger.removeEvent('onClick');","  }","","  showTrigger.createEvent('onClick', (ctx) => {","    this.properties.isShown = true;","    if (originalOnClickFx) {","      originalOnClickFx(ctx);","    }","  });","}","","const hideTrigger = context.getActor(this.additionals.hideTrigger);","","if (hideTrigger) {","  const originalOnClickFx = hideTrigger.events.onClick ? hideTrigger.events.onClick.fx : null;","  if (originalOnClickFx) {","    hideTrigger.removeEvent('onClick');","  }","","  hideTrigger.createEvent('onClick', (ctx) => {","    this.properties.isShown = false;","    if (originalOnClickFx) {","      originalOnClickFx(ctx);","    }","  });","}"]}}],"properties":{"fontSize":"4vmin"}}}
>```

## Objectif du Tutoriel :

Ce tutoriel vise à expliquer dans un premier temps comment créer un composite simple et à l'intégrer dans une scène . <br>
Par la suite, nous verrons comment paramétrer ce composite et comment modifier ce paramètre pour chaque instance de composite.

# Étape 1 : Créer un composite

Les composites sont accessibles depuis la librairie des [composites]({{ site.baseurl }}{% link concepts/composite.md %}).

Nous allons donc créer un composite exemple avec quelques acteurs qui va permettre d'afficher un bouton qui ouvre une modale avec du texte. Ce composite est trouvable dans la partie [ressource](#ressource)

>
>![Synapps]( {{ site.baseurl }}/assets/tutorials/create-composite/create-composite-setup.png)


# Étape 2 : Inclure des instances de composite dans ma scène

Le composite que nous vennons de créer est maintenant disponible en bas de la liste des acteurs à ajouter :

>![Synapps]( {{ site.baseurl }}/assets/tutorials/create-composite/create-composite-location.png)

Nous pouvons donc créer de multiples instances de ce composite au sein de notre scène, cela nous évitera d'avoir à dupliquer des acteurs.

# Étape 3 : Ajouter des propriétés spécifiques de composite

Les instances précédentes comportent toutes les mêmes acteurs avec exactement les mêmes informations, nous voudrions donc pouvoir personnaliser les informations au sein chaque instance.
Nous allons donc ajouter des *propriétés spécifiques de composite*.

Ces *propriétés spécifiques* sont semblables aux [additionelles]{{ site.baseurl }}{% link concepts/additionals.md %}.

Pour ajouter une propriété spécifique à un composite, il faut se rendre sur le composite lui même, section spécifiques.

>![Synapps]( {{ site.baseurl }}/assets/tutorials/create-composite/create-composite-specifique.png)

Pour ce tutoriel, nous allons créer une propriété spécifique de type *texte* et lier le texte affiché à l'intérieur de la modale à cette *propriété spécifique* :

>![Synapps]( {{ site.baseurl }}/assets/tutorials/create-composite/create-composite-additional.png)

>![Synapps]( {{ site.baseurl }}/assets/tutorials/create-composite/create-composite-binding.png)

Cette *propriété spécifique* peut maintenant être retrouvée dans n'importe quelle instance de composite, nous pouvons ainsi changer le texte situé à l'intérieur de la modale pour chaque instance de composite.
>📌 **REMARQUE**<br>
> Il est possible de lier ces propriété spécifiques.

>![Synapps]( {{ site.baseurl }}/assets/tutorials/create-composite/create-composite-instance.png)

# Étape 4 : Exécution de la synapp

>![Synapps]( {{ site.baseurl }}/assets/tutorials/create-composite/create-composite-execution.gif)

Notre scène présente 3 instances du même composite mais chacun dispose de son texte à afficher dans la modale.
Ce composite est trouvable dans la partie [ressource](#ressource)

Nous avons paramétré notre composite à l'aide d'une *propriété spécifique*, il est ainsi possible d'ajouter de nombreuses *propriétés spécifiques* afin d'obtenir des composite entièrement customisable.
