[Home](sitemap.md)

# Changelog

## Février 2018 (version 1.3.1 à 1.3.3)

Correction de bugs et améliorations diverses [detail ici](https://github.com/witsa/synapps/issues?utf8=%E2%9C%93&q=milestone%3A1.3.3+)

## Janvier 2018 (version 1.3.0)

### Acteur **slider**

Ajout d'un acteur d'intéraction utilisateur permettant de définir des valeurs analogiques
![Slider](changelog/1.3.0/slider.PNG)
_A noter:_ deux modes de fonctionnement: curseur **simple** ou **double**

### Acteur IFrame

Modification de l'acteur IFrame pour permettre de définir des urls composées à partir des propriétés d'acteurs

### Encodage des textes

Fix [Symbole € #22](https://github.com/witsa/synapps/issues/22).
Les caractères spéciaux sont désormais correctement encodés. Ex: €.
_Remarque:_ les Synapps avec des caractères spéciaux déployées en version 1.2.1 et inférieure devront être modifiées en 1.3.0

### Polices génériques

Interprétation Graphiques des Navigateurs #28
Fix [Interprétation Graphiques des Navigateurs #28](https://github.com/witsa/synapps/issues/28).
Ajput de tooltip sur les polices informant l'utilisateur du rendu des polices génériques différent selon le navigateur et l'OS

### Statistiques d'usages

Ajout de statistiques d'usages de SynApps Maker et Runtime
![Statistiques](changelog/1.3.0/stats.PNG)
Ces statistiques contiennent notamment des informations concernant les erreurs sur le Maker ou le Runtime. Elles peuvent être désactivées à tout moment depuis le Maker

### Optimisation des temps de chargement

Les SynApps sont désormais cachées dans le navigateur et ne sont chargées sur le Redy que lorsque de nouvelles versions sont déployées. Ce mécanisme s'appuie sur le numéro de _build_ de la SynApp cachée:
![Statistiques](changelog/1.3.0/build.PNG)
comparé à celui du numéro de build dans le Redy:
![Statistiques](changelog/1.3.0/build2.PNG)
En cas de différence, la SynApp est complètement rechargée dans le navigateur de l'utilisateur.
_Remarque:_ si vous modifier une proriété de la SynApp directement dans le Redy sans passer par le Maker alors vous devez **modifier le numéro de build dans le redy** pour forcer le rafraichissement de la SynApp.

Les configurations des SynApps sont désormais **gzippées** dans le Redy pour diminuer la quantité de données téléchargées et le temps de chargement.

### Maker

Fix [Acteur non déplaçable dans la liste #30](https://github.com/witsa/synapps/issues/30).
Problème corrigé

Amélioration [Rangement des scènes #29](https://github.com/witsa/synapps/issues/29).
Les scènes, ainsi que que les composites, peuvent désormais être triés

### Runtime

Fix [Une SynApp sans scène génère une erreur sur le runtime #32](https://github.com/witsa/synapps/issues/32).
Un popup d'erreur indique l'abscence de scène à l'utilisateur

### Divers

Corrections et améliorations diverses améliorant l'expérience utilisateur et la robustesse de SynApp
