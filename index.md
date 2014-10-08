---
title: Home
description: If we lived here you'd be home by now. 
image: "/images/pic01.jpg"
social: yes
---

## Welcome

Uncelestial is a band from San Francisco. This is their official site. If you're looking 
to get acquainted quickly, try reading the [bio](/about) or watching some [videos](/videos)

{% for post in site.posts %}
<h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
<p>{{ post.content }}</p>
<p>Posted: {{ post.date | date: "%-d %B %Y" }} | <a href="{{ post.url }}#disqus_thread">comment_count</a></p>
{% endfor %}

<script type="text/javascript" src="http://uncelestial.tumblr.com/api/read/json"></script>
<script language="javascript">
$(document).ready(function(){
  var output = new Array();
  for(i=0;i<tumblr_api_read['posts'].length;i++){
    output.push('<h2><a href="' + tumblr_api_read['posts'][i]['url-with-slug'] + '">' + tumblr_api_read['posts'][i]['regular-title'] + '</a></h2>');
    output.push(tumblr_api_read['posts'][i]['regular-body']);
    output.push('<p>Posted: <a href="' + tumblr_api_read['posts'][i]['url-with-slug'] + '">' + tumblr_api_read['posts'][i]['date'] + '</a></p>')
    $("#blogdiv").html(output.join("\n"));
  }
  
});
</script>
<div id="blogdiv"></div>
