# Hérités de Behavior.Parenthood

## `childUis`

Obtient les acteurs enfants.

- **Lecture seule**
- **Type** : `Set` d'objets `Actor`

## `isParent`

Toujours vrai pour un parent.

- **Lecture seule**
- **Type** : `Boolean`

## `childActors`

Obtiens la liste de tous les acteurs enfants.

- **Lecture seule**
- **Type** : `Array` d'objets `Actor`

## `getActor()`

Obtient un acteur enfant par sa clé.

- **Paramètres** :
  - `key` (`String`) : La clé de l'acteur enfant à obtenir.
- **Retourne** : L'acteur enfant (`Actor`) ou `null` si aucun acteur n'a été trouvé avec cette clé.
