[Accueil](../../) / [Tutoriaux](../index.md) / [Tutorial 07](index.md)

# Tutorial 7: les acteurs métiers natifs du REDY - Part 3: **Agenda**, **Grapheur** et **plus...**

Dans ce tutorial, nous allons utiliser les acteurs **grapheurs** et **agenda** qui ne nécessitent pas une configuration particulière. Nous allons les intégrer simplement dans 2 scènes sans barres de commandes

Nous allons également intégrer le **tableau de bord multi-énergies** du REDY !

## Scène **grapheur**

1. **Créer** une nouvelle scène et **renommer** le _label_ de la première scène en ```sceneGrapher``` et le _nom_ avec ```Grapheur``` puis déployer

2. **Définir** l'acteur principal avec un acteur _Empilement_ qui contiendra uniquement le grapheur

    * renommer le _Label_ avec ```stackRoot```

3. **Ajouter** un acteur enfant de type _Grapheur_

    * renommer le _Label_ avec ```grapher```
    * réinitialiser la propriété _Gabarit > Hauteur_ avec la valeur par défaut ```[vide]```
    * modifier la propriété _Position > Align. vertical_ en ```Etendre```

## Scène **agenda**

1. **Créer** une nouvelle scène et **renommer** le _label_ de la première scène en ```sceneAgenda``` et le _nom_ avec ```Agenda``` puis déployer

2. **Définir** l'acteur principal avec un acteur _Empilement_ qui contiendra uniquement le grapheur

    * renommer le _Label_ avec ```stackRoot```

3. **Ajouter** un acteur enfant de type _Agenda_

    * renommer le _Label_ avec ```agenda```
    * réinitialiser la propriété _Gabarit > Hauteur_ avec la valeur par défaut ```[vide]```
    * modifier la propriété _Position > Align. vertical_ en ```Etendre```

## Scène **tableau de bord multi-énergies**

L'approche est différente car SynApps ne dispose pas (encore) d'acteur _Tableau de bord multi-energies_ contrairement aux _Grapheurs_ et _Agendas_. Nous allons donc intégrer le contenu du tableau de bord du REDY via un acteur IFrame

_Remarque:_ il est déconseillé d'intégrer directement du contenu extérieur via SynApps afin de garantir une expérience utilisateur optimum. Mais c'est parfois beaucoup plus rapide voir nécessaire lorsque les fonctionnalités de SynApps ne sont pas suffisantes

1. **Créer** une nouvelle scène et **renommer** le _label_ de la première scène en ```sceneDashboard``` et le _nom_ avec ```Tableau de bord énergies``` puis déployer

2. **Définir** l'acteur principal avec un acteur _Empilement_ qui contiendra uniquement le grapheur

    * renommer le _Label_ avec ```stackRoot```

3. **Ajouter** un acteur enfant de type _IFrame_ qui contiendra le contenu du _Tableau de bord multi-energies_ du REDY

    * renommer le _Label_ avec ```iframeDashboard```
    * réinitialiser la propriété _Gabarit > Hauteur_ avec la valeur par défaut ```[vide]```
    * modifier la propriété _Position > Align. vertical_ en ```Etendre```
    * définir la propriété _Spécifiques > URL_ avec l'adresse du tableau de bord multi-énergies, du type

        ```TEXT
        http://127.0.0.1/WSID1347025956/easy/Dashboard-1
        ```

        _Remarque:_ pour connaître l'URL du tableau de bord: ouvrir l'écran d'_exploitation_ du REDY sur l'onglet _tableau de bord_ puis cliquer  sur le **bouton** ouvrant le tableau de bord dans une nouvelle fenêtre

        ![dashboard_link](/assets/dashboard_link.png)

        Copier l'URL dans la nouvelle fenêtre du navigateur
        ![dashboard_link2](/assets/dashboard_link2.png)

        Coller l'URL dans la propriété _Spécifiques > URL_
        ![preview_iframe](/assets/preview_iframe.png)

4. **Supprimer** la session dans la configuration du REDY, et recharger la SynApp (F5), vous constatez alors que le tableau de bord n'est plus affiché. En effet l'URL copié ci-dessus contient le numéro de session **WSID**. Lorsque ce dernier est expiré, l'IFrame est vide !

    De même, si nous exportons le paramétrage sur un REDY avec une **IP autre** que 127.0.0.1, le tableau de bord ne ne sera pas localisé

    Nous devons donc modifier l'URL pour la construire en fonction du **numéro de session WSID** et **IP** actuels

5. **Sélectionner** l'acteur ```iframeDashboard```

    * Modifier la propriété _Spécifiques > URL_ avec le texte suivant

        ```TEXT
        {% raw %}{{host}}{% endraw %}/WSID{% raw %}{{sid}}{% endraw %}/easy/Dashboard-1
        ```

    * compléter le contenu en créant les propriétés additionnelle _host_ et _sid_ de type _texte_

    * Lier en _interne_ la propriété _Spécifiques > host_ créée vers la propriété _Url hôte_ de l'objet _Hôte_ en _lecture_ uniquement
        ![bind_host](/assets/bind_host.png)

    * Lier en _interne_ la propriété _Spécifiques > sid_ créée vers la propriété _Url hôte_ de l'objet _Hôte_ en _lecture_ uniquement
        ![bind_host](/assets/bind_sid.png)

    * Le tableau de bord multi-énergies est de nouveau affiché dans la zone de prévisualisation !

6. **Supprimer** de nouveau la session dans la configuration du REDY, et recharger la SynApp (F5), vous constatez alors que le tableau de bord est toujours affiché. L'URL est bien construite avec le nouveau WSID !

## Que retenir

Nous avons mis en oeuvre 3 acteurs métiers:

* **Grapheur** et **Agenda** sont définis nativement dans SynApps et leurs intégrations est simple et fonctionne en l'état sans configuration particulière

* **Tableau de bord multi-énergies** n'existe pas nativement dans SynApps mais dans le REDY. L'acteur IFrame permet, sans trop de difficultés, son intégration dans SynApps: nous avons du construire l'URL du tableau de bord avec le numéro de session WSID ainsi que l'IP de l'hôte REDY

_Remarque:_ pour ce dernier, nous aurions également pu construire un nouvel acteur **composite** _Tableau de bord multi-énergies_ et permettre ainsi sa **réutilisation** et son **partage** comme n'importe quel acteur natif métiers !

## Conclusion

La **troisième partie du tutorial 7** portant est **terminée**. Nous avons construit 3 scènes simples avec le **grapheur**, l'**agenda** et le **tableau de bord multi-énergies**

Nous allons maintenant intégrer les 5 scènes créées dans une nouvelle scène de navigation pour **finaliser** l'application d'exploitation !

Vous pouvez remonter les **bugs** & **remarques** concernant ce tutorial, SynApps RUNTIME & MAKER sur [GitHub](https://github.com/witsa/synapps/issues)

[Tutoriel suivant](part4.md)
