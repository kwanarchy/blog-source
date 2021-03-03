---
title: Sort by Tag
permalink: sort-by-tag
layout: page
---

<!-- Sort tags alphabetically and iterate through them -->
{% assign sorted_tags = site.tags | sort %}
{% for tag in sorted_tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

<h2 id="{{t | downcase}}">{{ t | downcase }}</h2>
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