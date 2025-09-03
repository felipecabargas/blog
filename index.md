---
layout: default
title: "Home"
description: "Welcome to my thought leadership blog where I share insights on artificial intelligence, strategy and product management."
---

# Welcome

Welcome to **{{ site.title }}**, a personal space where I explore topics at the intersection of technology and business. Here you'll find articles about machine learning advancements, strategic frameworks, and how to build and manage products that delight users.

## Latest Posts

<ul>
{% assign sorted_posts = site.posts | sort: 'date' | reverse %}
{% for post in sorted_posts limit:5 %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a><br />
    <small><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%B %-d, %Y' }}</time> — {{ post.description | default: post.excerpt | strip_html }}</small>
  </li>
{% endfor %}
</ul>

Want to know more? Head over to the [About]({{ '/about/' | relative_url }}) page or browse the [Blog]({{ '/blog/' | relative_url }}) archive.