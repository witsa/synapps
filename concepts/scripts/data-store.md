---
title: "Magasin de donnée"
parent: Scripts
grand_parent: Concepts
---

{% include table_of_content.html %}

# Magasin de donnée

> ⚡ Par script : [référence du magasin REDY](./reference/data-store.md)

Le magasin de donnée fait le lien entre la synapp et le REDY auquel elle est connectée. Il charge et garde en mémoire les données du REDY (variables WOS, reflets, évènements, curseurs) et leur envoie les écritures et les commandes.

Les [fournisseurs de donnée]({{ site.baseurl }}/concepts/actor/#les-fournisseurs-de-donnée) et les acteurs à reflet passent par lui. Un script peut aussi l'utiliser directement.

## Accès par script

Le magasin du REDY est accessible dans tout script par `context.dataStores.redy` (et, depuis un acteur, par `this.dataStores.redy`).

{: .tip }
> Pour afficher, lier ou écrire une donnée, préférez un fournisseur de donnée : il gère la requête, le rafraîchissement et l'écriture. Le magasin sert aux besoins ponctuels d'un script.

## Ce qu'il permet

- **Variables WOS** : chercher, charger, recharger une [variable WOS]({{ site.baseurl }}/concepts/data-models/redy/wos-variable.html) et ses enfants, en écrire la valeur, rechercher des variables ou des ressources.
- **Reflets** : rechercher des reflets, obtenir un reflet déjà chargé, envoyer la commande d'un reflet.
- **Évènements** : rechercher des [évènements WOS]({{ site.baseurl }}/concepts/data-models/redy/wos-event.html) et les acquitter, rechercher des [évènements de reflet]({{ site.baseurl }}/concepts/data-models/redy/reflect-event.html).
- **Curseurs** (REDY Pilot) : lister les curseurs, exécuter un curseur de requête ou d'instruction.
- **Connexion** : l'[hôte](./reference/host.md), la [session](./reference/session.md) et la déconnexion (`logout()`).

Le détail de chaque méthode est dans la [référence du magasin REDY](./reference/data-store.md).
