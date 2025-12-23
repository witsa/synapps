# Hérités de Actor.LayoutBase

## `properties.overflowX`

Comportement au dépassement horizontal.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'hidden'`.
- **Valeurs possibles :** `'hidden'`, `'visible'`, `'scroll'`, ou `'auto'`.

## `properties.overflowY`

Comportement au dépassement vertical.

- **Modificateur :** `resize`.
- **Valeur par défaut :** `'hidden'`.
- **Valeurs possibles :** `'hidden'`, `'visible'`, `'scroll'`, ou `'auto'`.

## `childSetups`

Obtient les setups des acteur enfants.

- **Lecture seule**
- **Type** : `Array` d'objets `ActorSetup`

## `canAddActor`

Pour savoir s'il est possible d'ajouter un acteur.

- **Lecture seule**
- **Type** : `Boolean`

## `canRemoveActor`

Pour savoir s'il est possible de retirer un acteur.

- **Lecture seule**
- **Type** : `Boolean`

## `canClearActors`

Pour savoir s'il est possible de retirer tous les acteurs.

- **Lecture seule**
- **Type** : `Boolean`

## `moveUpActor()`

Déplace vers le haut un acteur enfant obtenu par sa clé.

- **Paramètres** :
  - `key` (`String`) : La clé de l'acteur enfant à déplacer.


## `moveDownActor()`

Déplace vers le bas un acteur enfant obtenu par sa clé.

- **Paramètres** :
  - `key` (`String`) : La clé de l'acteur enfant à déplacer.


## `addActor()`

Ajoute un acteur enfant.

L'acteur est ajouté à la fin de la liste si `atIndex` n'est pas renseigné.

{: .info }
> C'est le seul moyen de créer un acteur.

- **Asynchrone**
- **Paramètres** :
  - `actorSetup` (`ActorSetup`) : Le setup de l'acteur à ajouter.
  - `atIndex` (`Number`, optionnel) : L'index où insérer l'acteur. Si non renseigné, l'acteur est ajouté à la fin de la liste.
- **Retourne** : L'acteur ajouté (`Actor`).

## `addActors()`

Ajoute une collection d'acteurs enfants.

Les acteurs sont ajoutés à la fin de la liste si le tableau d'indexes n'est pas spécifié.

- **Asynchrone**
- **Paramètres** :
  - `actorSetups` (`Array` d'`ActorSetup`) : Les setups des acteurs à ajouter.
  - `atIndexes` (`Array` de `Number`, optionnel) : Les indexes où insérer les acteurs. Si non renseigné, les acteurs sont ajoutés à la fin de la liste.
- **Retourne** : Un tableau des acteurs ajoutés (`Array` d'`Actor`).

## `removeActor()`

Retire un acteur enfant obtenu par sa clé.

- **Asynchrone**
- **Paramètres** :
  - `key` (`String`) : La clé de l'acteur enfant à retirer.

## `clearActors()`

Retire tous les acteurs enfants.

- **Asynchrone**

{% include api/behavior/parenthood.md %}

{% include api/actor/base.md %}
