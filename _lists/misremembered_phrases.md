---
title: Misremembered Phrases
description: Not quite the original
layout: page
---
<ul>
{% for item in site.data.misremembered_phrases %}
  <li>
    {{ item.phrase }}
  </li>
{% endfor %}
</ul>
