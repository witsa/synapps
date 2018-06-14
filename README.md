# Home

[Home](sitemap.md)

![SynApps](assets/LogoSynApps128.png)

## **SynApps**: WIT tool to **build ambitious apps** for **REDY**

1. SynApps est le **nouveau outil** de construction d'applications web connectées au REDY. Il respecte les **standards** du WEB notamment dans sa capacité à s'adapter aux différentes tailles d'écrans et smartphones. Il ne s'agit pas d'une simple évolution des synoptiques mais d'une **rupture** complète dans la façon de construire des applications !

2. Les utilisateurs ciblés par les applications générées par SynApps sont **tous les occupants** du batiment équipés par nos gammes d'UTL REDY (et pas seulement les responsables d'exploitation): SynApps s'inscrit dans une démarche **Smart Building** et à pour ambition de répondre à ces **nouveaux usages**

3. SynApps est constitué de 2 web apps distinctes:
    * Le **MAKER**: outil de *construction* et de *déploiement*
    * Le **RUNTIME**: app d'exécution des SynApps

4. SynApps entre en phase de **BETA PREVIEW** pour évaluation de juin à Octobre 2018. Il va encore évoluer largemment mais nous garantissons le portage de toutes les applications créées pendant cette phase vers les prochaines versions

    _Attention:_ **aucune SynApp ne doit être déployé en production sur site** sans en informer WIT: nous vous invitons à **contacter notre support** pour toute question relative à ce sujet

## Modes de déploiement

A ce jour, les modes de distributions des MAKER et RUNTIME sont Web sur notre cloud « RIA » ainsi qu’embarqué dans le REDY concernant le RUNTIME uniquement

A terme, **SynApps MAKER** sera distribué sous la forme d'un éxécutable, avec installeur, sur les principales plateformes desktop, notamment _Windows_, _Mac_ et _Linux_ et ne sera plus accessible via notre cloud. La raison principale étant de donner un accès aux *ressources* locales: dossiers, images

De même, **SynApps RUNTIME**  sera également distribué pour les plateformes, _Windows_, _Android_ et _IOS_, sous la forme d'une application **hybride** (= WebApp embarquée dans natif) installée ou déployée dans les stores _Google Play_, _App Store_ et _Windows_

| Mode                            | MAKER | RUNTIME |  DISPONIBILITE   |
|---------------------------------|-------|---------|------------------|
| Web cloud RIA                   |  [x]  |   [x]   | Oui              |
| Web embarqué dans REDY          |  [ ]  |   [x]   | Oui              |
| Windows                         |  [x]  |   [x]   | Octobre 2018     |
| Linux                           |  [x]  |   [x]   | Date non définie |
| Mac                             |  [x]  |   [x]   | Date non définie |
| Android (APK: fichier installé) |  [ ]  |   [x]   | Fin 2018         |
| Android (Store)                 |  [ ]  |   [x]   | Date non définie |
| IOS (Store)                     |  [ ]  |   [x]   | Date non définie |

## Distributions

Actuellement **MAKER** et **RUNTIME** sont distribués uniquement en interne. Vous pouvez nous contacter si vous souhaitez participer à la phase de BETA PREVIEW

Les **modalités commerciales** de SynApps seront précisées en Octobre 2018 à l'issue de la phase d'évaluation

## Changelog

Le contenu des différentes versions de SynApps sont consultables dans la [changelog](changelog.md). La version actuelle **1.3.9**

## Issues

Les **bugs** relevés, **questions** ou **demandes d'évolutions** doivent remonter via le [gestionnaire d'issues GitHub](https://github.com/witsa/synapps/issues). Il est d'un accès simple et permet notamment d'être notifié, suivre l'évolution des issues, et partager auprès des autres utilisateurs

Essayer d'être le plus **exhaustif** possible et communiquer, quand c'est possible, étapes de reproduction d'un bug, copies d'écrans et description détaillée !

Dans un second temps, vous pouvez également contacter le **support** WIT

## Tutoriaux

Nous recommendons fortemment de découvrir SynApps avec les [tutoriaux](tutos/index.md). Ils permettent de comprendre et mettre en oeuvre tous les **concepts et mécanismes** de SynApps de manière **itérative**. A l'issue des tutoriaux proposés vous aurez une **vision avancée** de SynApps et serez à même de réaliser des **applications** webs évoluées **multi-plateformes**

## A vous de jouer !

Mais au préalable: [installer l'environnement](install.md)