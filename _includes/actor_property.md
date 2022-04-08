{% assign property = include.property %}

## {{ property.title }}

{{ property.content | markdownify }}

> {% include actor_property_script.md propName=property.propName propPath=property.propPath scriptApiClass=property.scriptApiClass %}
