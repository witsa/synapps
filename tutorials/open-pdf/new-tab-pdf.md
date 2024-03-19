---
title: "Afficher un PDF dans un nouvel onglet"
parent: Afficher un PDF
grand_parent: Tutoriels
has_children: false
nav_order: 2
---

Dans ce tutoriel, nous allons apprendre à configurer un acteur bouton afin qu'il ouvre un PDF dans un nouvel onglet.

Par convention, les PDF dans le REDY se situent à l'adresse : <b> /WEB/IMG/nom-de-mon-pdf </b>

# Afficher un PDF dans un nouvel onglet

## Étape 1 - Créer le bouton

Commençons par ajouter un acteur bouton qui servira à ouvrir le PDF.

![Synapps](../../assets/tutorials/pdf/add-button.gif)

## Étape 2 - Ajouter les additionnelles

Nous allons nous baser sur deux additionnelles afin de composer l'URL qui sera ouverte par le bouton.

Il y aura donc 2 additionnelles de type *texte*.
- La première se nomme *wsid* et représente l'identifiant qui permet au REDY d'authentifier la provenance de la requête.
- La seconde se nomme *pdfName* et représente le label du PDF dans le REDY.

> 📌 **REMARQUE**<br>
Le label du pdf dans le REDY n'est <b> pas </b> le nom de fichier du PDF.

![Synapps](../../assets/tutorials/pdf/button-additionals.png)