# Tutorial 7: les acteurs métiers natifs du REDY - Part 2: **Etats**

[Home](../../sitemap.md) > [Tutoriaux](../index.md) > [Tutorial](index.md)

L'acteur état fonctionne également sans la moindre configuration. Plusieurs propriétés _spécifiques_ permettent de personnaliser et filtrer son rendu. Ces propriétés sont **explicites** et comme pour le journal nous ne rentrerons pas dans le détail de chacune d'entre elles !
![etats_properties](assets/etats_properties.png)

Nous allons intégrer l'acteur états dans une adaptation de la **scène évoluée** du journal précédente avec le même type de barre de commande permettant de configurer le **comportement** et les **filtres** des états

## Configuration de la scène

Plutot que de configurer une nouvelle scène, nous allons dupliquer la scène du journal précédente et l'adapter à l'acteur état

1. **Cloner** la scène ```sceneJournal``` et renommer le _label_ de la scène en ```sceneEtat``` et le _nom_ avec ```Etats avancés``` puis déployer

    ![clone_scene](assets/clone_scene.png)

2. **Sélectionner** l'acteur ```sceneJournal``` et supprimer le

    _Remarque:_ une erreur de script apparait car une fonction de transformation en lecture essaye de localiser le journal

3. **Déployer** et **appuyer** sur F5 pour rafraichir la scène: des erreurs de validation apparaissent sur la scène concernant les liaisons intenes, vers le journal, désormais invalides

    ![actors_invalid](assets/actors_invalid.png)

    * Par exemple sur l'acteur ```buttonFilters``` les propriétés _Sépcifiques > Ensemble_ et _Période_

      ![props_invalid](assets/props_invalid.png)

      _Remarque:_ ces erreurs sont normales car consécutivent à la suppression du journal et vont être corrigées

4. **Sélectionner** l'acteur ```stackRoot``` et **ajouter** un acteur enfant de type _Etat_

    * renommer le _Label_ avec ```etats```
    * modifier la propriété _Spécifiques > Align. vertical_ en ```Etendre```

5. **Sélectionner** l'acteur ```htmlInfo```

    * modifier la propriété _Spécifiques > Contenu_ avec le code HTML
      ```html
      Etats <span class="badge" style="font-size:1em">{% raw %}{{nbEtats}}{% endraw %}</span> ressources
      ```
    * compléter le contenu en créant la propriété additionnelle _nbEtats_ de type _nombre_

    * éditer les propriétés additionnelles dans _Additionnelles > Gestion des propriétés additionnelles_. Supprimer _nbEvents_ et définir nom et description de _nbEtats_

      ![props_invalid](assets/edit_props.png)

    * Lier en _interne_ la propriété _Spécifiques > Nombre d'états_ à la propriété  _Spécifiques > Nombre filtré_ de l'acteur ```etats``` en lecture uniquement

6. **Sélectionner** l'acteur ```switchButtonMode``` qui permettra désormais le passage du mode _tableau_ au mode _vignette_ de l'acteur ```etats```

    * modifier la propriété _Spécifiques > Text On_ avec le texte ```Tableau```
    * modifier la propriété _Spécifiques > Text Off_ avec le texte ```Vignette```  
    * modifier la propriété _Spécifiques > Style Off_ avec la sélection ```Info```

7. **Sélectionner** l'acteur ```periodFilter``` et supprimer le car il n'est pas utile dans le contexte de l'acteur ```etats```

8. **Sélectionner** l'acteur ```stackCmd``` et **ajouter** un acteur enfant de type _Boite de texte_ qui permettra de définir une zone de recherche dans les états

    * renommer le _Label_ avec ```textboxSearch```
    * réinitialiser la propriété _Gabarit > Largeur_ avec la valeur par défaut ```[vide]```
    * remonter la position de l'acteur entre ```switchButtonMode``` et ```buttonFilters```
      ![props_invalid](assets/actor_order.png)
    * modifier la propriété _Position > Align. horizontal_ en ```centré```
    * réinitialiser la propriété _Spécifiques > Valeur_ avec ```[vide]```
    * définir la propriété _Spécifiques > Texte d'aide_ avec ```Recherche```
    * définir la propriété _Spécifiques > Type d'input_ avec ```Recherche```
    * modifier la propriété _Spécifiques > Taille_ avec ```50px```

9. **Sélectionner** l'acteur ```buttonFilters``` et corriger les 2 liaisons

    * Lier en _interne_ la propriété _Spécifiques > selSet_ (ou nom personnalisé que vous avez défini) à la propriété  _Spécifiques > Ensemble_ de l'acteur ```états```

    * Editer le _Script de lecture_ de la propriété avec le javascript
    ```javascript
    const etats = context.synoStage.findByLabel('etats');
    return etats.get('setName');
    ```
    _Remarque:_ on récupère le nom de l'ensemble sélectionné comme pour le journal

    * Lier en _interne_ la propriété _Spécifiques > period_ (ou nom personnalisé que vous avez défini) à la propriété  _Spécifiques > Période_ de l'acteur ```états```

10. **Sélectionner** l'acteur ```htmlPeriod``` et corriger la liaison

    * Lier en _interne_ la propriété _Spécifiques > period_ (ou nom personnalisé que vous avez défini) à la propriété  _Spécifiques > Période_ de l'acteur ```états```

11. **Sélectionner** l'acteur ```etats``` et définir les liaisons

    * Lier la propriété _Spécifiques > Filtre du nom_ avec la propriété _Spécifiques > Valeur_ de ```textboxSearch```
