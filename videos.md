---
layout: default
title: Complete public video index
permalink: /videos/
description: >-
  A crawlable index of every public Journey Journal YouTube video, generated
  from the channel's uploads. Private and unlisted videos are excluded.
---
# Complete public video index

This index contains **{{ site.data.public_videos.public_count }} public videos**
from the [Journey Journal YouTube channel]({{ site.youtube_channel }}). It was
last synchronized on {{ site.data.public_videos.generated_at }}. Detailed route
and history companions are added separately after fact review.

<ol class="video-index">
{% for video in site.data.public_videos.videos %}
  <li>
    <a href="https://www.youtube.com/watch?v={{ video.id }}">{{ video.title }}</a>
    <span class="meta">· {{ video.published_date }}{% if video.duration %} · {{ video.duration }}{% endif %}</span>
  </li>
{% endfor %}
</ol>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "CollectionPage",
  "name": {{ page.title | jsonify }},
  "description": {{ page.description | jsonify }},
  "url": {{ page.url | absolute_url | jsonify }},
  "inLanguage": "en",
  "mainEntity": {
    "@type": "ItemList",
    "numberOfItems": {{ site.data.public_videos.public_count }},
    "itemListElement": [{% for video in site.data.public_videos.videos %}
      {
        "@type": "ListItem",
        "position": {{ forloop.index }},
        "url": "https://www.youtube.com/watch?v={{ video.id }}",
        "name": {{ video.title | jsonify }}
      }{% unless forloop.last %},{% endunless %}{% endfor %}
    ]
  }
}
</script>
