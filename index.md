---
layout: default
title: Routes, landmarks & history
description: >-
  Route notes, landmark history, and FAQ for every Journey Journal video —
  real-time 4K walks and rides across New York City with pure ambient sound.
---
# Journey Journal — routes, landmarks & history

Companion notes for every video on the
[Journey Journal](https://www.youtube.com/@journeyjournal-q) YouTube channel:
the exact **route**, the **landmarks** you see on camera (with verified dates),
and a short **FAQ** for anyone who wants to do the same walk or ride.

The [public video index]({{ '/videos/' | relative_url }}) lists every public
Journey Journal upload, including older videos that do not yet have a detailed
route companion.

## Journeys

{% if site.walks.size > 0 %}
<ul>
{% for walk in site.walks %}
  <li><a href="{{ walk.url | relative_url }}">{{ walk.title }}</a>{% if walk.borough %} <span class="meta">· {{ walk.borough }}</span>{% endif %}</li>
{% endfor %}
</ul>
{% else %}
_Journey pages will appear here as videos publish._
{% endif %}
