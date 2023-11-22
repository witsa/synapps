---
title: Installation
parent: Documentation Maker
has_children: true
nav_order: 1
search_exclude: true
---

# Installation

## Prérequis

Le minimum pour construire et déployer une SynApp est:

* Le **MAKER** qui est l'outil de construction et de déploiement de SynApps

* Un **REDY** ou un **REDY PC** en version **12.0.1** et **supérieure** sur lequel sera déployé la *SynApp*

## MAKER

Le MAKER est l'outil de construction et de déploiement de SynApps. Il est distribué sous la forme de:

1. **WebApp** via le cloud WIT: consulter l'**équipe SynApps** pour les modalités d'accès. Voir également la [matrice de compatibilité des navigateurs](browers.md)

2. Executable **Windows** avec un installeur:

    La version **Windows** de SynApps MAKER est programmée pour Novembre 2018

## RUNTIME

1. **WebApp** idem MAKER

2. **Android** vous pouvez éxécuter vos SynApps depuis un smartphone _Android_ [installer SynApps sur Android](install/android.md)

3. **iOs** vous pouvez éxécuter vos SynApps depuis un smartphone _iOs_ [installer SynApps sur iOs](install/ios.md)

## REDY PC

Dans un premier temps, nous suggérons d'utiliser un REDY PC. Vous pouvez-récupérer la dernière version dans la zone téléchargement du site WIT:
[télécharger REDY PC](https://www.wit.fr/telechargement-par-produits/download-info/redy-pc-logiciel/)

Procédure détaillée pour [installer un REDY PC](redy/install.md)

Exécuter **REDY-PC.exe** et double cliquer pour ouvrir le navigateur

![REDY PC](assets/redyPCexe.png)

## REDY

Les UTLs REDY en version **12.0.1** et supérieures sont déja compatibles SynApps. Si votre UTL est dans une version inférieur, une version du REDY compatible est disponible ici:

[Téléchargement soft REDY](https://www.wit.fr/telechargement-par-produits/download-tag/redy,logiciel/)

Procédure détaillée pour [mettre à jour le .K4PCK d'un REDY](redy/install.md)

## Mode RIA local

Les versions de SynApps **évoluent régulierement**. Il est préferable de désactiver le mode *Hébergement RIA local* pour forcer le chargement de la **dernière version** du *RUNTIME SynApps* depuis le cloud RIA

[Désactiver le mode *Hébergement RIA local* du REDY](redy/configure.md)

## Compatibilité des RUNTIME & MAKER

Voir la note concernant la [compatibilité des versions de SynApps MAKER et RUNTIME](versions.md) surtout si vous décidez de fonctionner en mode local (RUNTIME embarqué dans le REDY)

## Étapes suivantes

Vous avez le **MAKER** de *SynApps* (Windows ou cloud RIA) et un **REDY PC** (ou REDY) compatible avec SynApps **>=12.0.1**, nous pouvons commencer la création et le déploiement d'une première SynApp simple sur le REDY en suivant le _Tutorial 1_: **première SynApp “Helloworld”** !

[Tutoriels](tutos/index.md)
