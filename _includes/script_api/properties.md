{%- comment -%}
Propriétés d'un acteur, générées depuis le code (synapps-studio : yarn script-api), par ordre
alphabétique du libellé : include.type = type d'acteur (ex. redy/data-source/wos-variable), ou
« common » pour les propriétés communes à tous les acteurs ; filtres facultatifs :
include.section (section de l'inspecteur, ex. text) et include.names (noms séparés par des virgules).
{%- endcomment -%}
{%- if include.type == "common" -%}
{%- assign api_actor = site.data.script_api.common -%}
{%- else -%}
{%- assign api_actor = site.data.script_api.actors[include.type] -%}
{%- endif -%}
{%- assign api_properties = api_actor.properties -%}
{%- if include.section %}{% assign api_properties = api_properties | where: "section", include.section %}{% endif -%}
{%- if include.names %}{% assign api_names = include.names | split: "," %}{% endif -%}
{%- for property in api_properties %}
{%- if include.names %}{% unless api_names contains property.name %}{% continue %}{% endunless %}{% endif %}

{%- assign api_title = property.label | default: property.name %}

## {{ api_title }}
{: .api-property }

`this.properties.{{ property.name }}` · {% if property.values %}{% for value in property.values %}`'{{ value }}'`{% unless forloop.last %} \| {% endunless %}{% endfor %}{% else %}{{ property.type | escape }}{% endif %} · défaut `{{ property.default }}`{% if property.modifier %} · modifie : [{{ property.modifier }}]({{ site.baseurl }}/concepts/actor/#évènement-de-modification){% endif %}
{: .fs-2 }
{% if property.description %}
{{ property.description }}
{% endif %}
{% include script_api/note.md type=include.type kind="property" name=property.name %}
{%- endfor %}
