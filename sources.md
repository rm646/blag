---
layout: page
title: Sources
---

### Sources

A list of sources I check regularly.

<ul>
{% for item in site.data.sources %}
  <li>
    <a href="{{ item.url }}">
      {{ item.source }}
    </a>
  </li>
{% endfor %}
</ul>
