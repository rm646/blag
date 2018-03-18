---
layout: page
title: List Index
---

<ul>
{% for list in site.lists %}
  <div class="list_index_entry">
    <h2><a href="{{ list.url | prepend:site.baseurl }}">{{ list.title }}</a></h2>
    {{list.description}}
  </div>
{% endfor %}
</ul>

<ul>
{% for item in site.data.nun_varieties %}
  <li>
    Type: {{ item.type }}. Habitat: {{item.habitat}}. Notes: {{item.notes}}
  </li>
{% endfor %}
</ul>
