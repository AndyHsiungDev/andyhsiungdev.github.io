---
title: Blog
layout: default
nav_order: 3
---

# Blog

{% if site.posts.size == 0 %}
No posts yet. Check back soon!
{% else %}
<ul class="post-list">
  {% for post in site.posts %}
  <li class="post-list-item">
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <p class="post-list-meta">
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
    </p>
    {% if post.excerpt %}
    <p class="post-list-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    {% endif %}
  </li>
  {% endfor %}
</ul>
{% endif %}
