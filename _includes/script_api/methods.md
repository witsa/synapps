{%- comment -%}
Méthodes d'un acteur accessibles par script (@script), générées depuis le code, par ordre
alphabétique : include.type = type d'acteur ou « common », ou include.object = objet documenté à part
(properties, binding) ; include.prefix = préfixe du chemin d'accès affiché (`this` par défaut). Le titre vient de la note (label) s'il y en a une.
{%- endcomment -%}
{%- assign api_note_type = nil -%}
{%- if include.object -%}
{%- assign api_actor = site.data.script_api.objects[include.object] -%}
{%- assign api_note_type = include.object -%}
{%- elsif include.type == "common" -%}
{%- assign api_actor = site.data.script_api.common -%}
{%- else -%}
{%- assign api_actor = site.data.script_api.actors[include.type] -%}
{%- endif -%}
{%- assign api_note_type = api_note_type | default: include.type -%}
{%- for member in api_actor.methods %}
{%- include script_api/find_note.md type=api_note_type kind="member" name=member.name %}

{%- assign api_title = api_note.label | default: member.signature %}

## {{ api_title }}
{: .api-method }

`{{ include.prefix | default: "this" }}.{{ member.signature }}`{% if member.type %} · renvoie {{ member.type | escape }}{% endif %}
{: .fs-2 #meth-{{ member.name }} }
{% if member.description %}
{{ member.description }}
{% endif %}
{%- for param in member.params %}
- `{{ param.name }}` : {{ param.description }}
{%- endfor %}
{% include script_api/note.md type=api_note_type kind="member" name=member.name %}
{%- endfor %}
