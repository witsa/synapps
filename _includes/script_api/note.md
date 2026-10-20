{%- comment -%}
Note écrite à la main (collection api_notes) pour un élément de la référence générée :
include.type (type d'acteur ou « common »), include.kind (property, event, member), include.name.
Les liens relatifs `.md` sont convertis en `.html` (jekyll-relative-links ne traite pas les includes).
{%- endcomment -%}
{%- assign api_note = site.api_notes | where: "api_type", include.type | where: "kind", include.kind | where: "name", include.name | first -%}
{%- if api_note %}

{{ api_note.content | replace: ".md)", ".html)" | replace: ".md#", ".html#" }}
{%- endif %}
