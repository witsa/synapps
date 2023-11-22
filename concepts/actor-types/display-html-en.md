---
title: "Display | HTML"
parent: "Actor types" 
grand_parent: Concepts
lang: en
permalink: /concepts/actor-types/display-html.html
---

{% include links_actor.md apiClass="Actor.Display.Html" %}

# HTML

HTML actor allows you to integrate HTML and CSS code into your scene.

It is a very practical actor to format text, or add CSS class for example.

{% include table_of_content.html %}

Its content is **wildcardable**.

## Specific properties

{% assign sorted = site.display_html_properties_en | sort: 'order' %}

{% for property in sorted %}

{% include actor_property_en.md property=property %}

{% endfor %}

# Information fields

## Completed content

{% include field_completed_content_en.md %}

# Variants

## Icon

Variant of the HTML actor offering the possibility to integrate an icon chosen among the icons integrated to Synapps.

The content of the actor is completed by an additional *icon*.
