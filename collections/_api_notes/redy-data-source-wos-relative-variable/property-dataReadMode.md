---
api_type: redy/data-source/wos-relative-variable
kind: property
name: dataReadMode
---
Cette propriété permet de renseigner comment le fournisseur principal doit aller chercher la cible de l'acteur. En effet, rappelons que c'est le fournisseur parent qui réalise les requêtes. Deux modes de lecture sont possibles :

- **Une seule fois** Le fournisseur parent ne fournira la cible que la première fois. Puis, ses autres requêtes n'iront plus la rafraîchir.
- **A chaque rafraîchissement** L'acteur rafraichira la cible à chaque fois que le fournisseur parent fera une requête.
