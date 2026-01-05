# Documentation Synapps

[![GitHub](https://img.shields.io/badge/GitHub-Discussions-blue)](https://github.com/witsa/synapps/discussions)
[![Issues](https://img.shields.io/badge/GitHub-Issues-red)](https://github.com/witsa/synapps/issues)

Ce repository contient la documentation officielle de **Synapps**, la solution de construction d'imagerie pour le REDY développée par WIT.

## 🌐 Documentation en ligne

La documentation est disponible en ligne : [https://witsa.github.io/synapps/](https://witsa.github.io/synapps/)

## 📚 À propos de Synapps

Synapps est la **nouvelle solution** de WIT de construction d'imagerie pour le REDY. La solution respecte les **standards** du WEB pour profiter des fonctionnalités modernes des navigateurs comme, entre autres, la capacité à s'adapter aux différentes tailles d'écrans et smartphones.

### Synapps Studio

Véritable environnement de développement intégré (IDE), Synapps Studio est l'outil de *construction* et de *déploiement* qui permet de :
- Construire des applications WEB avec des outils d'édition d'interface simples et intuitifs
- Tester l'exécution de l'application sur des ULIs
- Déployer vos applications dans des ULIs

## 🛠️ Développement local

Cette documentation est construite avec [Jekyll](https://jekyllrb.com/) et utilise le thème [Just the Docs](https://just-the-docs.github.io/just-the-docs/).

### Prérequis

- Ruby (version 2.7 ou supérieure)
- Bundler

### Installation

```bash
# Installer les dépendances
bundle install

# Lancer le serveur de développement
npm run serve
# ou
bundle exec jekyll serve --config ./_config.yml,./_config_dev.yml --safe
```

La documentation sera accessible à l'adresse : `http://localhost:4000/synapps/`

### Build de production

```bash
npm run build
# ou
bundle exec jekyll build --config ./_config.yml,./_config_dev.yml --safe
```

## 🤝 Contribuer

### Discussions et échanges

La plateforme de [discussion de GitHub](https://github.com/witsa/synapps/discussions) est ouverte à tous les utilisateurs pour poser des questions, proposer des idées, partager vos créations ou tout simplement discuter de la solution.

### Problèmes et demandes d'évolution

Utilisez [GitHub Issues](https://github.com/witsa/synapps/issues) pour :
- Signaler un bug dans la documentation
- Proposer une amélioration
- Demander des clarifications

Essayez d'être le plus **exhaustif** possible et communiquez, quand c'est possible, les étapes de reproduction d'un bug, copies d'écran et description détaillée !

### Directives de contribution

1. Fork le repository
2. Créez une branche pour votre modification (`git checkout -b feature/amelioration-doc`)
3. Committez vos changements (`git commit -m 'Amélioration de la section X'`)
4. Poussez vers la branche (`git push origin feature/amelioration-doc`)
5. Ouvrez une Pull Request

## 📝 Structure du projet

```
.
├── _config.yml           # Configuration Jekyll
├── _includes/           # Composants réutilisables
├── _layouts/            # Templates de page
├── assets/              # Images, CSS, JS
├── collections/         # Collections Jekyll
├── concepts/            # Documentation des concepts
├── quick-start/         # Guide de démarrage rapide
├── script-api/          # Documentation de l'API de script
├── tutorials/           # Tutoriels
└── maker/               # Documentation de Synapps Maker (legacy)
```

## 📄 Licence

Documentation développée par [WIT](https://www.wit.fr)

## 💬 Support

Pour toute question ou problème :
- Consultez la [documentation en ligne](https://witsa.github.io/synapps/)
- Rejoignez les [discussions GitHub](https://github.com/witsa/synapps/discussions)
- Créez une [issue](https://github.com/witsa/synapps/issues)
- Contactez le support WIT
