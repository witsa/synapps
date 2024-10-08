---
title: Documentation Maker
has_children: true
nav_order: 50
search_exclude: true
---

<br>
<br>
<br>

> ⚠️ **Avertissement**<br>
> Ceci est la documentation du précurseur de Synapps Studio. Cette ancienne génération n'est plus maintenue.


<br>
<br>
<br>

{% include table_of_content.html %}

[Plan du site](./sitemap.md)

# Accueil

![SynApps](assets/LogoSynAppsForREDY128.png)

## **SynApps**: construisez des apps **multiplateformes** avec le **REDY**

SynApps est le **nouvel outil** de construction d'applications web avec le REDY. Il respecte les **standards** du WEB de manière à profiter des fonctionnalités modernes des navigateurs comme, entre autres, la capacité à s'adapter aux différentes tailles d'écrans et smartphones. Il ne s'agit pas d'une simple évolution des synoptiques mais d'une **rupture** complète dans la façon de construire des applications !

![SynApps](assets/WHomeApp.gif)

Les utilisateurs ciblés par les applications générées par SynApps sont **tous les acteurs** du bâtiment (occupants, gestionnaires, exploitants, …) équipés par nos gammes d'UTLs REDY: SynApps s'inscrit dans une démarche **Smart Building** et à pour ambition de répondre à ces **nouveaux usages**

SynApps est constitué de 2 web apps distinctes:

* Le **MAKER**: outil de *construction* et de *déploiement*
* Le **RUNTIME**: app d'exécution des SynApps

SynApps entre en phase de **BETA PREVIEW** pour évaluation de juin à fin 2018. Il va encore évoluer largement mais nous garantissons le portage de toutes les applications créées pendant cette phase vers les prochaines versions

_Attention:_ **aucune SynApp ne doit être déployée en production sur site** sans en informer WIT: nous vous invitons à **contacter notre support** pour toute question relative à ce sujet

## Modes de déploiement

A ce jour, **MAKER** et le **RUNTIME** sont des applications Web hébergées sur notre cloud « RIA ». Seul le **RUNTIME** est embarqué dans le REDY

A terme, **SynApps MAKER** sera distribué sous la forme d'un éxécutable, avec installeur, sur les principales plateformes desktop, notamment _Windows_, _Mac_ et _Linux_ et ne sera plus accessible via notre cloud. La raison principale étant de donner un accès aux *ressources* locales: dossiers, images

De même, **SynApps RUNTIME** sera également distribué pour les plateformes, _Windows_, _Android_ et _IOS_, sous la forme d'une application **hybride** (= WebApp embarquée dans natif) installée ou déployée dans les stores _Google Play_, _App Store_ et _Windows_

| Mode                            | MAKER | RUNTIME |  DISPONIBILITE   |
|---------------------------------|-------|---------|------------------|
| Web cloud RIA                   |  [x]  |   [x]   | Oui              |
| Web embarqué dans REDY          |  [ ]  |   [x]   | Oui              |
| Windows                         |  [x]  |   [x]   | Novembre 2018    |
| Linux                           |  [x]  |   [x]   | Date non définie |
| Mac                             |  [x]  |   [x]   | Date non définie |
| Android (APK: fichier installé) |  [ ]  |   [x]   | Fin 2018         |
| Android (Store)                 |  [ ]  |   [x]   | Date non définie |
| IOS (Store)                     |  [ ]  |   [x]   | Date non définie |

## Distributions

Actuellement **MAKER** et **RUNTIME** sont distribués uniquement en interne. Vous pouvez nous contacter si vous souhaitez participer à la phase de `BETA PREVIEW`.

Les **modalités commerciales** de SynApps seront précisées fin 2018 à l'issue de la phase d'évaluation

## Propriété et confidentialité

Toutes les SynApps sont déployées sur vos REDY/REDY-PC, les données produites via SynApps MAKER restent donc **votre propriété**

_Remarque:_ pendant la phase de `BETA PREVIEW` nous envoyons des statistiques d'**usages** ainsi que bugs de SynApps MAKER sur la plateforme _Google Analytics_ afin de nous aider à améliorer le produit. Ces statistiques ne contiennent **en aucune manière** les configurations de vos SynApps ou infos provenant de vos UTLs

## Changelog

Le contenu des différentes versions de SynApps sont consultables dans la [changelog](changelog.md).

## Issues

Les **bugs** relevés, **questions** ou **demandes d'évolutions** doivent remonter via le [gestionnaire d'issues GitHub](https://github.com/witsa/synapps/issues). Il est d'un accès simple et permet notamment d'être notifié, suivre l'évolution des issues, et partager auprès des autres utilisateurs

Essayer d'être le plus **exhaustif** possible et communiquer, quand c'est possible, étapes de reproduction d'un bug, copies d'écrans et description détaillée!

Dans un second temps, vous pouvez également contacter le **support** WIT

## Tutoriels

Nous recommandons **fortement** de découvrir SynApps avec les [tutoriels](tutos/index.md). Ils permettent de comprendre et mettre en oeuvre tous les **concepts et mécanismes** de SynApps de manière **itérative**. A l'issue des tutoriels proposés vous aurez une **vision avancée** de SynApps et serez à même de réaliser des **applications** webs évoluées **multi-plateformes**


## Pratiques et équipements nomades *(...en construction...)*

Vous trouverez des [bonnes et les mauvaises pratiques](practices/index.md) que l'on peut avoir avec SynApps et mêmes des éléments fondamentaux à savoir à propos du design d'application dédiée aux équipements nomades.


## A vous de jouer !

Mais au préalable: [installer l'environnement](install.md)
