---
nav_order: 30
lang: en
permalink: /synapps-studio-releases
---

# Synapps Studio

Download the current version [1.2.0](https://github.com/witsa/synapps/releases/download/1.2.0/synapps-studio-setup.zip)

See the [Release Note](./notes/1.2.0){:target="_blank"}

# Release History

| Version | Date |
|---------|-----|-|
{% for release in site.data.releases %}| [**{{ release.version }}**]({{ release.notes }}{{ release.version }}){:target="_blank"} | {{ release.date }} |
{% endfor %}
