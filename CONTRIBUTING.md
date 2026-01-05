# Guide de contribution

Merci de votre intérêt pour contribuer à la documentation Synapps ! Ce document vous guidera à travers le processus de contribution.

## Comment contribuer

### Signaler un problème

Si vous trouvez une erreur dans la documentation, vous pouvez :

1. Créer une [issue GitHub](https://github.com/witsa/synapps/issues/new) en décrivant le problème
2. Utiliser le bouton "❔ Posez une Question" ou "💡 Proposez une Suggestion" disponible sur chaque page de documentation
3. Participer aux [discussions GitHub](https://github.com/witsa/synapps/discussions)

### Proposer une amélioration

Pour proposer une amélioration de la documentation :

1. **Forker** le repository
2. **Créer une branche** pour votre modification :
   ```bash
   git checkout -b amelioration/description-courte
   ```
3. **Faire vos modifications** en respectant les conventions décrites ci-dessous
4. **Tester localement** vos modifications (voir section "Développement local")
5. **Committer** vos changements avec un message clair :
   ```bash
   git commit -m "Amélioration: correction de la section X"
   ```
6. **Pousser** vers votre fork :
   ```bash
   git push origin amelioration/description-courte
   ```
7. **Ouvrir une Pull Request** vers le repository principal

## Conventions de documentation

### Structure des fichiers Markdown

Les fichiers Markdown doivent contenir un en-tête YAML (front matter) :

```yaml
---
title: "Titre de la page"
parent: "Nom du parent" # optionnel
grand_parent: "Nom du grand-parent" # optionnel
nav_order: 1 # optionnel
---
```

### Style d'écriture

- **Ton** : Utiliser le vouvoiement ("vous") pour s'adresser au lecteur
- **Verbes** : Utiliser l'infinitif pour les titres et instructions ("Créer un projet", "Configurer l'environnement")
- **Concision** : Être clair et concis
- **Orthographe** : Utiliser le français correct, éviter les anglicismes
- **Ponctuation** : Utiliser des espaces insécables avant les deux-points, points d'exclamation et d'interrogation
- **Listes** : Utiliser des listes à puces pour les éléments non ordonnés et des listes numérotées pour les étapes séquentielles
- **Tutoriels** :
   - Tutoriel courts.
   - Expliquer dès le début l'objectif final.
   - Diviser en sections claires avec des titres
   - Fournir des exemples concrets et des captures d'écran lorsque c'est pertinent
   - Animations légères pour illustrer les étapes complexes et courtes ([Screen2Gif](https://www.screentogif.com/){:target="_blank"} recommandé)
   - Inclure des liens vers des ressources supplémentaires si nécessaire
   - Fournir les scènes ou composites créés dans le tutoriel à copier/coller dans Synapps Studio.

### Images

- **Alt text** : Toujours fournir un texte alternatif descriptif pour les images
  ```markdown
  ![Description claire de l'image](chemin/vers/image.png)
  ```
- **Format** : Préférer PNG pour les captures d'écran, SVG pour les diagrammes
- **Taille** : Optimiser les images avant de les ajouter
- **Gif animés** : Utiliser [Screen2Gif](https://www.screentogif.com/){:target="_blank"} pour créer des animations légères

### Liens

- **Liens internes** : Utiliser des chemins relatifs
  ```markdown
  [Voir la section acteurs](./concepts/actor.md)
  ```
- **Liens externes** : Ajouter `{:target="_blank"}` pour ouvrir dans un nouvel onglet
  ```markdown
  [Documentation externe](https://example.com){:target="_blank"}
  ```
- **Sécurité** : Préférer HTTPS à HTTP pour les liens externes

### Callouts (Encadrés)

Utiliser les callouts Jekyll pour mettre en évidence des informations importantes :

```markdown
{: .warning }
> Ecrira automatiquement ⚠️ **Attention**
> Message d'avertissement

{: .tip }
> Ecrira automatiquement 💡 **Astuce**
> Conseil pratique

{: .info }
> Ecrira automatiquement ℹ️ **Remarque**
> Information complémentaire

{: .important }
> Ecrira automatiquement 💎 **Important**
> Information cruciale

{: .pin }
> Ecrira automatiquement 📌 **À retenir**
> Point clé
```

### Code

Pour les blocs de code, toujours spécifier le langage :

```markdown
​```javascript
console.log("Hello World");
​```

​```json
{
  "key": "value"
}
​```
```

Le mieux est de les entourer par les instructions `{% raw %}` et `{% endraw %}` pour éviter que Jekyll n'essaie de les interpréter.

```markdown
{% raw %}
​```javascript
console.log("Hello World");
​```
{% endraw %}
```

## Développement local

### Prérequis

- Ruby 2.7 ou supérieur
- Bundler

### Installation

```bash
# Cloner le repository
git clone https://github.com/witsa/synapps.git
cd synapps

# Installer les dépendances
bundle install
```

### Lancer le serveur de développement

```bash
npm run serve
# ou
bundle exec jekyll serve --config ./_config.yml,./_config_dev.yml --safe
```

La documentation sera accessible à : `http://localhost:4000/synapps/`

### Build de production

```bash
npm run build
```

## Checklist avant de soumettre une PR

- [ ] Les modifications ont été testées localement
- [ ] Les liens fonctionnent correctement
- [ ] Les images ont des textes alternatifs descriptifs
- [ ] Le style d'écriture est cohérent avec le reste de la documentation
- [ ] Les fautes d'orthographe et de grammaire ont été corrigées
- [ ] Les espaces en fin de ligne ont été supprimés
- [ ] Les liens HTTP ont été remplacés par HTTPS quand possible
- [ ] Le front matter YAML est correct
- [ ] La navigation fonctionne correctement

## Bonnes pratiques

### Qualité

- Relire attentivement avant de soumettre
- Utiliser un correcteur orthographique
- Tester tous les liens
- Vérifier l'affichage sur différentes tailles d'écran

### Commits

- Un commit par modification logique
- Messages de commit clairs et descriptifs en français
- Préfixer les messages : "Fix:", "Amélioration:", "Ajout:", etc.

### Pull Requests

- Titre clair et descriptif
- Description détaillée des modifications
- Référencer les issues liées si applicable
- Répondre aux commentaires de révision rapidement

## Questions ?

Si vous avez des questions, n'hésitez pas à :

- Ouvrir une [discussion GitHub](https://github.com/witsa/synapps/discussions)
- Créer une [issue](https://github.com/witsa/synapps/issues)
- Consulter la [documentation en ligne](https://witsa.github.io/synapps/)

Merci pour votre contribution ! 🎉
