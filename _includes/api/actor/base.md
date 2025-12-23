# Hérités de `Actor.BaseActor`

## `properties.classNames`

Nom de class CSS séparées par une virgule à ajouter à l'acteur.

- **Modificateur :** `render`.
- **Valeur par défaut :** `''`.
- **Type** : `String`

## `properties.height`

Hauteur de l'acteur

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'auto'`.
- **Type** : `CssSizeString`

## `properties.minHeight`

Hauteur minimale de l'acteur

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'auto'`.
- **Type** : `CssSizeString`

## `properties.maxHeight`

Hauteur maximale de l'acteur

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'none'`.
- **Type** : `CssSizeString`

## `properties.width`

Largeur de l'acteur

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'auto'`.
- **Type** : `CssSizeString`

## `properties.minWidth`

Largeur minimale de l'acteur

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'auto'`.
- **Type** : `CssSizeString`

## `properties.maxWidth`

Largeur maximale de l'acteur

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'none'`.
- **Type** : `CssSizeString`

## `properties.backgroundColor`

Couleur de fond de l'acteur.

- **Modificateur :** `css`.
- **Valeur par défaut :** `''`.
- **Type** : `CssColorString`

## `properties.color`

Couleur de l'acteur.

**Hérité**

- **Modificateur :** `css`.
- **Valeur par défaut :** `''`.
- **Type** : `CssColorString`

## `properties.paddingTop`

Marge intérieure haute.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `CssSizeString`

## `properties.paddingBottom`

Marge intérieure basse.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `CssSizeString`

## `properties.paddingRight`

Marge intérieure droite.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `CssSizeString`

## `properties.paddingLeft`

Marge intérieure gauche.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `CssSizeString`

## `properties.borderColor`

Couleur de bordure.

- **Modificateur :** `css`.
- **Valeur par défaut :** `'currentColor'`.
- **Type** : `CssColorString`

## `properties.borderWidth`

Épaisseur de bordure. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/border-width)

**Exemples :**

```javascript
// Bordure à 3px
'3px'

// Bordure haute à 0px et le reste à 3px
'0 3px 3px 3px'
```

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'1px'`.
- **Type** : `CssSizeString`

## `properties.borderStyle`

Style de bordure.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'none'`.
- **Type** : `'none'|'solid'|'dotted'|'dashed'`

## `properties.borderRadius`

Arrondissement des coins. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/border-radius)

**Exemples :**

```javascript
// Arrondis sur tous les coins, courbure de 3px
'3px'

// Arrondis sur le coin haut gauche, haut droit, bas droit, bas gauche :
'3px 3px 0 0'
```

- **Modificateur :** `css`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `CssSizeString`

## `properties.opacity`

Opacité en %.

- **Modificateur :** `css`.
- **Valeur par défaut :** `100`.
- **Type** : `Number`

## `properties.textAlign`

Alignement du texte.

**Hérité**

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'inherit'`.
- **Type** : `'inherit'|'left'|'right'|'center'|'justify'`

## `properties.horizontalAlignment`

Alignement horizontale dans un [acteur empilement](Actor.Layout.Stack) ou [acteur boite à vue](Actor.Layout.ViewBox).

**Attention** aux largeurs fixées qui prennent le pas sur la valeur `'expand'`

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'auto'`.
- **Type** : `'auto'|'left'|'right'|'middle'|'expand'`

## `properties.verticalAlignment`

Alignement verticale dans un acteur empilement ou boite à vue.

**Attention** aux hauteurs fixées qui prennent le pas sur la valeur `'expand'`

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'auto'`.
- **Type** : `'auto'|'left'|'right'|'middle'|'expand'`

## `properties.marginTop`

Marge extérieure haute.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `String`

## `properties.marginBottom`

Marge extérieure basse.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `CssSizeString`

## `properties.marginRight`

Marge extérieure droite.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `CssSizeString`

## `properties.marginLeft`

Marge extérieure gauche.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `CssSizeString`

## `properties.visible`

Visibilité de l'acteur.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `true`.
- **Type** : `Boolean`

## `properties.top`

Position verticale depuis le haut dans un [acteur toile](Actor.Layout.Canvas).

- **Modificateur :** `css`.
- **Valeur par défaut :** `''`.
- **Type** : `CssSizeString`

## `properties.bottom`

Position verticale depuis le bas dans un [acteur toile](Actor.Layout.Canvas).

- **Modificateur :** `css`.
- **Valeur par défaut :** `''`.
- **Type** : `CssSizeString`

## `properties.right`

Position horizontale depuis la droite dans un [acteur toile](Actor.Layout.Canvas).

- **Modificateur :** `css`.
- **Valeur par défaut :** `''`.
- **Type** : `CssSizeString`

## `properties.left`

Position horizontale depuis la gauche dans un [acteur toile](Actor.Layout.Canvas).

- **Modificateur :** `css`.
- **Valeur par défaut :** `''`.
- **Type** : `CssSizeString`

## `properties.textDecoration`

Décoration du texte.

**Hérité**

- **Modificateur :** `css`.
- **Valeur par défaut :** `'inherit'`.
- **Type** : `'none'|'underline'|'inherit'`

## `properties.fontStyle`

Style du texte.

**Hérité**

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'inherit'`.
- **Type** : `'normal'|'italic'|'inherit'`

