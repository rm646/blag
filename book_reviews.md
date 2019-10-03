---
layout: page
title: Book reviews
---

### Sources

Short reviews on books I have read.


{% for item in site.data.book_reviews %}
<hr/>
    <strong>{{ item.title }}</strong> ({{ item.author }}, {{item.publisher}}, ISBN:{{item.ISBN}})
    {{ item.review }}
<hr/>
{% endfor %}
