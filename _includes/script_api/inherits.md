{%- comment -%}
Ascendance d'un acteur, générée depuis le code : include.type = type d'acteur.
{%- endcomment -%}
{%- assign api_actor = site.data.script_api.actors[include.type] -%}
Outre ce qui est décrit ici, l'acteur a tout ce que décrit l'[acteur de base]({{ site.baseurl }}/concepts/actor/) : propriétés communes (taille, disposition, aspect, texte, bordures, effets...), évènements communs (cycle de vie, souris, clavier...) et membres accessibles par script.
{%- if api_actor.lineage.size > 0 %}

Il hérite aussi de :
{% for ancestor in api_actor.lineage %}
- **{{ ancestor.name }}**{% if ancestor.behavior %} (comportement){% endif %} : {{ ancestor.description }}
{%- endfor %}
{%- endif %}
