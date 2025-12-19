---
title: Copier/coller acteur, scène ou composite
parent: Tutoriels
---

L'action de copier/coller un acteur, une scène ou un composite est une fonctionnalité *phare* de Synapps Studio. Elle permet de gagner du temps et de partager des éléments entre plusieurs synapps ou entre plusieurs utilisateurs.

Même si elles demeurent assez intuitives, nous allons voir ici comment réaliser ces actions.

# Copier/Coller un acteur

Pour copier un acteur, il suffit de réaliser un clic droit sur l'acteur et de sélectionner l'option *Copier*.

![Acteur texte](../assets/tutorials/copy-paste-actor-scene-composite/picture-01.png)

**La définition de l'acteur est dans le press-papier.** Vous pouvez maintenant coller l'acteur dans un autre acteur, dans une autre scène, dans un autre projet ou bien dans un mail pour le partager.

Pour coller l'acteur, il suffit de réaliser un clic droit sur un acteur de disposition et de sélectionner l'option *Coller*. Vous pouvez aussi réaliser un clic droit sur un acteur quelconque, l'acteur créer sera placé dans la même disposition que l'acteur ciblé.

![Acteur texte](../assets/tutorials/copy-paste-actor-scene-composite/picture-02.png)

# Copier/Coller une scène

Pour copier une scène, il suffit de réaliser un clic droit sur la scène et de sélectionner l'option *Copier*.

![Acteur texte](../assets/tutorials/copy-paste-actor-scene-composite/picture-03.png)

Comme dans le cas de l'acteur, **la scène est dans le press-papier**. Vous pouvez maintenant coller la scène dans un autre dossier, dans un autre projet ou bien dans un mail pour le partager.

{: .info }
> C'est d'ailleurs ainsi que sont créées les [scènes remarquables](../concepts/scene.md#scènes-remarquables) proposées dans cette documentation.

Pour coller la scène, il suffit de réaliser un clic droit sur un dossier et de sélectionner l'option *Coller*. Vous pouvez aussi réaliser un clic droit sur une scène quelconque, la scène créée sera placée dans le même dossier que la scène ciblée.

![Acteur texte](../assets/tutorials/copy-paste-actor-scene-composite/picture-04.png)


# Copier/Coller un composite

Pour copier un composite, c'est le même principe que pour une scène. Il suffit de réaliser un clic droit sur le composite et de sélectionner l'option *Copier* et de coller en réalisant un clic droit sur un dossier et de sélectionner l'option *Coller*.

{: .info }
> C'est ainsi, également, que sont créés les [composites remarquables](../concepts/composite.md#composites-remarquables) proposés dans cette documentation.


# Quelques remarques

{: .warning }
> Certains logiciels ont un formatage automatique lorsqu'on colle du texte dedans. Par exemple **Microsoft Teams** a tendance à ajouter des caractères de formatage qui vont perturber le collage dans Studio.

{: .tip }
> Pour le partage, nous recommandons d'utiliser un fichier *texte brut* dans lequel vous glissez ce que vous avez copié.

{: .tip }
> Vous pouvez également réaliser des **couper/coller** qui ont pour effet de copier l'élément et de le supprimer de l'endroit d'origine. Pour cela, il suffit de réaliser un clic droit sur l'élément et de sélectionner l'option *Couper*. C'est une autre manière de déplacer un élément dans un autre endroit.

{: .warning }
> Les liaisons sont copiées mais pas leurs cibles. Ainsi des liaisons vers des librairies ne fonctionne plus lors du collage. Si vous coller un acteur qui utilise une librairie, il faudra la définir dans le projet.
