---
title: "Zone de texte"
parent: "Intéraction"
---

{% include links_actor.md apiClass="Actor.Input.TextArea" %}

# Zone de texte

L'acteur Zone de texte permet de renseigner du texte, il est généralement utilisé pour écrire du texte brut.

{% include table_of_content.html %}

# Propriétés spécifiques

**Valeur**

La propriété spécifique `Valeur` permet de définir la valeur actuelle de l'acteur.

La valeur attendue est un une chaine de caractère.

>📌 *REMARQUE*<br>
> Il n'est pas possible de décorer le texte au sein de cet acteur, pour ajouter de la décoration au texte il est préférable d'utiliser un acteur HTML.

**Taille**

{% include property_size.md %}

**Longueur Max**

Permet de limiter la taille de la chaine de caractère de `Valeur`.

>📌 *REMARQUE*<br>
> Le caractère vide 'espace' est comptabilisé comme tout autre caractère.

**Mode de saisie**

Ce champ permet de conditionner le type de clavier qui s'affiche sur les appareils mobiles et tablettes.

**Auto Completion?**

Permet d'activer / désactiver la saisie automatique sur les navigateurs.

**Lecture seule?**

Permet d'activer / désactiver la saisie de valeur dans le champ de saisie.

**État de validation**

Permet de donner une décoration prédéfinie au champ de saisie.

**Actif**

Permet d'activer / désactiver le champ de saisie.
