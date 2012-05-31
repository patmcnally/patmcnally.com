---
layout: default
title: Blog Entries
---

Blogs
=====
{% for post in site.posts %}
   [{{ post.title }}]({{post.url}}) {{ post.date }}
{% endfor %}