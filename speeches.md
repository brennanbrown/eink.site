---
layout: default
title: All Speeches
---

# All Speeches

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

### Business
<ul class="post-list">
{% for post in site.posts %}
  {% if post.category == "business" %}
  <li>
    <span class="post-date">[{{ post.date | date: "%Y-%m-%d" }}]</span>
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {% endif %}
{% endfor %}
</ul>

### Personal
<ul class="post-list">
{% for post in site.posts %}
  {% if post.category == "personal" %}
  <li>
    <span class="post-date">[{{ post.date | date: "%Y-%m-%d" }}]</span>
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {% endif %}
{% endfor %}
</ul>

### Technical
<ul class="post-list">
{% for post in site.posts %}
  {% if post.category == "technical" %}
  <li>
    <span class="post-date">[{{ post.date | date: "%Y-%m-%d" }}]</span>
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {% endif %}
{% endfor %}
</ul>

---

[← Back to Home](/)
