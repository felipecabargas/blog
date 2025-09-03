---
layout: default
title: "Blog"
description: "Archive of articles on AI, strategy and product management."
---

# Blog Archive

Below is a full list of posts organised by date. Use the headings to navigate by category.

{% assign posts_by_category = site.posts | group_by_exp: "post", "post.categories[0]" %}
{% for category in posts_by_category %}
  <h2 id="{{ category.name | downcase | replace: ' ', '-' }}">{{ category.name }}</h2>
  <ul>
    {% assign posts_sorted = category.items | sort: 'date' | reverse %}
    {% for post in posts_sorted %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <small><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%B %-d, %Y' }}</time></small>
      </li>
    {% endfor %}
  </ul>
{% endfor %}