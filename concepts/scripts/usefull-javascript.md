---
title: "Quelques éléments Javascript"
parent: Scripts
grand_parent: Concepts
---

> 🚧 En construction

{% include table_of_content.html %}

# Quelques éléments Javascript

## Les types

Il existe plusieurs types de données en Javascript. Les plus courants sont :

- Les booléens
- Les nombres
- Les chaînes de caractères
- Les objets

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

> 🚧 a écrire


#### Concaténation

```javascript
let str1 = 'Hello';
let str2 = 'World';
let str3 = str1 + ' ' + str2;
```
`str3` contiendra `Hello World`.

Autre méthode :

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

### (Les objets)

### (Les fonctions)

## Les conditions

### Les conditions simples
### les conditions multiples
### Les conditions ternaires

### Les opérateurs de comparaison
### Les opérateurs logiques


## L'instruction if...else
## L'instruction switch


## (Les boucles)
### La boucle for
### La boucle while
### La boucle do...while
### La boucle for...in
### La boucle for...of

## L'essentiel de la librairie Math
