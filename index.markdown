---
layout: default
title: patmcnally.com
---      
Welcome! I'm a developer living in Saint Louis, Missouri currently
working for [Brighton Agency](http://www.brightonagency.com). I
have a brand new baby and a beautiful wife. When I'm not being a
dad I start awesome projects and finish a few.


{% if site.posts.length > 0 %}

## Blog Posts ##

{% endif %}

{% for post in site.posts %}
 
 * __[{{ post.title}}]({{ post.url }})__ - _{{post.date | date_to_string}}_

{% endfor %}

## Notable Projects ##

<dl>
<dt><strong><a href="http://upprdwnr.com"> UpprDwnr.com </a></strong></dt>
<dd> 
 <p>User tagged sentiment analysis for twitter.
 Built with <a href="http://rubyonrails.org/">Rails</a>
 and <a href="http://nodejs.org/">node.js</a>.</p>
</dd>
</dl>
 
