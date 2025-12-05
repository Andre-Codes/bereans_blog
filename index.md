---
layout: default
title: Home
---

# Welcome to my blog

Here are the latest posts:

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      {% if post.image %}
        <img src="{{ post.image | relative_url }}" alt="Cover" style="width: 100px; height: 60px; object-fit: cover; float: left; margin-right: 15px; border-radius: 4px;">
      {% endif %}
      <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      <div style="clear: both;"></div>
    </li>
  {% endfor %}
</ul>
