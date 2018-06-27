# Tutorial 7: les acteurs métiers natifs du REDY - Part 3: **Agenda** et **Grapheur**

[Home](../../sitemap.md) > [Tutoriaux](../index.md) > [Tutorial](index.md)

Les acteurs grapheurs et agenda ne nécessitent pas une configuration particuliere. Nous allons les intégrer simplement dans 2 scènes sans barres de commandes contrairement aux 2 scènes

## Scène grapheur

1. **Créer** une nouvelle scène et **renommer** le _label_ de la première scène en ```sceneGrapher``` et le _nom_ avec ```Grapheur``` puis déployer

2. **Définir** l'acteur principal avec un acteur _empilement_ qui contiendra uniquement le grapheur

    * renommer le _Label_ avec ```stackRoot```

3. **Ajouter** un acteur enfant de type _Grapheur_

    * renommer le _Label_ avec ```grapher```
    * réinitialiser la propriété _Gabarit > Hauteur_ avec la valeur par défaut ```[vide]```
    * modifier la propriété _Position > Align. vertical_ en ```Etendre```

## Scène agenda

1. **Créer** une nouvelle scène et **renommer** le _label_ de la première scène en ```sceneAgenda``` et le _nom_ avec ```Agenda``` puis déployer

2. **Définir** l'acteur principal avec un acteur _empilement_ qui contiendra uniquement le grapheur

    * renommer le _Label_ avec ```stackRoot```

3. **Ajouter** un acteur enfant de type _Agenda_

    * renommer le _Label_ avec ```agenda```
    * réinitialiser la propriété _Gabarit > Hauteur_ avec la valeur par défaut ```[vide]```
    * modifier la propriété _Position > Align. vertical_ en ```Etendre```