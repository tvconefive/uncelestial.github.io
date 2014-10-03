---
title: Store
description: Because even GY!BE sells t-shirts. 
---

## Discography

One long page with jQuery UI for cycling through a release's:

- Overview (Artwork, Release Date, Label, Credits, Store Link)
- Tracklist (bandcamp insert with 30-second samples)
- Review clippings
- Remixes (Pull from same .yaml that store uses)
- Lyrics

That way you can link directly to one release's subsection but still do it all in one page.

## Store

- Sells Posters, Clothing, Decor, Toys
- Space for users to contribute their remixes and homemade merch/videos
- Accept user reviews of fan-contributed stuff
- Have fan contributors sign up and give me their PayPal email address first, then invoice them on PayPal later for 30%
- Fan-made digital assets must be hosted by me, then I push them 70% of sales revenue
- Include live recordings/video, zines that interview us, etc
- Digital store with HD vids, 24-bit sound, mp3 version, FLAC version
- Explain our no-stream policy
- Physical copies too

{% for release in site.data.discographymaster %}
{% if release.cdbabywidget %}<div style="max-width:600px;max-height:785px;min-width:300px;"><div style="position: relative;height: 0;overflow: hidden;padding-bottom:100%; padding-top:200px;"><iframe name="album" style="position:absolute;top:0px;left:0px;width:100%;height:100%;border:0px;" src="http://widget.cdbaby.com/{{ release.cdbabywidget }}/album/light/opaque"></iframe></div></div>{% endif %}
{% endfor %}

