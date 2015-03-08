---
title: Home
description: If we lived here you'd be home by now. 
image: "/images/pic01.jpg"
social: yes
---

## Welcome

Uncelestial is a band from San Francisco. This is their official site. If you're looking 
to get acquainted quickly, try reading the [bio](/about) or watching some [videos](/videos)

<script type="text/javascript" src="http://uncelestial.tumblr.com/api/read/json"></script>
<script language="javascript">
$(document).ready(function(){
  var output = new Array();
  for(i=0;i<tumblr_api_read['posts'].length;i++){
    if (tumblr_api_read['posts'][i]["type"]=="video") 
    {
      // video post
      output.push('<h3><a href="' + tumblr_api_read['posts'][i]['url-with-slug'] + '">' + tumblr_api_read['posts'][i]['video-caption'].replace("<p>","").replace("</p>","") + '</a></h3>');
      output.push(tumblr_api_read['posts'][i]['video-player']);
    } else if (tumblr_api_read['posts'][i]["type"]=="photo")
    {
      // photo post
      output.push('<h3><a href="' + tumblr_api_read['posts'][i]['url-with-slug'] + '">' + tumblr_api_read['posts'][i]['photo-caption'].replace("<p>","").replace("</p>","") + '</a></h3>');
      output.push('<a href="' + tumblr_api_read['posts'][i]['url-with-slug'] + '"><img src="' + tumblr_api_read['posts'][i]['photo-url-400'] + '" border="0"></a>');
    } else if (tumblr_api_read['posts'][i]["type"]=="audio")
    {
      // audio post
      output.push('<h3><a href="' + tumblr_api_read['posts'][i]['url-with-slug'] + '">' + tumblr_api_read['posts'][i]['audio-caption'].replace("<p>","").replace("</p>","") + '</a></h3>');
      output.push(tumblr_api_read['posts'][i]['audio-player']);
    } else {
      // regular post
    output.push('<h3><a href="' + tumblr_api_read['posts'][i]['url-with-slug'] + '">' + tumblr_api_read['posts'][i]['regular-title'] + '</a></h3>');
    output.push(tumblr_api_read['posts'][i]['regular-body']);
    }
    output.push('<p style="font-size: 14px">Posted to <a href="http://uncelestial.tumblr.com">tumblr</a> on: <a href="' + tumblr_api_read['posts'][i]['url-with-slug'] + '">' + tumblr_api_read['posts'][i]['date'] + '</a> | <a href="http://www.tumblr.com/follow/uncelestial">Follow on Tumblr</a> | <a href="https://www.tumblr.com/reblog/' + tumblr_api_read['posts'][i]['id'] + '/' + tumblr_api_read['posts'][i]['reblog-key'] + '?redirect_to=%2Fblog%2Funcelestial">Reblog Post</a></p>')
    
    $("#blogdiv").html(output.join("\n"));
  }
});
</script>
<div id="blogdiv"></div>
