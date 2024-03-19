---
title: "Afficher un PDF dans une iFrame"
parent: Afficher un PDF
grand_parent: Tutoriels
has_children: false
nav_order: 1
---

Dans ce tutoriel, nous allons apprendre à afficher un PDF depuis le REDY directement dans une iFrame au sein de la Synapp.
Il faut savoir que les navigateurs disposent de leur propre visualiseur de PDF et il n'est donc <b> pas possible </b> de modifier celui-ci.

Par convention, les PDF dans le REDY se situent à l'adresse : <b> /WEB/IMG/nom-de-mon-pdf </b>

# Afficher un PDF dans une iframe

## Étape 1 - Ajouter l'acteur iFrame

Commençons par ajouter un acteur iFrame et étendons le sur toute la longueur.

![Synapps](../../assets/tutorials/pdf/add-iframe.gif)

## Étape 2 - Construire l'URL

L'iFrame nécessite une URL à laquelle accéder afin d'afficher le PDF.

Nous allons avoir besoin de plusieurs informations afin de construire cette URL :

- Le WSID de la session utilisateur qui permet à l'iFrame d'être identifiée auprès du REDY
- Le chemin vers le PDF

Nous allons utiliser des [jokers](../tutorials/jokers-in-text.md) afin de construire l'URL dynamiquement.

Le contenu de la propriété _url_ de l'iFrame est donc : <b> /WSID\{\{wsid\}\}/WEB/IMG/\{\{pdfName\}\}.pdf </b>


Cette url est composée d'un joker  <b>_wsid_</b> afin de récupérer l'identifiant de la session de l'utilisateur et le second <b>_pdfName_</b> qui représente le label du PDF dans le REDY.

> 📌 **REMARQUE**<br>
Le label du pdf dans le REDY n'est <b> pas </b> le nom de fichier du PDF.

## Étape 3 - Renseigner les additionnelles

Nous allons donc créer deux additionnelles afin de renseigner des valeurs à nos jokers.

![Synapps](../../assets/tutorials/pdf/add-additionals-iframe.gif)


Il faut renseigner à l'additionnelle <b> _wsid_ </b> l'identifiant de session, il suffit de lui renseigner la liaison suivante :

![Synapps](../../assets/tutorials/pdf/wsid.png)

La seconde additionnelle devra être renseignée pour correspondre au pdf que l'on souhaite ouvrir dans le REDY.
Dans ce tutoriel, le fichier PDF a pour label *FILE0001*.

> 📌 **REMARQUE**<br>
Le label du pdf dans le REDY n'est <b> pas </b> le nom de fichier du PDF.

## Résultat

> Affichage d'un PDF dans une iframe
>
> ![Synapps](../../assets/tutorials/pdf/preview.png)

# Scène du tutoriel

Vous pouvez copier/coller la scène réalisée dans ce tutoriel.

{% raw %}
```
SYNAPPS-STUDIO-SCENE|{"config":{"key":"scene1","name":"Scène 1"},"leadActor":{"type":"layout/stack","key":"stack1","children":[{"type":"display/iframe","key":"iframe1","properties":{"verticalAlignment":"expand","url":"/WSID{{wsid}}/WEB/IMG/{{pdfName}}~pdf"},"additionalDefs":{"wsid":{"type":"text"},"pdfName":{"type":"text"}},"additionals":{"pdfName":""},"bindings":{"additionals.wsid":"session@sid"}}]}}
```
{% endraw %}
