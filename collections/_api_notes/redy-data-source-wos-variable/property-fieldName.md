---
api_type: redy/data-source/wos-variable
kind: property
name: fieldName
---
Par défaut, c'est la variable toute entière qui est récupérée et placée dans le champ *Donnée*. Si vous voulez récupérer une partie de la variable, vous pouvez indiquer le nom du champ à récupérer parmi les possibilités suivantes :
{% include script_api/model_fields.md model="redy/WosVariable" prefix="this.data" %}

Champs de l'objet [Variable WOS]({{ site.baseurl }}/concepts/data-models/redy/wos-variable.html), accessibles par script dans la donnée (`this.data`) quand aucun champ n'est choisi. Le champ suivant est calculé par le fournisseur :

- **Enfants** Le liste des enfants de la variable REDY.

Choisissez *Valeur* si vous voulez écrire dans ce champ. Ainsi, en vous liant avec l'écriture activée à la donnée de l'acteur, vous pourrez écrire dans la variable REDY et envoyer cette valeur automatiquement si la propriété *Écriture au changement* est activée. Sinon par script.
