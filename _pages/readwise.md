---
title: "Summaries of Books"
layout: single
permalink: /readwise/
author_profile: true
---


<ul>
  {% assign sorted_books = site.books | sort: 'date' | reverse %}
  {% for book in sorted_books %}
    <li>
      <a href="{{ book.url | relative_url }}">
        {{ book.title }}
      </a>
      {% if book.author %} – <em>{{ book.author }}</em>{% endif %}
    </li>
  {% endfor %}
</ul>