---
api_type: redy/data-source/wos-relative-variable
kind: property
name: relativePath
---
Cette propriété va contenir un *chemin relatif* vers la variable à récupérer. C'est un chemin au sens REDY mais par rapport à un autre chemin par ex : `R00001` ou même `R00001.Output`.

Le chemin de référence est une construction de tous les chemins en remontant dans les parents de l'acteur.

Par exemple :

- **Fournisseur 1** :
  - Chemin : `easy.RESS.R00001`

Ce fournisseur pointe sur la ressource `R00001`. Il réalisera les requêtes.

- **Fournisseur relatif 1** :
  - Parent : **Fournisseur 1**
  - Chemin relatif : `Output`

Ce fournisseur est relatif au premier. Il indique être intéressé par la variable enfant `Output` de ce qui est défini dans le fournisseur parent, ici, la ressource `R00001`. Le chemin en entier donne : `easy.RESS.R00001.Output`.

- **Fournisseur relatif 2** :
  - Parent : **Fournisseur relatif 1**
  - champ : *Valeur*

Finalement, ce fournisseur est relatif au *fournisseur relatif 1*. Il indique quant à lui être intéressé par le champ *Valeur* de ce qui résulte du fournisseur parent, ici, la variable `easy.RESS.R00001.Output`. Le chemin en entier donne encore : `easy.RESS.R00001.Output` mais c'est ça *valeur* qui sera inscrite dans la *donnée* de l'acteur.



Comme pour les fournisseurs normaux, un explorateur de paramétrage de REDY aide à saisir ce sous chemin.
