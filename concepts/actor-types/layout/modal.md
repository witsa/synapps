---
title: "Modale"
parent: "Disposition"
---


{% include links_actor.md apiClass="Actor.Layout.Modal" %}

# Modale

Acteur qui permet d'afficher une boite de dialogue ou un menu.

![SynApps](../../../assets/concepts/actor/layout_modal/sample-01.gif)

{% include table_of_content.html %}

# Propriétés

## Montrer ?

La propriété *Montrer?* permet d'afficher/cacher la modale.²

> 💡 **ASTUCE**<br>
> Vous pouvez activer cette propriété dans le designer pour apercevoir le contenu de la modale ou pour régler son ancrage. Vous avez également la possibilité d'avoir un apperçu de la modale en cliquant sur le bouton "oeil" juste à coté :
>
> ![aperçu](../../../assets/concepts/actor/layout_modal/image-01.png)


## Ferme si on clique en ailleurs

Cette propriété autorise/interdit la modale de se fermer si l'utilisateur clique en dehors de la modale.

> ⚠️ **ATTENTION**<br>
> Si vous n'autorisez pas ce comportement, vous avez obligatoirement besoin de définir un bouton pour fermer la modale.

## Overlay transparent

Active/désactive la présence d'un fond transparent opalescent derrière la modale.


## Ancrage de la modale

Par défaut, la modale va s'afficher au centre de l'écran. Vous pouvez définir un ancrage complètement différent.

Pour ancrer la modale, il y à trois points à observer :
- *L'acteur attaché :* par défaut, aucun acteur n'est attaché à la modale. Mais si vous en définissez un, la modale se positionnera par rapport à lui.
- *L'ancrage Horizontal/Vertical de la modale :* ces deux propriétés définissent un point sur la modale qui sera son ancre. C'est ce point qui sera ancré à celui de l'acteur attaché.
- *L'ancrage Horizontal/Vertical de l'acteur attaché :* ces deux propriétés définissent un point sur l'acteur attaché qui sera son ancre. C'est ce point qui sera ancré à celui de la modale.

Dans l'exemple ci dessous, la <span style="color: red;">**modale**</span> est attachée à un <span style="color: green;">**acteur bouton**</span> et son ancre est matérialisé par un cercle rouge, l'ancrage sur le bouton est vert :

![SynApps](../../../assets/concepts/actor/layout_modal/sample-02.gif)



## Dépassement de contenu

{% include property_overflow.md %}

La valeur par défaut est **Caché**

> ✔️ **CONSEIL**<br>
> Si votre contenu n'est pas visible, il y a de bonne chance que ce soit à cause de la taille réduite de l'acteur parent.


# Événements

{% include events_layout.md %}

# Usage

La modale est un acteur de disposition qui n'accepte qu'**un seul enfant**. En général, vous y placerez un empilement qui contiendra l'interface de dialogue.

> ✔️ **CONSEIL**<br>
> Placez le plus souvent possible vos modales tout en bas de vos arborescence d'acteurs. Cela évitera que leur contenu gène l'affichage des autres acteurs dans le designer.

> ⚠️ **ATTENTION**<br>
> N'oubliez pas de définir une taille pour votre modale. Sinon, elle ne s'affichera pas correctement.

## Montrer/Cacher la modale

C'est la propriété *Montrer ?* qui permet d'afficher ou de cacher la modale. Vous pouvez modifier cette propriété par liaison.

Vous pouvez également utiliser un script dans un évènement. Par exemple, dans un acteur bouton, dans l'évènement `onClick`, vous pouvez écrire le script suivant pour afficher une modale nommée `myModal` :

```javascript
context.getActor('myModal').properties.isShown = true;
```

Si vous n'êtes pas à l'aise avec les scripts, vous pouvez utiliser la variante **Modale au clic** qui est préconfigurée pour afficher/cacher la modale au clic sur un autre acteur.

# Réinitialisation des héritages de propriété

L'héritage des propriétés est brisé dans une modale. Il faudra redéfinir ces propriétés à l'intérieure.

Par exemple, si vous définissez une taille de texte de 10px sur l'acteur principal d'une scène, cela ne sera pas appliqué à la modale.


# Variantes

## Modale au clic

Cette variante de modale est préconfigurée pour indiquer l'acteur qui lorsqu'on cliquera dessus déclenchera son affichage et l'acteur qui déclenchera sa fermeture.

Voici un exemple de scène qui emploie cette variante :

{% raw %}
```
SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene145","name":"Exemple de modale au clic"},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"input/button","key":"button-open","properties":{"content":"Montrer","horizontalAlignment":"middle","verticalAlignment":"middle"}},{"type":"layout/modal","key":"modal-on-click1","properties":{"height":"200px","width":"200px","borderColor":"rgba(46, 193, 38, 1)","borderWidth":"8px","borderStyle":"solid"},"additionalDefs":{"showTrigger":{"type":"actor","label":"Affichage","helperTxt":"Acteur qui déclenche l'affichage."},"hideTrigger":{"type":"actor","label":"Fermeture","helperTxt":"Acteur qui déclenche la fermeture."}},"additionals":{"showTrigger":"button-open","hideTrigger":"button-close"},"children":[{"type":"layout/stack","key":"stack2","properties":{"verticalAlignment":"expand","paddingTop":"2px","paddingBottom":"2px","paddingRight":"2px","paddingLeft":"2px"},"children":[{"type":"display/text","key":"text1","properties":{"content":"la modale","horizontalAlignment":"middle","verticalAlignment":"middle"}},{"type":"input/button","key":"button-close","properties":{"content":"Fermer","mode":"danger","outline":true,"textAlign":"center"}}]}],"events":{"onPostInit":["const showTrigger = context.getActor(this.additionals.showTrigger);","","if (showTrigger) {","  const originalOnClickFx = showTrigger.events.onClick ? showTrigger.events.onClick.fx.bind(showTrigger) : null;","  if (originalOnClickFx) {","    showTrigger.removeEvent('onClick');","  }","","  showTrigger.createEvent('onClick', (...args) => {","    this.properties.isShown = true;","    if (originalOnClickFx) {","      originalOnClickFx(...args);","    }","  });","}","","const hideTrigger = context.getActor(this.additionals.hideTrigger);","","if (hideTrigger) {","  const originalOnClickFx = hideTrigger.events.onClick ? hideTrigger.events.onClick.fx.bind(showTrigger) : null;","  if (originalOnClickFx) {","    hideTrigger.removeEvent('onClick');","  }","","  hideTrigger.createEvent('onClick', (...args) => {","    this.properties.isShown = false;","    if (originalOnClickFx) {","       originalOnClickFx( ...args);","    }","  });","}"]}}]}}
```
{% endraw %}

![modal au clic](../../../assets/concepts/actor/layout_modal/image-02.png)
