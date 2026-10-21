{%- comment -%}
Méthodes d'un modèle de donnée accessibles par script (@script), générées depuis le code :
include.model = clé du modèle (ex. redy/ReflectBase), include.prefix = préfixe d'accès affiché.
{%- endcomment -%}
{%- assign api_model = site.data.script_api.models[include.model] %}

| Méthode | Renvoie | Description |
|---|---|---|
{%- for method in api_model.methods %}
| `{% if include.prefix %}{{ include.prefix }}.{% endif %}{{ method.signature }}` | {{ method.type | default: "" | escape | replace: "|", "&#124;" }} | {{ method.description | default: "" | replace: "|", "&#124;" }} |
{%- endfor %}
