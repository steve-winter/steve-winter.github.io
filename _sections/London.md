---
layout: entries
title:  "London"
date:   2016-09-20 12:03:37 +0100
categories: jekyll update
label: london
permalink: /journeys/london
mainImage: https://media.timeout.com/images/100644443/image.jpg
summary: Our time in London
---

{% for post in paginator.posts %}
  <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
  <p class="author">
    <span class="date">{{ post.date }}</span>
  </p>
  <div class="content">
    {{ post.content }}
  </div>
{% endfor %}
