---
layout: page
title: Propositions
permalink: /propositions/
---

This index lists the propositions from G.N.H. Peters' *The Theocratic Kingdom* that have been discussed in our blog posts.

> Note: Posts that are part of the main prop-by-prop study are highlighted

{% assign all_props = "" | split: "" %}
{% for post in site.posts %}
  {% if post.propositions %}
    {% for prop in post.propositions %}
      {% assign all_props = all_props | push: prop %}
    {% endfor %}
  {% endif %}
{% endfor %}
{% assign all_props = all_props | uniq | sort %}

<div class="prop-list" style="margin-bottom: 2rem;">
  <strong>Quick Links:</strong>
  {% for prop in all_props %}
    <a href="#prop-{{ prop }}" class="prop-link">Prop {{ prop }}</a>{% unless forloop.last %}, {% endunless %}
  {% endfor %}
</div>

<hr>

{% for prop in all_props %}
  <div class="prop-section">
    <h3 id="prop-{{ prop }}">Proposition {{ prop }}</h3>
    <ul>
      {% for post in site.posts %}
        {% if post.propositions contains prop %}
          <li>
            {% if post.primary_prop == prop %}
              <div class="primary-prop-highlight">
                <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
                <small>({{ post.date | date: "%b %-d, %Y" }})</small>
              </div>
            {% else %}
              <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
              <small>({{ post.date | date: "%b %-d, %Y" }})</small>
            {% endif %}
          </li>
        {% endif %}
      {% endfor %}
    </ul>
  </div>
{% endfor %}
