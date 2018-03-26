---
title: Great Names
description: Real and imaginary names
layout: page
---
Some names are drab, others are great. They have some intangible quality or 'phwoar' factor. Here are some examples.
<ul>
{% for item in site.data.great_names %}
  <li>
    {{ item.name }}. {{item.notes}}
  </li>
{% endfor %}
</ul>
