---
api_type: redy/data-source/wos-variable
kind: property
name: mode
---
Cette propriété permet de définir le comportement de l'acteur à son arrivée dans la scène ou lorsque le *chemin* ou le *champ* de la variable cible sont modifiés.

- **Automatique** Si toutes les conditions sons réunis, l'acteur va récupérer automatiquement la variable et la placer elle ou le *champ* dans la *donnée*.
- **Manuel** L'acteur attend qu'on change de *mode* ou qu'un script le demande pour récupérer la variable et la placer elle ou le *champ* dans la *donnée*.
- **Relatif** L'acteur se comportera comme dans le mode automatique dès qu'il a des [fournisseurs de variable relative](./wos-relative-variable-source.md) ou liaisons de type [fournisseur de variable](../../binding.md#fournisseur-de-variable) qui pointent dessus.

Dans tous les cas, ceci est complètement indépendant du mode de rafraîchissement de l'acteur.
