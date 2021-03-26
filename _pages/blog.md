---
layout: archive
permalink: /blog/
title: "Blog"
header:
  overlay_color: "#000"
  overlay_filter: "0.1"
  overlay_image: /photos/network_banner.png
---

<h1>Latest Posts</h1>

<ul>
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>
