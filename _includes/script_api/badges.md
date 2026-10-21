{%- comment -%}
Versions d'apparition, depuis l'en-tête de la page : since: { studio, runtime, redy, redy_pilot }.
Affichées automatiquement en tête de toute page qui en a (_layouts/my_default.html), en HTML.
Vert pour une version officielle ; jaune pour tous les badges si l'une des versions est une beta
(la fonctionnalité n'est encore disponible qu'en beta). Retirer « -beta » à la sortie officielle.
{%- endcomment -%}
{%- if page.since -%}
{%- assign since_versions = page.since.studio | append: page.since.runtime | append: page.since.redy | append: page.since.redy_pilot -%}
{%- if since_versions contains "beta" %}{% assign since_color = "label-yellow" %}{% else %}{% assign since_color = "label-green" %}{% endif -%}
<div class="since-badges">
{%- if page.since.studio %}<p class="label {{ since_color }}">Studio <strong>{{ page.since.studio }}</strong></p>{% endif -%}
{%- if page.since.runtime %}<p class="label {{ since_color }}">Runtime <strong>{{ page.since.runtime }}</strong></p>{% endif -%}
{%- if page.since.redy %}<p class="label {{ since_color }}">REDY <strong>{{ page.since.redy }}</strong></p>{% endif -%}
{%- if page.since.redy_pilot %}<p class="label {{ since_color }}">REDY Pilot <strong>{{ page.since.redy_pilot }}</strong></p>{% endif -%}
</div>
{%- endif -%}
