---
title: Sort by Tag
permalink: sort-by-tag
layout: page
---

{% for tag in site.tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

<h2>{{ t | downcase }}</h2>
<ul>
{% for post in posts %}
    {% if post.tags contains t %}
        <dt><a href="{{ post.url }}">{{ post.title }}</a> </dt>
        <dd class="date">{{ post.date | date: "%B %-d, %Y"  }}</dd>
    {% endif %}
{% endfor %}
</ul>
<hr/>
{% endfor %}

<!-- Thank you to https://www.jokecamp.com/blog/listing-jekyll-posts-by-tag/ for providing this code online! -->