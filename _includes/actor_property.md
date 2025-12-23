{% assign property = include.property %}

## {{ property.title }}

- **Champ** : `{{ property.propPath }}`

{{ property.content | markdownify }}
