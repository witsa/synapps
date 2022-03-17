{% assign property = include.property %}

## {{ property.title }}

{{ property.content | markdownify }}

> Chemin d'accès depuis l'acteur `{{ property.propPath }}` ([&#x1F4BB; Doc Script API ]({{ site.baseurl }}/script-api/{{ property.scriptApiClass }}.html#{{ property.propName }}){:target="_blank"})
