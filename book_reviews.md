---
layout: page
title: Book reviews
---

### Sources

Short reviews on books I have read.

<ul>
{% for item in site.data.book_reviews %}
    <li><strong>{{ item.title }}({{ item.author }}, {{item.publisher}}, ISBN:{{item.ISBN}}) </strong>
    {{ item.review }}
    <hr>
{% endfor %}
</ul>
