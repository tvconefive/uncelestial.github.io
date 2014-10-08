---
title: Home
description: If we lived here you'd be home by now. 
image: "/images/pic01.jpg"
---

## Welcome

<div id="twitch">
<iframe id="twitchvid" src="http://www.twitch.tv/uncelestial/embed" frameborder="0" scrolling="no"></iframe>
<a href="http://twitch.tv/uncelestial"><img src="http://streambadge.com/twitch/light/uncelestial.png" width="300" height="64" alt="uncelestial's Streambadge"></a>
</div>
<ul id="socialstuff">
<a class="twitter-timeline" href="https://twitter.com/uncelestial" data-widget-id="518837278257336320">Tweets by @uncelestial</a>
<script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+"://platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");</script>
</li>
<li>
<div class="fb-like-box" data-href="https://www.facebook.com/uncelestial" data-width="162" data-height="300" data-colorscheme="light" data-show-faces="false" data-header="true" data-stream="true" data-show-border="false"></div>
</li>
</ul>

Uncelestial is a band from San Francisco. This is their official site. If you're looking 
to get acquainted quickly, try reading the [bio](/about) or watching some [videos](/videos)

{% for post in site.posts %}
<h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
<p>{{ post.content }}</p>
<p>Posted: {{ post.date | date: "%-d %B %Y" }} | <a href="{{ post.url }}#disqus_thread">comment_count</a></p>
{% endfor %}
