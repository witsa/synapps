---
api_type: redy/data-source/wos-relative-variable
kind: property
name: relativeTo
---
Cette propriété permet de renseigner le fournisseur parent de l'acteur par sa clé. Vous aurez le choix parmi tous les fournisseurs de la même scène ou du même composite ainsi que ceux définis parmi les fournisseurs de donnée globaux.

Bien entendu, il sera tout a fait possible de choisir un autre fournisseur relatif de variable aussi.

> 📌 **REMARQUE**<br>
Quoi qu'il en soit, on trouvera un fournisseur normal en remontant dans l'ascendance des acteurs relatifs.

Si vous fournissez par liaison ou par script un fournisseur dans le contexte de donnée de l'acteur et que la clé du parent reste vide, ce fournisseur sera utilisé comme parent. C'est très utile pour paramétrer un composite qui contient un fournisseur relatif mais pas de normal.
