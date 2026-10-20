{%- comment -%}
Versions d'apparition de l'acteur, depuis l'en-tête de la page : since: { studio, runtime, redy, redy_pilot }.
{%- endcomment -%}
{%- if page.since %}
{% if page.since.studio %}Studio **{{ page.since.studio }}**
{: .label .label-green }
{% endif %}{% if page.since.runtime %}Runtime **{{ page.since.runtime }}**
{: .label .label-green }
{% endif %}{% if page.since.redy %}REDY **{{ page.since.redy }}**
{: .label .label-green }
{% endif %}{% if page.since.redy_pilot %}REDY Pilot **{{ page.since.redy_pilot }}**
{: .label .label-green }
{% endif %}
{%- endif %}
