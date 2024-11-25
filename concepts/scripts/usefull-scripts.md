---
title: "Scripts utiles"
parent: Scripts
grand_parent: Concepts
---

> 🚧 En construction

{% include table_of_content.html %}

# Scripts utiles

Nous allons voir ici quelques scripts utiles pour vous aider lorsqu'ils deviennent incontournables.
En effet, de nombreux concepts permettent de reppousser la limite avant que vous ayez besoin de scripter. Mais il arrive des situations où vous ne pourrez pas faire autrement.

>📌*Remarque*<br>
 L'équipe de développement de la solution reste à l'écoute pour intégrer des outils pour continuer de repousser la limite avant l'utilisation de script.

## Transformation de liaison simple

Pour une liaison, il est possible de transformer la valeur de la source avant de la transmettre à la cible. Pour cela, on ajoute l'évènement `onReadTransform` à la source.
Par défaut, elle ne fait que transférer la valeur de la source à la cible.

```javascript
return context.value;
```

`context.value` est la valeur de la source. Le mot clé `return` permet de renvoyer la valeur transformée.

> 📌*Remarque*<br>
Tout ce qui est après le `return` sera ignoré.


### Exemple 1 : Transformation de booléen en texte

Ici, on transforme un booléen en texte. Si la valeur est `true`, on renvoie `green`, sinon `red`.

```javascript
if (context.value) {
    return 'green';
} else {
    return 'red';
}
```

ou bien en ternaire

```javascript
return context.value ? 'green' : 'red';
```

### Exemple 2 : Transformation de nombre en texte

Ici, on transforme un nombre en texte. Si la valeur est `0`, on renvoie `zero`, sinon `not zero`.

```javascript
if (context.value === 0) {
    return 'zero';
} else {
    return 'not zero';
}
```

ou bien en ternaire

```javascript
return context.value === 0 ? 'zero' : 'not zero';
```

On a utilisé ici une condition simple avec l'opérateur `===` pour comparer les valeurs. Voir plus bas pour les [opérateurs de comparaison](#les-opérateurs-de-comparaison).

### Exemple 3 : Transformation de nombre en couleur en fonction d'un seuil
Ici, on va essayer de transformer la valeur en texte en fonction de sa valeur par rapport à un seuil : 'red lorsque la valeur est inférieure à `10`, 'green' lorsque la valeur est supérieure.

```javascript
if (context.value < 10) {
    return 'red';
} else {
    return 'green';
}
```

ou bien en ternaire :

```javascript
return context.value < 0 ? 'red' : 'green';
```

On a utilisé ici une condition simple avec l'opérateur `<` pour comparer les valeurs. Voir plus bas pour les [opérateurs de comparaison](#les-opérateurs-de-comparaison).

### Exemple 4 : Transformation de nombre en couleur par plage de valeurs

Ici, on va transformer la valeur en texte en fonction de sa valeur par rapport à une plage de valeurs : 'red' lorsque la valeur est inférieure à `10`, 'orange' lorsque la valeur est entre `10` et `20`, 'green' lorsque la valeur est supérieure à `20`.

```javascript
if (context.value < 10) {
    return 'red';
} else if (context.value < 20) {
    return 'orange';
} else {
    return 'green';
}
```

On évitera le ternaire ici pour plus de lisibilité.

#### Exemple 5 : Inversion de booléen

Ici, on va transformer un booléen en son inverse.

```javascript
return !context.value;
```

Nous avons utilisé ici l'opérateur `!` pour inverser la valeur du booléen. Voir plus bas pour les [opérateurs logiques](#les-opérateurs-logiques).


## Transformation de liaison multiple

Dans certain cas, une valeur doit être obtenu à partir de plusieurs sources. Pour cela, nous n'allons pas utiliser l'évènement `onReadTransform`. En effet, il se déclenchera que pour une liaison donnée alors que nous voulons obtenir une valeur à partir de plusieurs liaisons.

Pour cela, nous allons utiliser l'évènement `onPropertyChange` de l'acteur. Cet évènement se déclenche à chaque fois qu'une propriété ou une additionnelle de l'acteur change. Nous allons donc devoir surveiller les propriétés/additionnelles de l'acteur, liées à la source pour mettre à jour la propriété cible.

Imaginons le cas suivant : nous avons deux sources *source 1 * qui apportera une première valeur booléenne et *source 2* qui apportera une seconde valeur. Nous voullons qu'un acteur soit visible si les deux valeurs sont vraies.

Pour cela, nous allons ajouter deux additionnelles à l'acteur cible : `source1` et `source2`. Nous allons ensuite les liées à leur source respective. Enfin, nous allons ajouter le script suivant à l'évènement `onPropertyChange` de l'acteur cible.

```javascript
if (context.propertyPath === 'additionals.source1' ||
    context.propertyPath === 'additionals.source2') {
    this.properties.visible = this.additionals.source1 && this.additionals.source2;
}
```

Il faut remarquer plusieurs choses ici :
- `context.propertyPath` contient le chemin de la propriété qui a changé. Cela permet d'être sur que lorsque le script se déclenche, c'est bien une des deux sources qui a changé.
- `this` fait référence à l'acteur courant.
- `this.additionals.source1` et `this.additionals.source2` permettent de récupérer la valeur des sources.
- l'opérateur `&&` permet de vérifier que les deux valeurs sont vraies pour rendre l'acteur visible.
- `this.properties.visible` permet de rendre l'acteur visible ou non.


## Accès des objets Synapps
