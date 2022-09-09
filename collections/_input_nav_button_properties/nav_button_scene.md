---
title: Scène
section: specifics
propName: displaySceneKey
propPath: properties.displaySceneKey
scriptApiClass: Actor.Input.NavButtonProperties
order: 1
---
La propriété spécifique `Scène` permet de définir la scène vers laquelle le bouton va rediriger l'utilisateur.

Dans l'inspecteur, une aide référence toutes les scènes du projet vers lesquelles il est possible d'être redirigé.

Il y a deux cas de figure lors de la selection d'une scène.

- Le champ `clé de l'acteur écran` est laissé vide :
<br>
Le bouton va entraîner une navigation vers la scène sélectionnée.

- Le champ `clé de l'acteur écran` est renseigné avec la clé d'un acteur écran :
<br>
Le bouton va entraîner un changement d'affichage de l'acteur écran qui affichera la scène renseignée dans la propriété `scène`.

**Modification des paramètres d'une scène grâce au bouton de navigation**

Lors de la sélection de la propriété `Scène`, si la scène sélectionnée possède un ou des paramètre(s) de scène, une aide va apparaître en dessous de la selection.

Cette aide va permettre de renseigner une valeur différente à un paramètre de la scène afin de changer cette valeur.

Il suffit que la valeur de ce paramètre de scène soit lié à un autre élément d'un acteur pour que celui-ci change également.

Il est à noter que ceci peut être effectué sur la scène sur laquelle se trouve le bouton de navigation, ainsi, à l'aide du bouton, il est donc possible de changer des paramètres de la scène courante.

**Exemple**

Ci dessous, l'exemple d'une scène qui possède deux boutons qui font changer un paramètre de scène dont la valeur est liée à celle d'un acteur texte.

{% raw %}
```
SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene1","name":"Scène 1","additionalDefs":{"prop1":{"type":"text"}},"additionals":{"prop1":"TEST"}},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"input/nav-button","key":"nav-button1","properties":{"content":"Bouton de navigation","displaySceneKey":"scene1"},"additionals":{"prop1":"Hello world !"},"additionalDefs":{"prop1":{"type":"text"}}},{"type":"input/nav-button","key":"nav-button2","properties":{"content":"Bouton de navigation","displaySceneKey":"scene1"},"additionals":{"prop1":"Lorem Ipsum"},"additionalDefs":{"prop1":{"type":"text"}}},{"type":"display/text","key":"text1","properties":{"content":"Voici du texte !"},"bindings":{"properties.content":"stage@additionals.prop1"}}]}}
```
{% endraw %}

>⚠️ **ATTENTION**<br>
> Si vous désirez commander les paramètres d'une scène à travers un acteur écran, n'oublier pas de créer les additionnelles correspondantes sur celui-ci également, sinon, aucune action ne sera transmise
