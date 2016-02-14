---
layout: inner
title: Categories
permalink: /categories/
---

{% capture categories %}
{% for cat in site.categories %}
{{ cat[0] }}
{% endfor %}
{% endcapture %}
{% assign sortedtags = categories | split:' ' | sort %}

{% for tag in sortedtags %}
<h3 id="{{ tag }}">{{ tag }}</h3>
<ul>
    {% for post in site.categories[tag] %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
{% endfor %}