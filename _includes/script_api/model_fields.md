{%- comment -%}
Champs d'un modèle de donnée accessibles par script (@script), générés depuis le code :
include.model = clé du modèle (ex. redy/WosVariable), include.prefix = préfixe d'accès affiché
(ex. this.data). Libellé Studio : nom du champ dans l'inspecteur, s'il y en a un.
include.exclude = clé d'un autre modèle dont les champs sont omis (ex. les champs communs des reflets).
{%- endcomment -%}
{%- assign api_model = site.data.script_api.models[include.model] %}
{%- capture api_newline %}
{% endcapture -%}
{%- assign api_excluded = "," %}
{%- if include.exclude %}{% for other in site.data.script_api.models[include.exclude].fields %}{% assign api_excluded = api_excluded | append: other.name | append: "," %}{% endfor %}{% endif %}

| Libellé Studio | Champ | Type | Description |
|---|---|---|---|
{%- for field in api_model.fields %}
{%- assign api_key = "," | append: field.name | append: "," %}
{%- if api_excluded contains api_key %}{% continue %}{% endif %}
| {{ field.label | default: "" }} | `{% if include.prefix %}{{ include.prefix }}.{% endif %}{{ field.name }}`{% if field.readonly %} 🔒{% endif %} | {{ field.type | default: "" | escape | replace: "|", "&#124;" }} | {{ field.description | default: "" | replace: "|", "&#124;" | replace: api_newline, " " }} |
{%- endfor %}
