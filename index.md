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
$.ajaxSetup({cache: false});
function parseRSS(url, callback) {
  $.ajax({
    url: document.location.protocol + '//ajax.googleapis.com/ajax/services/feed/load?v=1.0&num=10&callback=?&q=' + encodeURIComponent(url),
    dataType: 'json',
    success: function(data) {
      var feedLimit = 5;
      if (data.responseData.feed.entries.length<5) feedLimit = data.responseData.feed.entries.length;
      for(i=0;i<feedLimit;i++) {
        console.log(data.responseData.feed.entries[i].content)
        var header = $('<h2 class="newstitle"></h2>').html('<a href="'+ data.responseData.feed.entries[i].link +'">'+ data.responseData.feed.entries[i].title +'</a>');
        var date = $('<div class="newsdate"></div>').html(data.responseData.feed.entries[i].publishedDate)
        var content = $('<div class="newscontent"></div>').html(data.responseData.feed.entries[i].content);
        var fbLink = $('<a href="http://www.facebook.com/share.php?v=4&amp;src=bm&amp;u=' + encodeURIComponent(data.responseData.feed.entries[i].link) + '" title="Facebook" target="_blank" ignore="y"><span class="dropdown-item"> <img src="http://uncelestial.67314.x6.nabble.com/images/social/facebook.png" style="width:16px;height:16px;margin-top:.2em;border:none;"> </span></a>"');
        var twitterLink = $('<a href="http://twitter.com/share?text='+ encodeURIComponent(data.responseData.feed.entries[i].title) +'&amp;related=Uncelestial&amp;url='+ encodeURIComponent(data.responseData.feed.entries[i].link)+'" title="Twitter" target="_blank" ignore="y"><span class="dropdown-item"> <img src="http://uncelestial.67314.x6.nabble.com/images/social/twitter.png" style="width:16px;height:16px;margin-top:.2em;border:none;"> </span></a>');
        var moreLink = $('<a href="'+encodeURIComponent(data.responseData.feed.entries[i].link)+'"></a>').html('Read More / Comment');
        var postFooter = $('<div class="newsfooter"></div>').html(fbLink + twitterLink + moreLink);
        $("#newsitems").append(header,date,content,postFooter);
      }
    },
    cache: false
  });
}
$(document).ready(function(){
  parseRSS("http://uncelestial.67314.x6.nabble.com/News-ft2.xml;random2")
});
</script>
<div id="newsitems"></div>
