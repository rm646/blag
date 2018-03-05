---
title: Varietes of Nun
description: Notes on nuns
---

### Nuns abound

<ul>
{% for item in site.data.nun_varieties %}
  <li>
    Type: {{ item.type }}. Habitat: {{item.habitat}}. Notes: {{item.notes}}
  </li>
{% endfor %}
</ul>
