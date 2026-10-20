{%- comment -%}
Champs d'un modèle de donnée accessibles par script (@script), générés depuis le code :
include.model = clé du modèle (ex. redy/WosVariable), include.prefix = préfixe d'accès affiché
(ex. this.data). Libellé Studio : nom du champ dans l'inspecteur, s'il y en a un.
{%- endcomment -%}
{%- assign api_model = site.data.script_api.models[include.model] %}

| Libellé Studio | Champ | Type | Description |
|---|---|---|---|
{%- for field in api_model.fields %}
| {{ field.label | default: "" }} | `{% if include.prefix %}{{ include.prefix }}.{% endif %}{{ field.name }}`{% if field.readonly %} 🔒{% endif %} | {{ field.type | default: "" | escape | replace: "|", "&#124;" }} | {{ field.description | default: "" | replace: "|", "&#124;" }} |
{%- endfor %}
