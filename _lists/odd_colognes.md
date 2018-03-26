---
title: Odd Colognes
description: Ideas for unconventional fragrances
layout: page
---
The advertising of perfume for men and women has never really made sense to me. They seem to market an idea of what it'll be like when you wear their perfume, when I would like to know what it smells like before I buy it. The other issue I have is the lacklustre set of smells they seem to choose from. Some smells have the potential to <em>really </em>grab us, and I don't think they shouldn't be considered just because they happen to be like petrol. There're enough smells out there to find your niche and perhaps give someone else that Ratatouille moment. Here are some suggestions.

<ul>
{% for item in site.data.odd_colognes %}
  <li>
    {{ item.cologne }}
  </li>
{% endfor %}
</ul>
