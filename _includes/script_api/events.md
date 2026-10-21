{%- comment -%}
Évènements propres à un acteur, générés depuis le code (@event, appels runEvent), par ordre
alphabétique : include.type = type d'acteur ou « common » ; include.list = autre liste de l'acteur
(property_events : évènements propres à chaque propriété, ancre explicite sans accents).
{%- endcomment -%}
{%- if include.object -%}
{%- assign api_actor = site.data.script_api.objects[include.object] -%}
{%- elsif include.type == "common" -%}
{%- assign api_actor = site.data.script_api.common -%}
{%- else -%}
{%- assign api_actor = site.data.script_api.actors[include.type] -%}
{%- endif -%}
{%- comment -%} liste demandée même vide (default remplacerait une liste vide par les évènements) {%- endcomment -%}
{%- if include.list -%}
{%- assign api_events = api_actor[include.list] -%}
{%- else -%}
{%- assign api_events = api_actor.events -%}
{%- endif -%}
{%- assign api_event_note_type = include.object | default: include.type -%}
{%- capture api_newline %}
{% endcapture -%}
{%- for event in api_events %}

## {{ event.name | escape }}
{% if include.list %}{: .api-event #{{ event.name | slugify: "latin" }} }{% else %}{: .api-event }{% endif %}
{% if event.description %}
{{ event.description }}
{% endif %}

`context` : [contexte d'évènement]({{ site.baseurl }}/concepts/scripts/reference/context.html){% if event.context.size > 0 %}, avec en plus :{% endif %}
{: .fs-2 }
{%- if event.context.size > 0 %}

| Membre de `context` | Type | Description |
|---|---|---|
{%- for item in event.context %}
| `{{ item.name }}` | {{ item.type | default: "" | escape | replace: "|", "&#124;" }} | {{ item.description | default: "" | replace: "|", "&#124;" | replace: api_newline, " " }} |
{%- endfor %}
{% endif %}
{%- if event.returns %}

Valeur renvoyée{% if event.returns.type %} ({{ event.returns.type | escape }}){% endif %} : {{ event.returns.description }}
{% endif %}
{% include script_api/note.md type=api_event_note_type kind="event" name=event.name %}
{%- endfor %}
