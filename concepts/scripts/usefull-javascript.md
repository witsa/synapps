---
title: "Quelques éléments Javascript"
parent: Scripts
grand_parent: Concepts
---

{% include table_of_content.html %}

# Quelques éléments Javascript

## Les types

Il existe plusieurs types de données en Javascript. Les plus courants sont :

- Les booléens
- Les nombres
- Les chaînes de caractères
- Les objets
- Les fonctions

### Les booléens

Les booléens sont des valeurs qui peuvent être soit `true` soit `false`.

```javascript
let isTrue = true;
let isFalse = false;
```

Les booléens sont souvent utilisés pour les conditions.

#### Conversion en booléen

```javascript
let num = 42;
let bool = Boolean(num);
```
Dans cet exemple, `bool` contiendra `true`.
En Javascript, les valeurs suivantes sont considérées comme `false` :
- `false`
- `0`
- `''` (chaîne de caractères vide)
- `null`
- `undefined`
- `NaN`

Toutes les autres valeurs sont considérées comme `true`.

### Les nombres

Les nombres en Javascript sont des valeurs numériques.

```javascript
let num1 = 42;
let num2 = 3.14;
let num3 = 1e3; // 1000
let num4 = 0b1010; // 10 en binaire
let num5 = 0o12; // 10 en octal
let num6 = 0xA; // 10 en hexadécimal
let num7 = NaN; // Not a Number
let num8 = Infinity;
let num9 = -Infinity;
```

Les opérations mathématiques sont possibles en Javascript.

### Les chaînes de caractères

#### Concaténation

```javascript
let str1 = 'Hello';
let str2 = 'World';
let str3 = str1 + ' ' + str2;
```
`str3` contiendra `Hello World`.

Autre méthode, la chaine dynamique (template string). Elle permet d'insérer des expression directement dans la chaîne.

Par exemple :

```javascript
let str1 = 'Hello';
let str2 = 'World';
let str3 = `${str1} ${str2}`;
```

#### Longueur d'une chaîne

```javascript
let str = 'Hello World';
let length = str.length;
```

Dans cet exemple, `length` contiendra `11`.

#### Recherche dans une chaîne

```javascript
let str = 'Hello World';
let index = str.indexOf('World');
```
Dans cet exemple, `index` contiendra `6`.

Autre méthode pour savoir si une chaîne contient une sous-chaîne :

```javascript
let str = 'Hello World';
let contains = str.includes('World');
```
Dans cet exemple, `contains` contiendra `true`.

#### Extraction d'une sous-chaîne

```javascript
let str = 'Hello World';
let subStr = str.substring(6, 11);
```
Dans cet exemple, `subStr` contiendra `World`.

#### Remplacement

```javascript
let str = 'Hello World';
let newStr = str.replace('World', 'Synapps');
```
Dans cet exemple, `newStr` contiendra `Hello Synapps`.

### Remplacement multiple

```javascript
let str = 'Hello World';
let newStr = str.replaceAll('o', 'a');
```
Dans cet exemple, `newStr` contiendra `Hella Warld`.

### Conversion en majuscule/minuscule

```javascript
let str = 'Hello World';
let upperStr = str.toUpperCase();
let lowerStr = str.toLowerCase();
```
Dans cet exemple, `upperStr` contiendra `HELLO WORLD` et `lowerStr` contiendra `hello world`.

### Suppression des espaces en début et fin de chaîne

```javascript
let str = ' Hello World ';
let trimmedStr = str.trim();
```
Dans cet exemple, `trimmedStr` contiendra `Hello World`.

### Découpage d'une chaîne

```javascript
let str = 'Hello World';
let parts = str.split(' ');
```
Dans cet exemple, `parts` contiendra un tableau avec `Hello` et `World`.

### Conversion en nombre

```javascript
let str = '42';
let num = Number(str);
```
Dans cet exemple, `num` contiendra `42`.

### Conversion en booléen

```javascript
let str = 'test';
let bool = Boolean(str);
// > true

let boolTrue = Boolean(10);
// > true

let boolFalse = Boolean(0);
// false
```

### Les tableaux

Les tableaux sont des objets qui permettent de stocker plusieurs valeurs. Ils sont définis en utilisant des crochets `[]`.
Il n'est pas nécessaire de définir le type des éléments du tableau, un tableau peut contenir des éléments de types différents.

```javascript
let array = [1, 'two', true, 4.5];
```

## Accéder aux éléments d'un tableau

```javascript
let array = [1, 2, 3];
let firstElement = array[0]; // 1
let secondElement = array[1]; // 2
let thirdElement = array[2]; // 3
```
## Taille d'un tableau

```javascript
let array = [1, 2, 3];
let size = array.length; // 3
```

### Ajouter un élément à un tableau

Ajouter un élément à la fin du tableau :

```javascript
let array = [1, 2, 3];
array.push(4);
// array est maintenant [1, 2, 3, 4]
```

Il est aussi possible d'ajouter un élément au début du tableau :

```javascript
let array = [1, 2, 3];
array.unshift(0);
// array est maintenant [0, 1, 2, 3]
```
Il est aussi possible d'ajouter plusieurs éléments à la fois :

```javascript
let array = [1, 2, 3];
array.push(4, 5, 6);
// array est maintenant [1, 2, 3, 4, 5, 6]
```

### Supprimer un élément d'un tableau

```javascript
let array = [1, 2, 3, 4];
array.pop();
// array est maintenant [1, 2, 3]
```

```javascript
let array = [1, 2, 3, 4];
array.shift();
// array est maintenant [2, 3, 4]
```

## Les opérateurs de comparaison

Les opérateurs de comparaison permettent de comparer deux valeurs.

