{%- comment -%}
Versions d'apparition de l'acteur, depuis l'en-tête de la page : since: { studio, runtime, redy, redy_pilot }.
Vert pour une version officielle ; jaune pour tous les badges si l'une des versions est une beta
(la fonctionnalité n'est encore disponible qu'en beta). Retirer « -beta » à la sortie officielle.
{%- endcomment -%}
{%- if page.since %}
{%- assign since_versions = page.since.studio | append: page.since.runtime | append: page.since.redy | append: page.since.redy_pilot -%}
{%- if since_versions contains "beta" %}{% assign since_color = "label-yellow" %}{% else %}{% assign since_color = "label-green" %}{% endif %}
{% if page.since.studio %}Studio **{{ page.since.studio }}**
{: .label .{{ since_color }} }
{% endif %}{% if page.since.runtime %}Runtime **{{ page.since.runtime }}**
{: .label .{{ since_color }} }
{% endif %}{% if page.since.redy %}REDY **{{ page.since.redy }}**
{: .label .{{ since_color }} }
{% endif %}{% if page.since.redy_pilot %}REDY Pilot **{{ page.since.redy_pilot }}**
{: .label .{{ since_color }} }
{% endif %}
{%- endif %}