## `properties.fontVariant`

Variant du texte.

**Hérité**

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'inherit'`.
- **Type** : `'normal'|'small-caps'|'all-small-caps'`

## `properties.fontWeight`

Épaisseur du texte.

**Hérité**

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'inherit'`.
- **Type** : `'normal'|'bold'|'inherit'`

## `properties.fontFamily`

Police du texte. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/font-family)

**Hérité**

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'inherit'`.
- **Type** : `CssFontFamilyString|'inherit'`

## `properties.fontSize`

Hauteur du texte.

**Hérité**

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'inherit'`.
- **Type** : `CssSizeString|'inherit'`

## `properties.lineHeight`

Hauteur de ligne.

**Hérité**

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'inherit'`.
- **Type** : `CssSizeString|'inherit'`

## `properties.toolTip`

Texte info bulle.

- **Modificateur :** `other`.
- **Valeur par défaut :** `''`.
- **Type** : `String`

## `properties.rotate`

Angle de rotation en degré.

- **Modificateur :** `css`.
- **Valeur par défaut :** `0`.
- **Type** : `Number`

## `properties.scaling`

Taux de mise à l'échelle.

**Exemples :**

```javascript
// > 1 : plus grand
// < 1 : moins grand
// < 0 : renversé
```

- **Modificateur :** `css`.
- **Valeur par défaut :** `1`.
- **Type** : `Number`

## `properties.translateX`

Translation horizontale.

- **Modificateur :** `css`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `CssSizeString`

## `properties.translateY`

Translation verticale.

- **Modificateur :** `css`.
- **Valeur par défaut :** `'0px'`.
- **Type** : `CssSizeString`

## `properties.boxShadow`

Ombre portée. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/box-shadow)

- **Modificateur :** `css`.
- **Valeur par défaut :** `'none'`.
- **Type** : `String`

## `properties.zIndex`

Z-index. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/z-index)

Rester entre -9 et 4999 (-10 et 5000 sont réservés aux modales)

- **Modificateur :** `css`.
- **Valeur par défaut :** `'auto'`.
- **Type** : `String`

## `properties.transition`

Transition. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/transition)

- **Modificateur :** `css`.
- **Valeur par défaut :** `'none'`.
- **Type** : `String`

## `properties.animation`

Animation. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/animation)

- **Modificateur :** `css`.
- **Valeur par défaut :** `'none'`.
- **Type** : `String`

## `properties.cursor`

Curseur souris. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/cursor)

> Attention au limitation de taille pour les images : maximum 126x126

- **Modificateur :** `css`.
- **Valeur par défaut :** `'inherit'`.
- **Type** : `String`

## `properties.backgroundImage`

Image de fond. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/background-image)

- **Modificateur :** `css`.
- **Valeur par défaut :** `'none'`.
- **Type** : `String`

## `properties.backgroundPosition`

Position du fond. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/background-position)

- **Modificateur :** `css`.
- **Valeur par défaut :** `'left top'`.
- **Type** : `String`

## `properties.backgroundSize`

Taille du fond. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/background-size)

- **Modificateur :** `css`.
- **Valeur par défaut :** `'auto auto'`.
- **Type** : `String`

## `properties.backgroundRepeat`

Répétition du fond. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/background-repeat)

- **Modificateur :** `css`.
- **Valeur par défaut :** `'repeat'`.
- **Type** : `String`

## `properties.backgroundAttachment`

Attachement du fond. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/background-attachment)

- **Modificateur :** `css`.
- **Valeur par défaut :** `'scroll'`.
- **Type** : `String`

## `properties.filter`

Filtre. Voir information [ici](https://developer.mozilla.org/fr/docs/Web/CSS/filter)

- **Modificateur :** `css`.
- **Valeur par défaut :** `'none'`.
- **Type** : `String`


## `key`

La clé unique de l'acteur.
<br>Son unicité est valable dans le contexte de la scène ou du composite parent direct de l'acteur.

- **Lecture seule**
- **Type** : `String`

## `dataStores.redy`

Obtient les magasins de données de la synapp.

- **Lecture seule**
- **Type** : REDY.Synapps.DataStores.Redy`

## `accessories`

Obtient les accessoires de l'acteur.

Chaque accessoire est accessible par sa clé :
```js
this.accessories.log.properties.onActorPropertyChanged = true;
```
pour accéder à l'accessoire `log` préalablement créé et activer la journalisation au changement de propriété de l'acteur.
 <br> La gestion des accessoires s'effectue avec les méthodes : [`createAccessory()`](#createaccessory) et [`removeAccessory()`](#removeaccessory).

## `isDestroyed`

Pour savoir si l'acteur a été détruit.

- **Lecture seule**
- **Type** : `Boolean`

## `isDestroying`

Pour savoir si l'acteur est en cours de destruction.

- **Lecture seule**
- **Type** : `Boolean`

## `slotComposite`

Composite auquel appartient l'emplacement contenant l'acteur.

- **Lecture seule**
- **Type** : [`Actor.Composite`]({{ site.baseurl }}/api/actor/composite) ou `null`
