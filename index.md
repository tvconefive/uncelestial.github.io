---
title: Home
description: If we lived here you'd be home by now. 
image: "/images/pic01.jpg"
---

<!-- http://uncelestial.67314.x6.nabble.com/News-ft2.xml;cid=1412057808465-339 -->

## Welcome

Uncelestial is a band from San Francisco. This is their official site. If you're looking 
to get acquainted quickly, try reading the [bio](/about) or watching some [videos](/videos).

<script language="javascript">
$.ajaxSetup({cache: false}});
function parseRSS(url, callback) {
  $.ajax({
    url: document.location.protocol + '//ajax.googleapis.com/ajax/services/feed/load?v=1.0&num=10&callback=?&q=' + encodeURIComponent(url),
    dataType: 'json',
    success: function(data) {
      var feedLimit = 5;
      if (data.responseData.feed.entries.length<5) feedLimit = data.responseData.feed.entries.length;
      for(i=0;i<feedLimit;i++) {
        $("#newsitems").append('<h2><a href="'+ data.responseData.feed.entries[i].link +'">' + data.responseData.feed.entries[i].title + '</a></h2><p>' + data.responseData.feed.entries[i].content + '</p>');
      }
    },
    cache: false
  });
}
$(document).ready(function(){
  parseRSS("http://uncelestial.67314.x6.nabble.com/News-ft2.xml")
});
</script>
<div id="newsitems">
</div>
