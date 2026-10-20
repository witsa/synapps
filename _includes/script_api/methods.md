{%- comment -%}
Méthodes d'un acteur accessibles par script (@script), générées depuis le code, par ordre
alphabétique : include.type = type d'acteur. Le titre vient de la note (label) s'il y en a une.
{%- endcomment -%}
{%- assign api_actor = site.data.script_api.actors[include.type] -%}
{%- for member in api_actor.methods %}
{%- include script_api/find_note.md type=include.type kind="member" name=member.name %}

{%- assign api_title = api_note.label | default: member.signature %}

## {{ api_title }}
{: .api-method }

`this.{{ member.signature }}`{% if member.type %} · renvoie {{ member.type | escape }}{% endif %}
{: .fs-2 }
{% if member.description %}
{{ member.description }}
{% endif %}
{%- for param in member.params %}
- `{{ param.name }}` : {{ param.description }}
{%- endfor %}
{% include script_api/note.md type=include.type kind="member" name=member.name %}
{%- endfor %}
