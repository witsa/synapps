{%- comment -%}
Champs d'un acteur accessibles par script (@script), générés depuis le code, par ordre
alphabétique : include.type = type d'acteur. Le titre vient de la note (label) s'il y en a une.
{%- endcomment -%}
{%- assign api_actor = site.data.script_api.actors[include.type] -%}
{%- for member in api_actor.fields %}
{%- assign api_note = site.api_notes | where: "api_type", include.type | where: "kind", "member" | where: "name", member.name | first %}

## {{ api_note.label | default: member.name }}

`this.{{ member.name }}` · {% if member.readonly %}🔒 lecture seule{% else %}✏️ modifiable{% endif %}{% if member.type %} · {{ member.type | escape }}{% endif %}
{: .fs-2 }
{% if member.description %}
{{ member.description }}
{% endif %}
{% include script_api/note.md type=include.type kind="member" name=member.name %}
{%- endfor %}
