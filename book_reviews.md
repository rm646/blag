---
layout: page
title: Book reviews
---

### Sources

Short reviews on books I have read.

{% for item in site.data.book_reviews %}
    <hr/>
    <strong>{{ item.title }}({{ item.author }}, {{item.publisher}}, ISBN:{{item.ISBN}}) </strong>
    {{ item.review }}
{% endfor %}
