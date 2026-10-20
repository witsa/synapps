{%- comment -%}
Évènements propres à un acteur, générés depuis le code (@event, appels runEvent), par ordre
alphabétique : include.type = type d'acteur. Les évènements communs sont décrits avec l'acteur
de base.
{%- endcomment -%}
{%- if include.type == "common" -%}
{%- assign api_actor = site.data.script_api.common -%}
{%- else -%}
{%- assign api_actor = site.data.script_api.actors[include.type] -%}
{%- endif -%}
{%- for event in api_actor.events %}

## {{ event.name }}
{: .api-event }
{% if event.description %}
{{ event.description }}
{% endif %}
{%- if event.context.size > 0 %}

| Membre de `context` | Type | Description |
|---|---|---|
{%- for item in event.context %}
| `{{ item.name }}` | {{ item.type | default: "" | escape | replace: "|", "&#124;" }} | {{ item.description | default: "" | replace: "|", "&#124;" }} |
{%- endfor %}
{% endif %}
{% include script_api/note.md type=include.type kind="event" name=event.name %}
{%- endfor %}
