{%- comment -%}
Cherche la note écrite à la main (collection api_notes) d'un élément de la référence générée et
la place dans la variable api_note : include.type (type d'acteur ou « common »), include.kind
(property, event, member), include.name. La note de l'acteur l'emporte ; à défaut, celle d'un
acteur dont il hérite (note_types, ex. la ressource reprend les notes du fournisseur de variable).
{%- endcomment -%}
{%- assign api_note_types = site.data.script_api.actors[include.type].note_types | default: include.type -%}
{%- assign api_note = nil -%}
{%- for api_note_type in api_note_types -%}
{%- unless api_note -%}
{%- assign api_note = site.api_notes | where: "api_type", api_note_type | where: "kind", include.kind | where: "name", include.name | first -%}
{%- endunless -%}
{%- endfor -%}
