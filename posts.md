---
layout: default
title: All Posts
---

# All Posts

## By Date

<ul class="post-list">
{% for post in site.posts %}
  <li>
    <span class="post-date">[{{ post.date | date: "%Y-%m-%d" }}]</span>
    <a href="{{ post.url }}">{{ post.title }}</a>
    {% if post.category %}
    <em>({{ post.category }})</em>
    {% endif %}
  </li>
{% endfor %}
</ul>

---

## By Category

{% assign categories = site.posts | map: 'category' | uniq | sort %}
{% if categories.size > 0 %}
  {% for category in categories %}
    {% if category %}
### {{ category | capitalize }}
<ul class="post-list">
{% for post in site.posts %}
  {% if post.category == category %}
  <li>
    <span class="post-date">[{{ post.date | date: "%Y-%m-%d" }}]</span>
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {% endif %}
{% endfor %}
</ul>

    {% endif %}
  {% endfor %}
{% else %}
<p><em>No categories defined yet.</em></p>
{% endif %}

---

[← Back to Home](/)
