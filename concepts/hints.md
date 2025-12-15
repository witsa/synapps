---
title: "Conseils"
parent: Concepts
---

# Conseils, bonnes pratiques et Optimisations

> **🚧 En cours de rédaction 🚧**
>
> mise à jour : `2024-11-06 16:00`

Nous vous proposons ici quelques conseils et bonnes pratiques pour la création de vos synapps, ainsi que des optimisations pour améliorer leurs performances.

Un point important à garder à l'esprit est que les synapps sont conçues pour fonctionner sur une variété d'appareils, y compris des appareils mobiles avec des ressources limitées. Mais, surtout dans ce cas, **il demeure essentiel d'optimiser vos synapps pour garantir une expérience utilisateur fluide et réactive**.

## Bonnes pratiques pour la création de synapps

### Découper en scènes

Divisez votre synapp en plusieurs scènes logiques. Cela facilite la gestion du contenu et améliore les performances en ne chargeant que les scènes nécessaires à un moment donné.

Vous pouvez prévoir une navigation entre scènes à l'aide de l'acteur *Bouton de navigation*. Mais le mieux est d'avoir une scène principale qui gère la navigation dans un acteur *Écran*. Les modèles prédéfinis de synapps dans Studio sont conçus selon ce principe.

### Différer les chargements

Comme le précédent point le suggère, plus généralement, ne chargez pas tout le contenu d'un coup. Utilisez des acteurs *Écran* pour charger des portions de votre synapp qui ne sont pas toujours visibles.

En effet, un acteur *Écran* ne charge son contenu que lorsqu'il devient visible, et le décharge lorsqu'il n'est plus visible. Cela permet de réduire la mémoire utilisée et d'améliorer les performances.

Le cas le plus courant est celui des modales : utilisez un acteur *Écran* pour le contenu de la modale, qui ne sera chargé que lorsque la modale est ouverte.

### Regrouper les requêtes vers le REDY

Lorsque vous utilisez des acteurs qui font des requêtes vers le REDY, essayez de les regrouper pour minimiser le nombre d'appels réseau.
 - Dans vos liaisons, utilisez un même fournisseur global.
 - Évitez les détails de reflet autonomes. Utilisez plutôt un requêteur de reflet commun, par exemple un global.

### Utiliser les acteurs utilisant une iframe avec parcimonie

Les acteurs qui utilisent des iframes (comme l'acteur *Iframe*, *Agenda*, *Synoptique*, etc.) peuvent être gourmands en ressources. N'en ajoutez pas une multitude dans vos scènes/composites. Faites attention par exemple à ceux que vous placez dans un composite qui va être instancié plusieurs fois : pour chaque instance, une iframe sera créée et un chargement réseau sera effectué. Différez leur chargement en les plaçant dans un acteur *Écran* si possible.

### Composites légers

Un composite peut contenir un grand nombre d'acteurs. Mais si vous comptez l'utiliser plusieurs fois dans une scène, le nombre d'acteurs instanciés peut rapidement devenir très élevé. Essayez de garder vos composites aussi légers que possible, en évitant d'y inclure des acteurs inutiles, redondants ou invisibles.

### Images en librairie

Dans la mesure du possible, utilisez des images en librairie plutôt que des images importées dans vos scènes. Les images en librairie seront chargées par le navigateur, alors que les images dans vos scènes vont ralentir la publication et son chargement par le Runtime.

### Surveiller les indicateurs d'utilisation des acteurs

Des indicateurs d'utilisation sont disponibles dans Studio dans les designers à partir de la version 1.6.0-beta. Ils permettent de surveiller l'impact de ce que vous ajoutez dans vos scènes/composites.

 Les indicateurs suivants sont affichés :

- le nombre d'acteurs définis dans l'élément courant
- le nombre réel d'acteurs instanciés dans l'élément courant. C'est à dire le nombre d'acteurs qui sont réellement présents à l'exécution, en tenant compte des acteurs :
    - à l'intérieur des composites,
    - dans les scènes des acteurs *Écran*
    - et ceux instanciés dynamiquement ou par script.
- le nombre d'acteurs qui contiennent une iframe, comme par exemple les acteurs *Iframe*, *Agenda* ou *Synoptique*.
- le nombre d'acteurs qui sont susceptibles de requêter des données de manière autonome, comme par exemple les fournisseurs de ressources, les listes de reflets, les journaux, les détails de reflets en mode autonome, etc.
- le nombre de requêtes de données simultanées en cours et le maximum de requêtes simultanées depuis le chargement de l'élément courant.

> 💡 En cliquant sur cet indicateur, on peut réinitialiser le maximum.

Comme pour l'indicateur de taille, certains indicateurs seront colorés en orange si leur valeur dépasse un certain seuil. Cela informe qu'il peut être pertinent d'optimiser l'élément courant pour améliorer ses performances.

- Nombre d'iframes trop élevé dans une scène : à partir de **5**.
- Nombre d'acteurs susceptibles de requêter des données de manière autonome trop élevé dans une scène : à partir de **10**.
- Nombre de requêtes simultanées trop élevé : à partir de **10**.

## Ralentissements et blocages connus

Voici quelques cas connus qui peuvent provoquer des ralentissements ou des blocages dans une synapp.

### Les images trop volumineuses

Une image trop volumineuse va ralentir la publication de la synapp, même placée en librairie.
Aussi, si votre scène met du temps à s'afficher, vérifiez que vous n'avez pas d'images trop lourdes directement dedans. Dans ce cas, réduisez leur taille **et** placez-les en librairie.


### Les composites trop lourds

Un composite qui contient un grand nombre d'acteurs que vous instanciez plusieurs fois dans une scène peut provoquer des ralentissements importants au chargement de la scène. En effet, chaque instance du composite va instancier tous les acteurs qu'il contient. Le nombre peut rapidement devenir très élevé. Surveillez les indicateurs d'utilisation des acteurs pour détecter ce genre de situation.

Aussi, si le composite se charge de requêter ses données ou qu'il contient des acteurs avec iframe, cela peut aggraver la situation.

### Les inclusions en timeout

Dans la section *Projet > Inclusions*, il est possible de définir des dépendances externes qui seront chargées avant chaque scène. Si une inclusion met trop de temps à se charger ou est carrément inaccessible, cela peut bloquer le chargement de la scène. Vérifiez que vos inclusions sont bien accessibles et qu'elles se chargent rapidement.
