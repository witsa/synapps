---
title: "Scène"
parent: Concepts
---

> 🚧 en cours de rédaction...

![SynApps](../assets/under-progress.gif)


# Dans le Runtime

# Dans Studio


# Scènes remarquables

Voici une scène qui, une fois définie comme départ, permet d'automatiquement naviguer vers une scène faite pour le gabarit Desktop/Tablette ou vers une scène faite pour le gabarit Smartphone du projet. La bonne scène est choisie en fonction de la résolution de l'afficheur et de la présence des fonctions tactiles.

Les scènes cibles sont à définir dans des paramètres de la scène.


## Hub choix de gabarit

```text
SYNAPPS-STUDIO-SCENE|{"config":{"key":"hub","name":"Hub","additionalDefs":{"desktopMaster":{"type":"scene","label":"Gabarit Desktop","helperTxt":"Scène de Gabarit pour PC et tablette"},"smartphoneMaster":{"type":"scene","label":"Gabarit Smartphone","helperTxt":"Scène de Gabarit pour Smartphone"},"size":{"type":"number","label":"Taille limite","unit":"px"}},"additionals":{"size":760}},"leadActor":{"key":"stack1","type":"layout/stack","properties":{"verticalAlignment":"expand"},"events":{"onInit":["const smartphoneMaster = this.scene.additionals.smartphoneMaster;","const desktopMaster = this.scene.additionals.desktopMaster;","const size = this.scene.additionals.size || 760;","const isEmpty = context.utils.isEmpty;","if (isEmpty(smartphoneMaster) || isEmpty(smartphoneMaster)) return;","this._navTimeout = setTimeout(() => {","  if (this.isDestroyed || this.isDestroying) return;","  if (this.synapp.isInDesigner) return;","  var isSmallScreen = window.matchMedia(`only screen and (max-width: ${size}px), only screen and (max-height: ${size}px)`);","  var isTouchEnabled = 'ontouchstart' in window || navigator.maxTouchPoints > 0 || navigator.msMaxTouchPoints > 0;","  var hasMouse = Boolean(window.matchMedia('(hover: hover) and (pointer: fine)').matches);","  if (isSmallScreen.matches && isTouchEnabled && !hasMouse) {","    this.synapp.navigate(this.scene.additionals.smartphoneMaster);","  } else {","    this.synapp.navigate(this.scene.additionals.desktopMaster);","  }","}, 500);"],"onDestroy":["if (this._navTimeout) clearTimeout(this._navTimeout);"]}}}
```
