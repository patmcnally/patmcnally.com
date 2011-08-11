---
layout: default
title: Projects Index
---

Projects
========

For all the hours spent hammering away at a keyboard, I've manange to
accomplish a few minor things. These are the projects I've either been
responsible for or a major contributor too.

I build primarily on a unix stack, and my framework of choice is[Ruby
on Rails](http://rubyonrails.org/).[Node.js](http://nodejs.org)is becoming increasingly
attractive as way to do really cool things very fast. I also like the
idea of writing <del>javascript</del>[coffescript](http://jashkenas.github.com/coffee-script/)on both sides of browser/server
divide.

UpprDwnr
--------

![UpprDwnr Screenshot](/images/work/uppr_dwnr.jpg)

UpprDwnr was an effort to short-cut sentiment analysis of Twitter by
encouraging the use of two distinct hash tags, #uppr and #dwnr. An
over-enginered node.js process was connected to the Twitter feed,
constantly on the look out for those two tags. Once once was found we
used a simple heuristic to parse out the user, url, or other hashtag
that was being 'uppered' or 'downered'.

Myself and another engineer built both the node.js process and the rails
application powering the public-facing presentation website. We spent
alot of time trying to encourage the use of the hash tags, but they
never took off. Leaving us with a system designed for orders of
magintude more people than were using it. Lesson learned, don't
overbuild until you know you're onto somthing.

Built with[@stubelshe](http://twitter.com/stubelshe)and[@jaredmacke](http://twitter.com/jaredmacke)

Scottrade Hadoop Cluster
--------

![Hadoop Mascot](/images/work/hadoop.png) Scottrade was receiving more
information from it's add placements than it could handle. In an
attempt to wring some buisness data from the terrabytes of log files
I put together a Hadoop Cluster than could be summoned from Amazon's
Web Services. The cluster would gather, do rudimentary interpretation
and translation, and store the data in a large HFS running on-top of
Amazon's EBS. We had just begin to return results when Scottrade
switched ad-serving platforms and began receiving better statistics
directly from their vendor.

Built at the convivial[Brighton Agency] [brighton].

Growing Knowldege
--------
![CottonCommunity Screenshot](/images/work/growingknowledge.png)

The Growing Knowledge Newsletter, Agronomic Update, and Agronomic
Alerts are read by hundreds of farmers a day. These communications are
tailor made at the county level, giving farmers pertinent information
and letting them know of any disease or pests affecting their
area. Getting these communications in the inboxes of farmers was
proving to be a very time intesive process. We built a web application
that integrates with [ExactTarget](http://www.exacttarget.com). This application takes the
pain out of sending a large number or emails to very small groups of
people based on geography.

Built at the vivacious[Brighton Agency] [brighton].

Cotton Community
--------

![CottonCommunity Screenshot](/images/work/cottoncommunity.jpg)

CottonCommunity was a social network for cotton farmers, particularly
cotton farmers who grew Deltapine brand cotton. It also became the hub
for submitting and viewing plot reports from growers working with
experimental varieties. Learned alot about building a big complicated
system in Rails, mostly by doing it the wrong way first. Eventually it
ran solid for the greater part of 3 years before it was put to
pasture. Learned even more about when you should be saying no, like
maybe from the very beginning.

Built at the indefatigable[Brighton Agency] [brighton].


[brighton]: http://www.brightonagency.com

Family
----------

![Family Screenshot](/images/work/family.png)

Yup, I'm that guy, I just put my family as the last item in my list of
projects. If I kept track of sleepless nights per project, this would
definitly have the most.

Built with the beautiful[@smcnally](http://twitter.com/smcnally)