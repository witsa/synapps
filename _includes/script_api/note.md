{%- comment -%}
Note écrite à la main (collection api_notes) pour un élément de la référence générée :
include.type (type d'acteur ou « common »), include.kind (property, event, member), include.name.
Recherche (notes héritées comprises) : find_note.md.
Les liens relatifs `.md` sont convertis en `.html` (jekyll-relative-links ne traite pas les includes).
{%- endcomment -%}
{%- include script_api/find_note.md type=include.type kind=include.kind name=include.name -%}
{%- if api_note %}

{{ api_note.content | replace: ".md)", ".html)" | replace: ".md#", ".html#" }}
{%- endif %}
