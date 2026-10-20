{%- comment -%}
Propriétés d'un acteur, générées depuis le code (synapps-studio : yarn script-api), par ordre
alphabétique du libellé : include.type = type d'acteur (ex. redy/data-source/wos-variable).
{%- endcomment -%}
{%- assign api_actor = site.data.script_api.actors[include.type] -%}
{%- for property in api_actor.properties %}

## {{ property.label | default: property.name }}

`this.properties.{{ property.name }}` · {% if property.values %}{% for value in property.values %}`'{{ value }}'`{% unless forloop.last %} \| {% endunless %}{% endfor %}{% else %}{{ property.type | escape }}{% endif %} · défaut `{{ property.default }}`
{: .fs-2 }
{% if property.description %}
{{ property.description }}
{% endif %}
{% include script_api/note.md type=include.type kind="property" name=property.name %}
{%- endfor %}
