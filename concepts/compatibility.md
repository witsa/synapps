---
title: "Compatibilité"
parent: Concepts
---

# Compatibilités

## Synapps Runtime

Le moteur d'exécution de Synapps, le Runtime est compatible avec tous les navigateurs modernes.

Voici un tableau des versions de navigateurs les plus anciennes que le runtime supporte :

| Navigateur | Version |
|----------- |---------|
| Chrome     | 60      |
| Firefox    | 55      |
| Edge       | 79      |
| Safari     | 11.1    |
| Safari iOS | 11.3    |
| Opera      | 47      |

En ce qui concerne les appareils nomades, il faudra veiller à utiliser les version minimales suivantes :

| Système    | Version |
|------------|---------|
| Android    | *Oreo* `8.0` (ou `6.0.1` si mise à jour de chrome possible à ≥ `60`) |
| iOS        | 11.3    |


### Versions du Runtime embarquées dans REDY

| REDY   | Runtime | Studio |
|--------|---------|--------|
| 16.3.0 | 2.7.1   | 1.4.1  |
| 16.2.0 | 2.7.0   | 1.4.0  |
|        | 2.6.1   |        |
| 16.1.0 | 2.6.0   | 1.3.0  |
|        | 2.5.1   | 1.2.1  |
| 14.5.2 | 2.5.0   | 1.2.0  |
| 14.4.1 | 2.4.1   | 1.1.6  |
| 14.4.0 | 2.4.0   | 1.1.5  |
| 14.3.2 | 2.3.3   | 1.1.4  |
| 14.2.3 | 2.3.2   | 1.1.2  |
| 14.2.2 | 2.3.1   | 1.1.0  |

## Synapps Studio

Synapps Studio fonctionne sur *Windows 10* et les versions suivantes.

Un PC de puissance moyenne suffit pour son exécution. Le périmètre des caractéristiques requises sont en cours de définition mais il apparaît déjà que Synapps Studio tournera convenablement sur des systèmes ayant
- `4Go`de RAM mimum, `8Go` recommandé,
- processeurs à 4 cœurs ou plus
- `600Mo` d'espace lible au moins
- Résolution d'écran `1080p` recommandé

Il faudra bien entendu de l'espace libre suplémentaire sur votre disque dur pour accueillir les fichiers de projet.

> | Studio     | Incompatibilité |
> |------------|-----------------|
> | ≥ `1.4.0`  | **⚠️ Incompatibilité avec les anciènnes versions**<br>Un projet ouvert avec cette version de Studio ne pourra plus être ouvert avec une version antérieure.<br>C'est le cas aussi pour un export de modèle : un modèle exporté avec cette version ne pourra pas être importé dans une version antérieure. |
> | < `1.4.0` | **⚠️Incompatibilité avec les lecteurs réseau**<br> N'utiliser pas de lecteur réseau pour accueillir vos projets. En effet, les versions précédentes de Studio n'arrivent pas à récupérer les dossiers présents sur ce type de lecteur. |

### Compatibilités avec REDY

Voici un tableau des versions de REDY que Studio est capable de gérer :

| Studio | REDY   |
|--------|--------|
| 1.4.1  | 16.3.0 |
| 1.4.0  | 16.2.0 |
| 1.3.0  |        |
| 1.2.1  |        |
| 1.2.0  | 14.5.2 |
| 1.1.6  | 14.4.1 |
| 1.1.5  | 14.4.0 |
| 1.1.4  | 14.3.2 |
| 1.1.2  | 14.2.3 |
| 1.1.0  | 14.2.2 |


### Versions du Runtime embarquées dans Studio

| Studio | Runtime |
|--------|---------|
| 1.4.1  | 2.7.1   |
| 1.4.0  | 2.7.0   |
| 1.3.0  | 2.6.0   |
| 1.2.1  | 2.5.1   |
| 1.2.0  | 2.5.0   |
| 1.1.6  | 2.4.1   |
| 1.1.5  | 2.4.0   |
| 1.1.4  | 2.3.3   |
| 1.1.2  | 2.3.2   |
| 1.1.0  | 2.3.1   |