- `==` : égal à
- `===` : strictement égal à (même type et même valeur)
- `!=` : différent de
- `!==` : strictement différent de (même type et même valeur)
- `<` : inférieur à
- `<=` : inférieur ou égal à
- `>` : supérieur à
- `>=` : supérieur ou égal à

Quelques exemples d'utilisation :

```javascript
let a = 5;
let b = '5';
console.log(a == b); // true
console.log(a === b); // false
console.log(a != b); // false
console.log(a !== b); // true
console.log(a < 10); // true
console.log(a <= 5); // true
console.log(a > 3); // true
console.log(a >= 5); // true
```

### La différence entre `==` et `===`
La différence entre `==` et `===` est que `==` compare les valeurs en effectuant une conversion de type si nécessaire, tandis que `===` compare les valeurs sans conversion de type.

### Les opérateurs logiques
Les opérateurs logiques permettent de combiner plusieurs conditions.

- `&&` : et logique
- `||` : ou logique

Quelques exemples d'utilisation :

```javascript
let a = 5;
let b = 10;
console.log(a < 10 && b > 5); // true
console.log(a < 10 || b < 5); // true
```

On peut aussi utiliser l'opérateur de négation `!` pour inverser une condition.

```javascript
let a = 5;
console.log(!(a < 10)); // false
```

## Les conditions

Les conditions permettent de savoir si une certaine condition est vraie ou fausse et en fonction du résultat, d'exécuter un certain code.

### Les conditions simples

La structure de base d'une condition est la suivante :

```javascript
if (condition) {
    // code à exécuter si la condition est vraie
} else {
    // code à exécuter si la condition est fausse
}
```

Par exemple :

```javascript
if (context.value === 0) {
    return 'zero';
} else {
    return 'not zero';
}
```

### Les conditions ternaires

Une condition ternaire est une forme abrégée de la structure if...else. Elle permet d'écrire une condition en une seule ligne.
```javascript
condition ? valeur_si_vrai : valeur_si_faux;
```

Par exemple :

```javascript
return context.value === 0 ? 'zero' : 'not zero';
```

### les conditions multiples

La structure de base d'une condition multiple est la suivante :

```javascript
if (condition1) {
    // code à exécuter si la condition1 est vraie
} else if (condition2) {
    // code à exécuter si la condition2 est vraie
} else {
    // code à exécuter si aucune des conditions n'est vraie
}
```

Par exemple :

```javascript
if (context.value === 0) {
    return 'zero';
} else if (context.value === 1) {
    return 'one';
} else {
    return 'other';
}
```

ça peut devenir difficile à lire si on a beaucoup de conditions. Dans ce cas, il est préférable d'utiliser l'instruction `switch`.

```javascript
switch (expression) {
    case valeur1:
        // code à exécuter si l'expression est égale à valeur1
        break;
    case valeur2:
        // code à exécuter si l'expression est égale à valeur2
        break;
    default:
        // code à exécuter si aucune des valeurs n'est égale à l'expression
}
```

Par exemple :

```javascript
switch (context.value) {
    case 0:
        return 'zero';
    case 1:
        return 'one';
    default:
        return 'other';
}
```


## Les boucles (avancé)

Il est parfois nécessaire de répéter une série d'instructions plusieurs fois. Pour cela, Javascript propose plusieurs types de boucles.

### La boucle for

La boucle for permet de répéter un bloc de code un certain nombre de fois.

```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

Le code ci-dessus affichera les nombres de `0` à `4` dans la console.

La première partie de la boucle `let i = 0` initialise la variable `i` à `0`. La deuxième partie `i < 5` est la condition qui doit être vraie pour que la boucle continue. La troisième partie `i++` incrémente la variable `i` de `1` à chaque itération.

### La boucle while

La boucle while permet de répéter un bloc de code tant qu'une condition est vraie.

```javascript
let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}
```

### La boucle do...while

La boucle do...while est similaire à la boucle while, mais elle garantit que le bloc de code est exécuté au moins une fois.

```javascript
let i = 0;
do {
    console.log(i);
    i++;
} while (i < 5);
```

### La boucle for...in
La boucle for...in permet de parcourir les propriétés d'un objet.

```javascriptlet obj = {a: 1, b: 2, c: 3};
for (let key in obj) {
    console.log(key + ': ' + obj[key]);
}
```

### La boucle for...of

La boucle for...of permet de parcourir les éléments d'un tableau ou d'une chaîne de caractères.

```javascript
let array = [1, 2, 3];
for (let value of array) {
    console.log(value);
}
```

## Les fonctions (avancé)

Il est possible de définir des fonctions en Javascript. Les fonctions sont définies en utilisant le mot-clé `function`.

```javascript
function maFonction(param1, param2) {
    // Corps de la fonction
    return param1 + param2;
}
```

on peut aussi les définir en utilisant une expression de fonction fléchée :

```javascript
const maFonction = (param1, param2) => {
    // Corps de la fonction
    return param1 + param2;
}
```
L'avantage des fonctions fléchées est qu'elles sont plus concises et qu'elles n'ont pas leur propre contexte `this`.


## L'essentiel de la librairie Math
La librairie Math permet de faire des opérations mathématiques courantes.

```javascript
Math.PI; // 3.141592653589793
Math.sqrt(16); // 4
Math.pow(2, 3); // 8
Math.random(); // Nombre aléatoire entre 0 et 1

Math.floor(4.7); // 4
Math.ceil(4.3); // 5
Math.round(4.5); // 5
```

## La console de débogage

La console de débogage permet d'afficher des messages dans la console de Synapps. Cela peut être utile pour déboguer des scripts.

```javascript
console.log('Message de débogage');
console.error('Message d\'erreur');
console.warn('Message d\'avertissement');
console.info('Message d\'information');
console.debug('Message de débogage détaillé');
```
