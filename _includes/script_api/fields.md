{%- comment -%}
Champs d'un acteur accessibles par script (@script), générés depuis le code, par ordre
alphabétique : include.type = type d'acteur ou « common », ou include.object = objet documenté à part
(properties, binding). Le titre vient de la note (label) s'il y en a une.
{%- endcomment -%}
{%- if include.object -%}
{%- assign api_actor = site.data.script_api.objects[include.object] -%}
{%- elsif include.type == "common" -%}
{%- assign api_actor = site.data.script_api.common -%}
{%- else -%}
{%- assign api_actor = site.data.script_api.actors[include.type] -%}
{%- endif -%}
{%- for member in api_actor.fields %}
{%- include script_api/find_note.md type=include.type kind="member" name=member.name %}

{%- assign api_title = api_note.label | default: member.name %}

## {{ api_title }}
{: .api-field }

`this.{{ member.name }}`{% if member.readonly %} · 🔒 lecture seule{% endif %}{% if member.type %} · {{ member.type | escape }}{% endif %}
{: .fs-2 }
{% if member.description %}
{{ member.description }}
{% endif %}
{% include script_api/note.md type=include.type kind="member" name=member.name %}
{%- endfor %}
