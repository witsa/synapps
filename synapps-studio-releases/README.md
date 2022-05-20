---
nav_order: 30
---

# Synapps Studio

Télécharger la version actuelle [1.1.1](https://github.com/witsa/synapps/releases/download/1.1.1/synapps-studio-setup.zip)

Voir la [Note de version](./notes/1.1.1){:target="_blank"}

# Historique des versions

| Version | Date |
|---------|-----|-|
{% for release in site.data.releases %}| [**{{ release.version }}**]({{ release.notes }}{{ release.version }}){:target="_blank"} | {{ release.date }} |
{% endfor %}
