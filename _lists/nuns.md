---
title: Varietes of Nun
description: Notes on nuns
---

Stray ye not. Nuns can be as dangerous as they are colourful. Here are the varieties of nun.

<ul>
{% for item in site.data.nun_varieties %}
  <li>
    Type: {{ item.type }}. Habitat: {{item.habitat}}. Notes: {{item.notes}}
  </li>
{% endfor %}
</ul>
