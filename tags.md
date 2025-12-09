---
layout: page
title: Tags
permalink: /tags/
---

<div class="tag-cloud">
  {% assign tags = site.tags | sort %}
  {% for tag in tags %}
    <a href="#{{ tag[0] | slugify }}" style="font-size: {{ tag[1] | size | times: 4 | plus: 80 }}%">
      {{ tag[0] }} ({{ tag[1] | size }})
    </a>
  {% endfor %}
</div>

<hr>

{% for tag in tags %}
  <h3 id="{{ tag[0] | slugify }}">{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <small>({{ post.date | date: "%b %-d, %Y" }})</small>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
