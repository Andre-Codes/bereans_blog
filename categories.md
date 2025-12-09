---
layout: page
title: Categories
permalink: /categories/
---

<ul>
  {% assign categories = site.categories | sort %}
  {% for category in categories %}
    <li>
      <a href="#{{ category[0] | slugify }}">
        {{ category[0] | capitalize }} ({{ category[1] | size }})
      </a>
    </li>
  {% endfor %}
</ul>

<hr>

{% for category in categories %}
  <h3 id="{{ category[0] | slugify }}">{{ category[0] | capitalize }}</h3>
  <ul>
    {% for post in category[1] %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <small>({{ post.date | date: "%b %-d, %Y" }})</small>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
