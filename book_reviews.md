---
layout: page
title: Book reviews
---

Short reviews on some of the books I have read.
<details open>
    <summary>2023</summary>
    <ul>
    {% for review_hash in site.data.book_reviews.2023 %}
    {% assign review = review_hash[1] %}
        <details>
            <summary><strong>{{ review.title }},  {{ review.author }}</strong></summary>
            <em>({{review.publisher}}, ISBN:{{review.ISBN}})</em><br>
            {{ review.review }}
        </details>
        <hr>
    {% endfor %}
    </ul>
</details>
<details>
    <summary>Earlier</summary>
    <ul>
    {% for review_hash in site.data.book_reviews.pre_2022 %}
    {% assign review = review_hash[1] %}
        <details>
            <summary><strong>{{ review.title }},  {{ review.author }}</strong></summary>
            <em>({{review.publisher}}, ISBN:{{review.ISBN}})</em><br>
            {{ review.review }}
        </details>
        <hr>
    {% endfor %}
    </ul>
</details>