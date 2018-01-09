---
layout: page
title: Book reviews
---

### Sources

Short reviews on books I have read.

<ul>
{% for item in site.data.book_reviews %}
  <li>
    <strong>{{ item.title }}</strong>({{ item.author }}, {{item.publisher}}, ISBN:{{item.ISBN}}})
    {{ item.review }}
  </li>
{% endfor %}
</ul>
