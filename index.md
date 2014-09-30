---
title: Home
description: If we lived here you'd be home by now. 
image: "/images/pic01.jpg"
---

<!-- http://uncelestial.67314.x6.nabble.com/News-ft2.xml;cid=1412057808465-339 -->

## Welcome

Uncelestial is a band from San Francisco. This is their official site. If you're looking 
to get acquainted quickly, try reading the [bio](/about) or watching some [videos](/videos).

{% for post in site.posts %}
<h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
<p>{{ post.excerpt }}</p>
<p><a href="{{ post.url }}">Posted: {{ post.date }} | Read more...</a></p>
{% endfor %}
